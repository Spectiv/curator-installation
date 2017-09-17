# Android Player

## Download the Source Files
Make sure that you've started your ssh-agent and added the `github_rsa` key to it.
_**Windows** - as always, make sure to run this in `Git Bash`_

If that's up and running, navigate to where the app is going to live and clone the repo.
_**Windows**_
```
cd C:/
git clone git@github.com:euroclydon37/Displayer.git
```

_**MacOS** or **Linux**_
```
cd ~
git clone git@github.com:euroclydon37/Displayer.git
```

## Installation
Next, you'll need to open the `Displayer` directory in Android Studio.

Once the project is open, you'll want to do the following.
1. Click `terminal` in the bottom left of the window. If you don't see it, click the square icon in the far bottom left.
2. Connect to each monitor using the following command, replacing `ip` with the actual address of the device.  
```
adb connect ip
```
3. Once you've connected to all of the displays you wish to install the app on, you'll click the green 'play' button at the top center of the window.
4. Select all of the displays you wish to install to in the popup menu and confirm.

## Disconnect Android Studio
If you click the 'stop' button, it will stop the app on all of the displays. You should instead run the following in the terminal.  
```
adb kill-server
```
