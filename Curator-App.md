# Curator App
The App is where you'll go to add, remove, and edit players, content, and playlists in any given system.

**Disclaimer** - Please do not install this on a machine that is going to live on an IMAX site. If for some reason you can't avoid it, DO NOT FORGET TO REMOVE IT before you leave. Anyone with access to this app will has access to all other active installations worldwide.

**Disclaimerer** - This part of the process will be much prettier down the road. Apologies.

#### Authentication
Be sure to follow the instructions [here](https://github.com/euroclydon37/curator-installation/blob/master/README.md) to get your ssh credentials up and running for the following commands. **Windows** requires that you run these commands in `Git Bash` as an Administrator.

## Installation
Create and move into the directory that `Curator App` will live in.
```
mkdir C:/Curator-App && cd C:/Curator-App
```

Initialize the local repo and pull from the online repository
```
git init
git pull git@github.com:euroclydon37/curator-app.git master
```
Install all of the dependencies
```
npm i
```

For the app, you'll have to install `Electron` and `Gulp` globally
```
npm i -g electron
npm i -g gulp
```

And Gulp needs to also be installed locally.
```
npm i gulp
```

## Run the App
It's as simple as a `Gulp` command.
```
gulp watch
```

## Disable Dev Tools
Open the `main.js` file.
```
atom app/main.js
```

Replace
```
win.webContents.openDevTools();
```
with
```
//  win.webContents.openDevTools();
```
