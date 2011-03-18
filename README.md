##GrowlRender 

**DESCRIPTION** :	monitoring daemon for Maya and Mental Ray, designed for MacOS, but might work on other OSes

**AUTHOR** :		Pierre Lhoste

**VERSION** :		1.0 (March 18 2011)

**LICENSE** : 		BSD

![sample growl notifications](https://github.com/peterhost/growlrender-maya-mentalray/blob/master/extra/img/sample.png?raw=true "Better Growl notifications for Mental Ray and Maya OSx")

##USAGE :

1. either clone this repository or extract [this archive](https://github.com/peterhost/growlrender-maya-mentalray/tarball/master) someplace

2. either
	- copy the *growlrender-maya-mentalray* folder someplace within your $PATH
	- make a symbolic link to 'growlrender' in a directory within your $PATH
	  ex : `ln -s growlrender /usr/local/bin/growlrender`

3. launch growlrender from the command line.

4. choose Mental Ray as your rendering engine in Maya

5. set "Verbosity Level" in Mental Ray Rendering Options to "Detailed Messages" 

   `render -> batch render -> Messages -> Verbosity Level`

   or `render current frame -> batch render -> Messages -> Verbosity Level`

See the help for runtime options ( `growlrender -h`)
