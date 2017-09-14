# Curator Server
`Curator server` is the hub that controls all of the Curator players that exist on your network.

# Installation

### Prerequisites
[Nodejs](https://nodejs.org/en/) and [Git](https://git-scm.com/) have to be installed. Make sure to get the latest version of Node.

### Get SSH configured for Github
_**Windows Note**: you'll need to run the commands in this section in Git Bash, which gets installed with Git_  

First, we'll need to download the ssh private key file [here](https://drive.google.com/a/sparrowav.com/file/d/0B_MvBkpX7P0mTGhod0hJR0JHeUk/view?usp=sharing). It'll require that you sign into your Spectiv Google account.

After the key downloads, we'll start the ssh agent that will handle authentication for us with the following command.  
`eval "$(ssh-agent -s)"`  

Once that's running, we'll need to add the key file to that agent.  
`ssh-add /path/to/key/file`  
_It'll ask for a password. It's one of the usual passwords we always use._

### Download Curator Server

Open a terminal (or Powershell) instance.
Create and navigate to the directory that **Curator Server** will live in.

**Linux and MacOS**  
```
mkdir ~/Curator-Server && cd ~/Curator-Server
```

**Windows (Powershell)**  
```
mkdir ~\Curator-Server; cd ~\Curator-Server
```
