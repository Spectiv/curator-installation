# Curator Server
`Curator server` is the hub that controls all of the Curator players that exist on your network.

# Installation

### Prerequisites
[Nodejs](https://nodejs.org/en/) and [Git](https://git-scm.com/) have to be installed. Make sure to get the latest version of Node.

### Get SSH configured for Github
_**Windows Note**: you'll need to run the commands in this section in Git Bash, which gets installed with Git. You should be able to search for it in the start menu._  

First, we'll need to download the ssh private key file [here](https://drive.google.com/a/sparrowav.com/file/d/0B_MvBkpX7P0mTGhod0hJR0JHeUk/view?usp=sharing). It'll require that you sign into your Spectiv Google account.

After the key downloads, we'll start the ssh agent that will handle authentication for us with the following command.  
`eval "$(ssh-agent -s)"`  

Once that's running, we'll need to add the key file to that agent. It'll ask for a password. Open Slack and type `github key file password` to get the password.  
`ssh-add /path/to/key/file`

### Download Curator Server
Open a terminal (or Powershell) instance.
Create and navigate to the directory that `Curator Server` will live in.

*Windows (Powershell)*  
```
mkdir C:\Curator-Server; cd C:\Curator-Server
```

*Linux and MacOS*  
```
mkdir ~/Curator-Server && cd ~/Curator-Server
```

Initialize the directory for Git and download `Curator Server`
```
git init
git pull git@github.com:euroclydon37/Curator-Server.git master
```

# Configuration

We need to configure the environment before starting the server. Let's start with installing all of the dependencies.
```
npm install
```
Next, we need to create the site-specific `.json` file.  

*Powershell*
```
echo $null >> data/site-config.json
```
*MacOS or Linux*
```
touch data/site-config.json
```

Open `data/site-config.json` and paste the following into it. Replace `LocationName` with the actual name that you want to show up in the app.
```json
{
	"name":"LocationName",
	"autostart":true
}
```

# Running the server
We're going to use a process manager to run the server. This will make it easier to check on the status of the server and still give us the ability to view its output if we choose. It'll also restart it if it crashes for whatever reason.  

First, let's install it.

_If working in **Powershell**, run this command in a separate Administrator session and omit `sudo`_
```
sudo npm install -g pm2
```

Once PM2 is installed, we need to register it so that we can remotely monitor our processes
```
pm2 register
```
To get the password, open slack and type `pm2` into any channel. Slackbot will respond with the account information.

Once that's finished, it should launch a browser window where you can sign into PM2 and verify that the process information is showing up.

Now you're ready to start the process.  
_**Powershell Note**: Run this command in the original Powershell session you opened._
```
pm2 start content-server
pm2 start main.js
```

# Conclusion
You should be up and running and the server should be viewable from the app, now.
