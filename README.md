##GrowlRender 

**DESCRIPTION** :	monitoring daemon for Maya and Mental Ray, designed for MacOS, but might work on other OSes

**AUTHOR** :		Pierre Lhoste

**VERSION** :		1.0 (March 18 2011)

**LICENSE** : 		BSD

![sample growl notifications](https://github.com/peterhost/growlrender-maya-mentalray/blob/master/extra/img/sample.png?raw=true "Better Growl notifications for Mental Ray and Maya OSx")

##USAGE :

1. either clone this repository or extract [this archive](https://github.com/peterhost/growlrender-maya-mentalray/tarball/master) someplace

2. copy the *growlrender-maya-mentalray* folder someplace within your $PATH

3. **edit the growlrender script** and change the line reading

    `pathToGrowlRender="$HOME/bin/growlrender-maya-mentalray"`
    to make it point to where your growlrender-maya-mentalray directory actually is

4. launch growlrender from the command line. It will run in the background from now on, and *automatically* detect when a *Mental Ray* render is launched

5. choose Mental Ray as your rendering engine in Maya

6. set "Verbosity Level" in Mental Ray Rendering Options to "Detailed Messages" 

   `render -> batch render -> Messages -> Verbosity Level`

   or `render current frame -> batch render -> Messages -> Verbosity Level`

##MORE :

See the help for runtime options ( `growlrender -h`)
