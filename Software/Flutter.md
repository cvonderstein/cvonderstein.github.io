# Flutter

## Using Flutter

I just followed the [Get Started](https://docs.flutter.dev/get-started/install) guide from the official docs.
I opted for the git version to not deal manually with updates.
After that, I ran `flutter doctor`, which told me that I was missing some parts of the Android Toolchain (I already had Android Studio and everything else installed before).
I fixed this by starting Android Studio, clicking onto the three vertical points in the upper right corner (in the main menu, where you select which project you want to open) and choosing SDK Manager there.
Under SDK Tools I checked the Google USB Driver, Android SDK Platform-Tools and the Android SDK Build-Tools (I don't think all of them are neccessary for now).
Then running `flutter doctor` again told me that I need to agree to some Android License and thats it for now I guess.
