# Power App

## Prerequisites
You'll need to make sure that you're running python 2.7.13
```
python -V
```
If you're not, you'll have to search the internet for how install that version.

## Installation
First of all, this is hosted on Gitlab instead of Github, so you'll need a different ssh key. You can download it [here](https://drive.google.com/a/sparrowav.com/file/d/0B_MvBkpX7P0mU0U2NGJYT3c3ZTg/view?usp=sharing).

Once you have it, you'll need to make sure to add it to the ssh-agent. Again, if using **Windows**, you'll need to run these commands in `Git Bash`.
```
ssh-add /path/to/key/file
```

Navigate to where the app will live.

**_Windows_**
```
cd C:/
```
_**MacOS** or **Linux**_
```
cd ~
```

`Clone` the repo instead of pulling it. This is because we're going to have to switch to a different branch for the China install.
```
git clone git@gitlab.com:adamkaz/spectiv-power.git
```

Now cd into the new directory.
```
cd spectiv-power
```


## Configuration

If you're in **China**, you'll need to checkout the appropriate branch.
```
git checkout newStrips
```

Install the dependencies
```
pip install -r requirements.txt
```

Next, you'll need to set the environment variable. Replace `value` with `project.server.config.DevelopmentConfig` unless you're in **China**. Then `project.server.config.ProductionConfig` should be used instead.

_**Windows** - You'll have to run this in an Administrator Powershell session_
```
[Environment]::SetEnvironmentVariable("APP_SETTINGS", "value", "Machine")
```

_**MacOS** or **Linux**_
```
export APP_SETTINGS="value"
```

Next, you'll need to update layout.json with the layout for the rack power, pods and alarms
```
atom layout.json
```
*Make sure to name pods `Pod_Pwr_XX` where `XX` is the number. Racks should be `Rack_Pwr` or `Rack_Pwr_XX` if you need more than one.*

Finally, after layout.json is the way it should be, this script will use it to set up the database.
```
python manage.py initialize_system
```

## Running the App
Now it should be as simple as this command, replacing `address` with the actual ip of the computer.
```
python manage.py runserver -h address -p 80
```

## Autostarting the application
