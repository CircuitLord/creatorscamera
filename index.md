## Creator's Camera
Creator's Camera is a program for content creators that allows them to make cinematics in games that don't have a keyframing system.

### I want to see it in action.
Fair enough. [Cool showcase video.](https://www.youtube.com/watch?v=s87N4mZ9xgQ)


### How does it work?
Creator's Camera emulates joystick movement on a virtual controller that is detected by games. It then reads scripts that you can make to do fancy camera movements. 

This program never would have been possible without Mogzol's [ScpDriverInterface](https://github.com/mogzol/ScpDriverInterface), which itself is based off Scarlet.Crush's [SCP Server Software](https://forums.pcsx2.net/Thread-XInput-Wrapper-for-DS3-and-Play-com-USB-Dual-DS2-Controller)


### Where can I get it?
You can download Creator's Camera v0.2 [here](https://cloud.kalman98.net/index.php/s/6WQ8Mkc8AmZGfEX/download).
Please keep in mind this is an alpha version, and still very buggy. (check readme for details)


### How do I install it?

Random note, in this release I accidently named some of the folders CameraCreator instead of CreatorsCamera

```markdown
1. Download the file above.
2. Unzip it, and go to the ScpDriverInterface>DriverInstaller folder, and run DriverInstaller.exe, and install the driver. You'll need this for my program to be able to emulate a controller.
3. Go to the CreatorsCamera folder, and run CreatorsCamera.exe
4.  You're done! Refer to the next part for scripting tutorials.
```

### How do I write scripts for it?

 Be sure to check the example scripts in the paths folder to learn about them :)
 
 Note: capital letters are optional
 Note: You can use newlines wherever in your script, it won't mess up anything.
    
    Each script starts with 3 lines
    name:
    desc:
    versionMadeFor:
    Name and desc are basically what they say, just put whatever you want to show up in the program there.
    with versionMadeFor, put the current version of the program it's made for, in this case, 0.2

    After that comes the commands.
    There are quite a few commands at your disposal.
    set1x (value) //Set the value of left stick X axis, somewhere between -32767 and 32768.
    set1y (value) //Same as last, except Y axis
    set2x (value) //ditto
    set2y (value)
    lerp1x (value) (time) //Same as set command, but takes in a time value. This time defines how long it'll take to transition to the new value given. (good for smooth transitions)
    lerp1y (value) (time) //ditto
    lerp2x (value) (time)
    lerp2y (value) (time)
    
    Note, the lerp command does not sleep by itself, so you'll have to call the sleep thing below if you want the script to wait before starting the next movement.

    sleep (MS) //Sleeps the script for a certain amount of time, in millaseconds.
    resetall //Resets all the sticks.
