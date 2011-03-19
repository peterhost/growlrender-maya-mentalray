##GrowlRender 

**DESCRIPTION** :	monitoring daemon for Maya and Mental Ray (MacOS)

**AUTHOR** :		Pierre Lhoste

**VERSION** :		0.1 (March 18 2011)

**LICENSE** : 		BSD

![sample growl notifications](https://github.com/peterhost/growlrender-maya-mentalray/blob/master/extra/img/sample.png?raw=true "Better Growl notifications for Mental Ray and Maya OSx")

##INSTALLATION :

###MacOS app

1. Download [growlrender.app](http://)

2. Run it !

3. See below (MORE section) to learn about growlrender command line parameters

###Shell version :

If you prefer to run growlrender from the command line instead, follow these instructions :

1. either clone this repository or extract [this archive](https://github.com/peterhost/growlrender-maya-mentalray/tarball/master) someplace

2. copy the *growlrender-maya-mentalray* folder someplace within your $PATH

3. **edit the growlrender script** and change the line reading

    `pathToGrowlRender="$HOME/bin/growlrender-maya-mentalray"`
    to make it point to where your growlrender-maya-mentalray directory actually is

4. launch growlrender from the command line `growlrender --all`. It will run in the background from now on, and *automatically* detect when a *Mental Ray* render is launched

5. choose Mental Ray as your rendering engine in Maya

6. set "Verbosity Level" in Mental Ray Rendering Options to "Detailed Messages" 

   `render -> batch render -> Messages -> Verbosity Level`

   or `render current frame -> batch render -> Messages -> Verbosity Level`

##MORE :

See the help for runtime options ( `growlrender -h`)

**GrowlRender for Maya and Mental Ray**

**description**:
			 monitor the rendering process of a Maya scene with Mental Ray
             via (detailed) growl notifications. This script is intended for
             use on macOS X Leopard, but should be easilly adapted to other
             growl-compliant OSes
             Growl must be running on your system otherwise growlrender will
             exit (and whinny in disagreement)

**usage**: growlrender {options} {logfile} 

   *logfile* :  
			path to your maya render logfile (if not provided, the default,
            /Users/you_user_name/Library/Logs/Maya/mayaRender.log is used)

   *options* :

    START/STOP DAEMON :
        by default, calling growlrender will start/restart the daemon. If you
       wish to stop it, use the --stop option
       
       --stop      stops the last running growlrender daemon
       --status    tells if growlrender is running
        
       NOTIFICATIONS :
       --debug   turn on 'debug' notifications     (default off)
       --warn    turn on 'warn' notifications      (default off)
       --info    turn on 'info' notifications      (default off)
       --error   turn on 'error' notifications     (default off)
       --progr   turn on 'progress' notifications  (default off)
       --all     turn on ALL notifications
       --progranderr   turn on 'progress', 'error', 'warn'
       
       --sticky  growl notifications are sticky    (default is off, except
                                                    for FATAL or SUCCESS which
                                                    are always sticky )

       --debug   also show uncaught notifications  (default is off)
       
       ALERTS:
       -q --quiet       growlrender doesn't print anything to STDOUT, to
                        your wall, and doesn't play any sound
       
       if the growl daemon is stopped or crashes by itslef :                 
        -nwh --no-whinny-on-growl-crash   won't play the sound alert 
        -nwa --no-wall-alert              won't send the 'wall' message
        --keepalive       		growlrender won't exit if the main growl daemon crashes,
                           		or is disabled. No whinny, no wall alert.
        --keepalive-noisy 		same but ALL alerts are active.
                                               
       OTHERS :
       --growltimeout=xxx   set the number of nanoseconds between two consecutive
                            growl notifications of one given type. Lower than 300000
                            is hazardous
                       
       -? -h --help    print this message
   
   *NB* :

	1. only one instance of growlrender can be launched by user
    2. The 'growl watching' sub-daemon only works on Macos for now


##TODO


* debuging, better parsing of mayarender.log (especially network rendering)

*  remote host notifications

*  elapsed time notifications