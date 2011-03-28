##GrowlRender 

**DESCRIPTION** :	monitoring daemon for Maya and Mental Ray (MacOS)

**AUTHOR** :		Pierre Lhoste


**VERSION** :		0.3 (March 28 2011)


**LICENSE** : 		BSD

![sample growl notifications](https://github.com/peterhost/growlrender-maya-mentalray/blob/master/shell_version/extra/img/sample.png?raw=true "Better Growl notifications for Mental Ray and Maya OSx")

##INSTALLATION :

###MacOS app

1. Download [growlrender.app](http://)

2. Run it !

3. See below (MORE section) to learn about growlrender command line parameters

###Shell version :

If you prefer to run growlrender from the command line instead, follow these instructions :

1. either clone this repository or extract [this archive](https://github.com/peterhost/growlrender-maya-mentalray/tarball/master) someplace

2. copy the *growlrender-maya-mentalray* folder someplace within your $PATH

3. launch growlrender from the command line `growlrender --all`. It will run in the background from now on, and *automatically* detect when a *Mental Ray* render is launched

4. choose Mental Ray as your rendering engine in Maya

5. set "Verbosity Level" in Mental Ray Rendering Options to "Detailed Messages" 

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
		   -q --quiet  growlrender doesn't print status messages to STDOUT.
    
		   GROWL NOTIFICATIONS :
		   --debug   turn on 'debug' notifications     (default off)
		   --warn    turn on 'warn' notifications      (default off)
		   --info    turn on 'info' notifications      (default off)
		   --error   turn on 'error' notifications     (default off)
		   --progr   turn on 'progress' notifications  (default off)
   
		   --all     turn on ALL notifications
		   --progranderr   turn on 'progress', 'error', 'warn'
		   --debug   also show uncaught notifications  (default is off)
   
		   --sticky  growl notifications are sticky    (default is off, except
		                                                for FATAL or SUCCESS which
		                                                are always sticky )
   
		   ALERTS:
   
		   if the growl daemon is stopped or crashes by itslef :
		    -gf --growl-check-freq            frenquency in seconds of checks for
		                                      the main GROWL service                 
		    -nk --no-keepalive                tells growlrender to exit whenever
		                                      the main growl daemon crashes,or is disabled.
		    -w --wall-notify-on-growl-crash       sends alert to 'wall'
		    -s --sound-notify-on-growl-crash      plays a sound alert 
		    -sw --all-notify-on-growl-crash       both of the preceding
                                                  
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