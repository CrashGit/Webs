# Webs
Window Management Tool

### Snap, Shackle, Plot!

*Start your day off right with a nice delicious bowl of*... wait, hold on. This isn't a commercial for breakfast cereal.

But it is a script that introduces a (maybe) new way of moving/resizing windows. To be honest, I'm not up-to-date with other tools so maybe this isn't a new idea, but I think it's neat and wanted to share.

Here's a quick (albeit old) demonstration so you don't feel lost when reading about how it works:

https://github.com/CrashGit/Webs/assets/31493162/1b8d40f6-a0a9-43d9-a7e8-7f3e222a7e97



## Why does this tool exist?

When I think of third-party window management tools, I think of having to press a hotkey to move a window to a pre-determined position with a pre-determined size. Depending on your needs, this can result in a lot of hotkeys and in turn, a lot of memorization of hotkeys. This is the problem I aim to "solve" by using intuitive directional movement. I'm not saying it's better than existing methods, just more different :)


## So how does it work?

Well, little Susie, I'm glad you asked. (Or you could try it out yourself!)

For simplicity, let's just say your window is maximized. You would hold down some modifier key (defaulted to `CapsLock`) to enable other keys to reposition/resize the window. By default, these other keys are `I, J, K, L`, obviously correlating to directions `up left down right` respectively.

Now let's say you pressed `L` to go right. The window would now be moved and resized to take up the right half of the screen. Pressing `J` from here would move the window to the left half and pressing `L` again would move it back to the right half.

Before I go further, to help understand how these adjustments are made, imagine when you attempt to move a window in the same direction where it is already against the side of the screen, that you're smushing it, and therefore making it smaller.

Going back to our example, from this right half position, going right again would adjust the window to be on the right thirds of the screen. Going left would put the window in the middle thirds, and going left again would move it to the left thirds of the screen.

Okay, so now you're on the left thirds of the screen. Attempting to go down from here with `K` would smush the window down vertically, cutting it half. Going down again would smush it further to 1/3 height. With your window now 1/3 in width and 1/3 in height, it could effectively fit on your screen 9 times. This 3x3 grid formation is the max default, meaning the window won't be squished down any further if you tried but it can be changed by adjusting `grid_size`.

**Do note:** as mentioned in the script, you shouldn't make this value much higher. Most, if not all, windows have a minimum size. Attempting to make them smaller than they can go (without external forces like WinSetRegion or maybe a certain DLLCall) may not allow them to play nicely in a smaller grid.

Attempting to smush the window smaller than the grid size allows for will either make the window full width/height depending on what side of the screen it is attempted on, or if it already is full width/height, it will make the opposite half size. You may have to play with this to understand what I mean, but it exists to alleviate situations where you make the window too small in a direction and you would normally have to start the process over.



### Bonus features!


1. You don't have to worry about manually moving/resizing windows. It automatically determines a grid position depending on what position and size the window is (this aspect could probably be improved but is good enough for now). No need to save window positions and sizes to a map or external file.

2. I know I called having many hotkeys a problem, but you can still create hotkeys to move and resize the window where you want. See the example near the beginning of the script to see how it works.

3. Whenever you reposition a window with the hotkeys, you will see, what I call gui guides. In the current grid formation of the window, these gui guides will show you adjacent positions you can freely move the window to. These may help you get your bearings when using the tool.

&nbsp;

**Additional Notes:**

I have also included **hotkeys** to:

1. Move the window to previous and next monitors that allow the window to maintain its position in the grid and show the gui guides on that other monitor.

2. Maximize the window.

3. Move the window to the closest grid position based on the window's size and position.

&nbsp;

I personally haven't noticed any bugs yet due to the script itself. Windows 11 Notepad had issues but that's not surprising given that other AHK functions behave weirdly with this particular program on this Windows version. Perhaps there are issues with DPI scaling; I did not test for that. I'm sure I did miss something that isn't part of my setup or is part of a less common scenario but what code doesn't have bugs ;)

## In Conclusion

You snap a window in a direction where it will become confined to a plot in a grid-like system. Bet that "Snap, shackle, plot" slogan at the start makes more sense now, doesn't it :P

Moreover, webs are like grids, and if you squint hard enough, the gui guides look like a web! Okay, look. I suck at names. Sue me.
