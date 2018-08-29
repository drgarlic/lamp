![lamp](previews/lamp.png)

# Description

`lamp` is a very simple deamon-less terminal effect manager. The main goal of this script is to push the potential of `art` even further by using it's api and taking the window focus to another level. There are different modes available, which are quite unique in there own way. If you have some ideas for a new mode, open an issue and let me know !

**NOTE:** The top image is using 3 modes at the same time !

# How to install ?

## Dependencies

- `art`: used to process everything including colors
- `xdotool`: used to get the name of the focused window

## Insctructions

### Bash

Add this lines to your `.bashrc` (or any other shell run commands file):

```bash
# Set title of the window (used in lamp)
PROMPT_COMMAND='echo -en "\033]0;$(tty)\007"'
DISABLE_AUTO_TITLE=true
```

### Installation

Add `lamp` to your `PATH`:

```bash
cd WHEREVER_YOU_WANT
git clone https://github.com/gawlk/lamp.git
cd lamp
echo "PATH="${PATH}:$( pwd )"" >> ${HOME}/.bashrc
```

### Window Manager

Now the hardest part, `lamp` **is deamon-less**, which means it has to be ran each time a new window is being focused.

Some may disagree but it was a clear choice from the start, feel free to make a deamon if want to !

So the idea is to change the configuration file of your WM and make it run `lamp` everytime you:
- kill a window
- focus a window
- change the workspace
- open a terminal

Basically, you just need to do something like that: `ACTION && lamp`. 

**NOTE:** it's very likely that `lamp` doesn't launch properly after opening a terminal but don't worry there is a fix for that. Just instead of `TERMINAL && lamp`, change it to `lamp -t TERMINAL`.

One advantage is that you don't need to configure the colors of your terminal after that, **they will automatically update themselves.**

Here are examples, which illustrates how it can be done for:
- [2bwm](https://github.com/gawlk/dots/blob/master/2bwm/config.h)
- [bspwm](https://github.com/gawlk/dots/blob/master/sxhkd/sxhkdrc)

Unfortunately, if your WM supports mouse events and you can't or don't want to disable them, you might have undesired results like not having `lamp` launched when a window is being focused.

I had a situation like that with `2bwm`, which focuses every window that happens to be under the mouse pointer. Since this option can't be disable without changing the source code, I decided to change it and make instead 2bwm [launch `lamp` everytime the focus is set](https://github.com/gawlk/dots/blob/master/2bwm/2bwm.c?utf8=%E2%9C%93#L1632).

I understand that this may not be practical for everybody but there is no other way without a deamon.

### Tmux (optional)

If you are a `tmux` user, you need to add those lines to your `tmux.conf`:

```
set -g set-titles off
set -g allow-rename off
```

**NOTE:** This fix does not work when `tmux` is launched directly in your `.bashrc`. I'm still looking for a solution.

# How to use ?

```
lamp - A daemon-less terminal focus manager

Example: lamp -m "4+2+1"

Arguments:
(none)                  Launch lamp
-f | -force             Force the refresh of the cache
-h | -help              Display this menu and exit
-m | -modes "number"    Set a different mode or modes to load
-t | -terminal "name"   Fix for terminal launch 
```

# TODO

- Add more modes
- Find a better way to determined which terminal is being focused

# Previews

## Hightlight (mode 1)

### Dark version

![mode1_dark](previews/mode1/dark.png)

### Light version

![mode1_light](previews/mode1/light.png)

## Yin Yang (mode 2)

### Dark version

![mode2_dark](previews/mode2/dark.png)

### Light version

![mode2_light](previews/mode2/light.png)

## Stealth (mode 3)

### Dark version

![mode3_dark](previews/mode3/dark.png)

### Light version

![mode3_light](previews/mode3/light.png)

## Black and white (mode 4)

### Dark version

![mode4_dark](previews/mode4/dark.png)

### Light version

![mode4_light](previews/mode4/light.png)
