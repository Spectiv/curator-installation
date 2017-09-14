# Curator Installation
This repo details how to install all of the various components of a Curator system.

## Prerequisites
[Nodejs](https://nodejs.org/en/), [Git](https://git-scm.com/), [Android Studio](https://developer.android.com/studio/index.html) and [Atom](https://atom.io/) have to be installed. Make sure to get the latest version of Node.

## Get SSH configured for Github
_**Windows Note**: These commands will have to be run in Git Bash, which is installed with Git. Leave the session open as you work through the other installation instructions, as you'll need it from time to time._  

First, we'll need to download the ssh private key file [here](https://drive.google.com/a/sparrowav.com/file/d/0B_MvBkpX7P0mTGhod0hJR0JHeUk/view?usp=sharing). It'll require that you sign into your Spectiv Google account. After the key downloads, we'll start the ssh agent that will handle authentication for us with the following command.  
```
eval "$(ssh-agent -s)"
```

Once that's running, we'll need to add the key file to that agent. It'll ask for a password.  
```
ssh-add /path/to/key/file
```
Open Slack and type `github key file password` to get the password.


## Installation
[Curator Server](https://github.com/euroclydon37/curator-installation/blob/master/Curator-Server.md) is the hub that controls all of the players running on the network.  
[The Android app](https://github.com/euroclydon37/curator-installation/blob/master/Android-Player.md) displays images and streams videos given to it by `Curator Server`.  
[The Curator app](https://github.com/euroclydon37/curator-installation/blob/master/Curator-App.md) is the place where users can configure players, content, and playlists.
