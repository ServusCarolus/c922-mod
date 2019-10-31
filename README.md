# c922-mod
Change or reset some camera settings for the Logitech c922 webcam.

# Syntax forms:

    c922 <mod|default> <0-9|device-name>
    
    Examples:
    
    c922                      show help
    c922 mod                  modify settings of /dev/video0
    c922 default              reset  settings of /dev/video0
    c922 mod     1            modify settings of /dev/video1
    c922 default 1            reset  settings of /dev/video1
    c922 mod     /dev/video2  modify settings of /dev/video2
    c922 default /dev/video2  reset  settings of /dev/video2

# Requirements
Install the `v4l2-ctl` program from its respective package.

# Settings
The changes are self-contained in the script and can be modified by editing the script. The whole point is to make a number of changes that increase framerate. We turn off auto exposure and set `exposure_absolute` (think aperture) to 250 so that we get enough light without slowing the frame rate. We compensate by increasing `gain` (think ISO), yet in a way that tries to avoid too much noise. We adjust white balance to avoid the "zombie effect" and turn off autofocus to increase frame rate.
