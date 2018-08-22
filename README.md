# lamp

`lamp` is a very simple deamon-less terminal effect manager. The main goal of this script is to push the potential of `art` even further by using it's api and taking the window focus to another level. There are different modes available, which are quite unique in there own way. If you have some ideas for a new mode, open an issue and let me know !

## How to install ?

### Dependencies

- `art`: used to process everything including colors
- `xdotool`: used to get the name of the focused window

### Insctructions

#### .bashrc

Add this lines to your .bashrc (or any other shell run commands file).

```bash
# Set title of the window (used in lamp)
PROMPT_COMMAND='echo -en "\033]0;$(tty)\007"'
DISABLE_AUTO_TITLE=true
```
#### lamp

```bash
cd WHEREVER_YOU_WANT
git clone https://github.com/gawlk/lamp.git
cd lamp
echo "PATH="${PATH}:$( pwd )" >> ${HOME}/.bashrc
```

#### Window Manager

Now the hardest part, to be continued...

## How to use ?

TODO

## TODO

- Add more options
- Find a better way to determined which terminal is being focused

## Previews

### Hightlight (mode 1)

#### Dark version

![mode1_dark](previews/mode1/dark.png)

#### Light version

![mode1_light](previews/mode1/light.png)

### Yin Yang (mode 2)

#### Dark version

![mode2_dark](previews/mode2/dark.png)

#### Light version

![mode2_light](previews/mode2/light.png)

### Stealth (mode 3)

#### Dark version

![mode3_dark](previews/mode3/dark.png)

#### Light version

![mode3_light](previews/mode3/light.png)

### Black and white (mode 4)

#### Dark version

![mode4_dark](previews/mode4/dark.png)

#### Light version

![mode4_light](previews/mode4/light.png)
