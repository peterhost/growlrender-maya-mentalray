NAME :			GrowlRender 
DESCRIPTION :	monitoring daemon for Maya and Mental Ray, designed for MacOS, but might work on other OSes
AUTHOR :		Pierre Lhoste
VERSION :		1.0 (March 18 2011)
LICENSE : 		BSD

USAGE :
1) extract the archive someplace
2) either
	- copy the folder to someplace within your $PATH
	- make a symbolic link to 'growlrender' in a directory within your $PATH
	  ex : ln -s growlrender /usr/local/bin/growlrender
3) launch growlrender from the command line.
4) choose Mental Ray as your rendering engin under Maya
5) set "Verbosity Level" in Mental Ray Rendering Options to "Detailed Messages" 
   (  render -> batch render -> Messages -> Verbosity Level
   or render current frame -> batch render -> Messages -> Verbosity Level )

See the help for runtime options ( growlrender -h)
