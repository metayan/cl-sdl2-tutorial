# Common Lisp SDL2 tutorials
Adapted from http://lazyfoo.net/tutorials/SDL/

## Installing the SDL2 Libraries

  The tutorial requires that SDL2, SDL2 Image, and SDL2 TTF are installed before
  running the examples.

### Mac OS X

Mac OS X requires each library to be downloaded and copied to
$HOME/Library/Frameworks or /Library/Frameworks.

 Library Name | Download Link
 ------------ | -------------
 SDL2         | https://www.libsdl.org/download-2.0.php
 SDL2 Image   | https://www.libsdl.org/projects/SDL_image
 SDL2 TTF     | https://www.libsdl.org/projects/SDL_ttf

Running the tutorials will cause Catalina to report that the framework cannot be
opened because the developer cannot be verified. The workaround for this problem
is the following:

1. Navigate to System Preferences -> Security & Privacy -> General on the Mac

2. Run repl.sh

3. When the dialog appears about the developer not being verified, click the
"Cancel" button.

4. Examine the Security & Privacy screen for a button called "Allow Anyway" for
the framework. Click the "Allow Anyway" button with the identified framework.

5. The verification dialog will now appear a second time, but there will be an
option to "Open" the framework. Click "Open".

6. Repeat steps 3 through 5 for the different frameworks.

### Linux

The SDL2 libraries can be installed on a Debian based system with the command
below.

	apt install libsdl2-2.0 libsdl2-image-2.0 libsdl2-ttf-2.0


## Installation

Using [quicklisp](https://www.quicklisp.org/beta/):
```
git clone https://github.com/TatriX/cl-sdl2-tutorial/ ~/quicklisp/local-projects
```

```lisp
> (ql:quickload :sdl2-tutorial)
```


## Running the Examples

Tutorial packages are named as `sdl2-tutorial-XX-DESC`
where `XX` is a number starting from `01`.

```lisp
(sdl2-tutorial-01-hello-sdl:run)
;;
(sdl2-tutorial-04-key-presses:run)
```

## Notes
As far as I can tell `cl-sdl2` in most cases doesn't free created
objects. This means it's up to a user to do so. I've tried to free
allocated resources, but as with any manual memory management I could
miss something. If you notice anything, please create an issue or even
send a PR!
