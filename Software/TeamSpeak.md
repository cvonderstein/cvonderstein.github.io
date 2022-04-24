---
layout: default
title: TeamSpeak
has_children: false
permalink: software/teamspeak
parent: Software
---

# Change ServerQuery Password

## Prerequisites

I run a teamspeak server in a docker container, which is called `ts3`.
This container has a volume called `ts3-data` mounted at `/var/ts3server/`
All of this runs on an Ubuntu 20.04, so I'm using `apt` as package manager.

If you use a different setup, you might have to change some commands or variables, but everything should be clear if you have a little understanding of whats going on (otherwise you probably shouldn't just execute commands you found on a random website).

Just for completeness, here is my `docker run` command:

```zsh
docker run -d --name ts3 --network host -v ts3-data:/var/ts3server/ -e TS3SERVER_LICENSE=accept --restart unless-stopped teamspeak
```

The username of which I want to change the password is `serveradmin`, the default query login.
Just for this tutorial, I'm assuming that the new password should be `verySafePassword`.
Don't use this, better generate one (although I found that YaTQA seems to have trouble with extremely long passwords or some special characters, which is why I'm using an alphanumerical password just below 40 characters.

## Changing the password

We need to have the `sqlite3` command line interface installed, to install it run

```zsh
sudo apt install sqlite3
```

Get our generated password into the required format:

```zsh
echo -n 'verySafePassword' | openssl dgst -binary -sha1 | openssl base64
```

In this case, I receive the following hash: `yX+IcoRkb8Kw6hlAeisyK0USDSk=`
Write that down for later usage.

Change into the directory of the mounted docker volume:

```zsh
cd /var/lib/docker/volumes/ts3-data/_data
```

Stop the container:

```zsh
docker stop ts3
```

Make a backup copy of the database, in case something goes wrong:

```zsh
cp ts3server.sqlitedb ts3server.sqlitedb.backup
```

Open the database using the sqlite CLI tool:

```zsh
sqlite3 ts3server.sqlitedb
```

In this CLI, enter the following (subsitute the hash given here with the hash you received at the beginning):

```SQL
UPDATE clients SET client_login_password='yX+IcoRkb8Kw6hlAeisyK0USDSk=' WHERE client_login_name='serveradmin';
```

After this, you can close the database using `Ctrl + D`, no further manual saving is neccessary.
Then, you can start the container again:

```zsh
docker start ts3
```
