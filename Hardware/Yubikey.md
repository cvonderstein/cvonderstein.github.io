---
layout: default
title: Yubikey
has_children: false
permalink: hardware/yubikey
parent: Hardware
---

# Yubikey

## 2FA or passwordless login on Ubuntu

You can use Yubikeys for passwordless logins or as a second factor.
The steps to set this up are nearly identical, the differences will be pointed out.

{: .important }
> {: .opaque }
> <div markdown="block">
> {: .warning }
> If you do something wrong here, you might lock yourself out of your user account, so be careful, make sure you understand the instructions, follow them carefully and if possible test it on a machine, that you can afford to lose (or at least reinstall/reset to some backup, e.g. a VM) beforehand.
Also, things might change between versions, so also check against the linked sources, which I used to set it up.
> </div>

These are my sources:

1. [Ubuntu Linux Login Guide - U2F](https://support.yubico.com/hc/en-us/articles/360016649099-Ubuntu-Linux-Login-Guide-U2F) with their linked subpages:
    1. [Enable the Yubico PPA](https://support.yubico.com/hc/en-us/articles/360016649039-Enabling-the-Yubico-PPA-on-Ubuntu)
    1. [Using Your U2F YubiKey with Linux](https://support.yubico.com/hc/en-us/articles/360013708900-Using-Your-U2F-YubiKey-with-Linux)
1. [AskUbuntu to make it passwordless instead of 2FA](https://askubuntu.com/questions/1167691/passwordless-login-with-yubikey-5-nfc)

But why am I writing this, if you should check my sources?
Well, these sources didn't work out the way I wanted them to, so I had to combine them.
Also, I am documenting for myself what I did, in case I want to revert this later.

First, follow 1a to add the PPA.
I followed the *Using Yubico's PPA (Ubuntu and derivatives)*, which you can find if you scroll a little bit down on the page.
So, you run:

```zsh
add-apt-repository ppa:yubico/stable && sudo apt-get update
```

Afterwards, according to 1b, you run

```zsh
dpkg -s libu2f-udev
```

to check, if `libu2f-udev` is installed. For me, it was already installed, but if its not, run:

```zsh
sudo apt install libu2f-udev
```

Then, add the content of <https://github.com/Yubico/libfido2/blob/main/udev/70-u2f.rules> to `/etc/udev/rules.d/70-u2f.rules`.
Run

```zsh
sudo udevadm --version
```

to make sure your udevadm version is greater than 188, otherwise follow the instructions listed on page 1b.
If everything looks good, save the file and reboot your system.
This will not cause any problem and you can login as before, as there is no yubikey requirement set up yet.

After the reboot, open a terminal and install

```zsh
sudo apt-get install libpam-u2f
```

Afterwards, create a directory for your stored keys

```zsh
mkdir -p ~/.config/Yubico
```

Then run

```zsh
pamu2fcfg > ~/.config/Yubico/u2f_keys
```

to link your Yubikey.
You might have to enter your PIN if you set one.
When its light starts blinking, tap on the metal button.
Now you loaded your Yubikey.
To link additional keys, which is especially useful for backup keys if you use this as 2FA (if you only have one key linked and you lose it, you are locked out of your account), run:

```zsh
pamu2fcfg -n >> ~/.config/Yubico/u2f_keys
```

Note, that this uses double `>` instead of single ones, to append the input instead of replacing it.
If your key begins flashing or asks for a PIN, enter it as you've done before.
You can also repeat this step multiple times, if you have more keys.
The official documentation (1) also explained how you can move this file into a safer location (which is only editable by root), which I didn't do.

---

Now starts the important part, where you need to make sure to not do something stupid, and for desktop computers, you should ensure reliable power.

---

Here, we need to decide between

- passwordless, which allows you to log in using only one method, using either your yubikey or your password is sufficient
- 2FA, which always requires your password **and** the yubikey

Both have their downsides, which I'm not going to elaborate further on here.
If you decide for passwordless, replace `required` with `sufficient` in the `auth required pam_u2f.so` line.
You can also use a mixed version, e.g. using passwordless login for the user account but 2FA for sudo.

We start by editing `/etc/pam.d/sudo`.
Thats where I did deviate from the official documentation, as mentioned [here](https://askubuntu.com/a/1305512) (an answer of [2]).
Right **before** the line `@include common-auth`, add (**but do not quit your editor yet**)

```
auth required pam_u2f.so
```

or

```
auth sufficient pam_u2f.so
```

depending if you want to use passwordless or 2FA.
The difference to the official documentation is, that it states to put this line after `@include common-auth`, which didn't work for me.

Save the file but keep the editor open, the change will be active directly.
Open a second terminal and run `sudo echo test`, to test if your configuration works.

For 2FA, the expected behavior is to ask for your password, submitting it with enter and then requiring you to tap on your yubikey (you will not be prompted, but the key will blink).
For passwordless, the expected behavior is to just requiring you to tap your yubikey if it is plugged in, not asking for your password at all, and asking for your password if the yubikey is not plugged in.
Remember that sudo sessions might be open for some time, so make sure to test both if you go passwordless and test them each in their own shell session, to not be fooled by "open" sudo sessions.

If everything works, you can continue and close the editor.
In the next step, we will do the same with `/etc/pam.d/gdm-password` on Ubuntu 17.10 or never, or `/etc/pam.d/lightdm` on Ubuntu 17.04 or older.
This is the change for your user login, so

1. do not do this if the step before did not work
2. this is the point, where you might want to go a different way if you want to go passwordless for your user login but 2FA for sudo.

As this is basically the same step (add the `auth sufficient/required pam_u2f.so` line before `@include common-auth`), I will not cover this in detail again.

Afterwards, you can lock your account and test the change, again, this should take immediate effect.

And thats it!
