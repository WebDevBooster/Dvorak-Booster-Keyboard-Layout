# Modifying Keyboard Layout on Linux

Compared to Windows and MacOS, Linux seems to be the **worst** in regards to options for modifying/creating a custom keyboard layout. 
While it's fairly easy to do **primitive** modifications to a keyboard layout on Linux, it appears to be impossible to do sophisticated modifications.  
Well, this is because for both Windows and MacOS third-party programs exist that make sophisticated modifications possible. So, strictly speaking all operating systems Windows, MacOS and Linux SUCK when it comes to doing sophisticated modifications to the keyboard layout.

To make primitive/simple modifications to the keyboard layout on Linux, I've been doing the following: 

1) First switch the keyboard layout to "English US Programmer Dvorak".

2) Locate the file with the keyboard layout definitions and make changes to it.

For US English, the file is named `us` and that file is usually located in: `/usr/share/X11/xkb/symbols`

It's a simple text file.  
The definions are located under:  
**partial alphanumeric_keys  
xkb_symbols "dvp"**

`include "us(dvorak)"` means that "dvp" (=Programmer Dvorak) is actually extending/modifying the "us(dvorak)" layout or it was supposed to.

The physical keys are represented by abbreviations inside the angle brackets. `key <TLDE>` means it's the tilde key on the standard US keyboard, `key <BKSP>` is the back space key, `key <CAPS>` is the caps lock key etc. 

Most physical keys are represented as `key <AX01>` where "X" is to be replaced with the letter corresponding with the row whereas the letter "A" is assigned to the lowest row, the letter "B" to the second row from the bottom etc. 

So, in `key <AC01>` the "C" means the physical key is in the third row from the bottom and "01" means it's the second key. I assume `key <AC00>` would be equivalent to `key <CAPS>`? I don't know. 

Following the physical key representation you have the key mappings inside the curly brace/square brackets combo. Inside the square brackets you have (up to) 4 comma-separated key mappings for the states: 

* Unmodified
* Shift key pressed
* AltGr key pressed
* Shift+AltGr key combination pressed

So, in the standard US keyboard layout this:  
`key <AC01> { [ a, A, aacute, Aacute ] };`  
would have meant that in the third row (counting from the bottom) the second physical key (`key <AC01>`) would in the unmodified state produce a lower case letter "a", with a `shift` key pressed an upper case "A", with the `AltGr` key pressed a lower case á (a-acute) and with `Shift + AltGr` an upper case Á (a-acute).

And that appears to be it! 

That's what I meant by "primitive". 

This is a very primitive way of modifying a keyboard layout. The bare minimum that would be needed to make it less primitive is a way of defining **custom dead keys**. But so far (after having wasted a LOT of time on searching) I haven't been able to find a way to define custom dead keys. 

Being able to define CUSTOM dead keys is extremely important for designing a custom keyboard layout. 

Here's one example as to why: 

On Windows (admittedly with the help of a third-party program [KbdEdit](http://www.kbdedit.com)), I assigned the physical caps lock key to the semicolon **dead key**. Here's what that means: 

When I press the physical caps lock key on Windows (with my custom keyboard layout active), nothing happens at first. However, if the next key press is the space bar, then I get semicolon + space. If I were to follow up with the physical A key (instead of space bar), I'd get an ampersand. And following up with the physical J key instead, would produce the right parenthesis etc.

Depending on which key press follows the dead key, I get a different output. That's what a dead key does. It doesn't produce anything by itself but when followed by another key the output is something completely different than what that other key does by default. 

This is **extremely** useful. And not just "useful". That functionality is **absolutely necessary** for an ergonomic keyboard layout. Any ergonomic keyboard layout. Especially one that adheres to the Dvorak philosophy. 

I have several strategically well-positioned dead keys defined for the Dvorak-Booster layout. Those dead key combinations as what makes the Dvorak-Booster layout vastly superior to the regular Programmer Dvorak layout. 

Here's another example: 

The comma key on the Dvorak-Booster layout (W key on the QWERTY layout) is also a dead key. So, by itself that key press doesn't do anything i.e. it's a trigger waiting for instructions depending on what key will be pressed next. So, when followed by space bar (which you do 99% of the time anyway because a comma is almost always followed by a space in text), you get exactly what you'd normally expect: a comma and a space. And if instead of the space bar you follow by a number, you also get exactly what you'd normally expect: a comma and that number. 

BUT... if after pressing the comma key you follow up by another key on the Dvorak-Booster layout, it will transform many of those other keys into something completely different. 

So, the term "dead key" is maybe a bit confusing for some people. I know it was initially for me. Why would anyone want a "dead" key? I think a better name for this functionality would be **"transformer key"**!

Oh, and for those very rare cases when I really just want a comma to be printed (without a space afterwards), then I press the `AltGr` key first and then the comma key. On the Dvorak-Booster layout that combination really just gets me a comma and nothing else. So, in this case I have to press 2 keys to get just one comma. But this is a very minor trade-off considering the fact that you'll almost always need to follow a comma key either with a space or with a number anyway. And in those cases you get exactly what you'd normally expect. And if, for some reason, I wanted 2 consecutive commas, I'd just press the comma key twice.

Anyway, this transformer key (dead key) functionality for producing **custom output** (and not just pre-defined accented letters) is vitally important for an ergonomic keyboard layout and Linux seems to lack options for that. So, just like with Windows and MacOS a third-party software is required to achieve the desired functionality and the currently existing options for Linux aren't great. 

[Here is the first version of the "us" file](us_v1.0) that I used for the modified "dvp" layout. 

### TODO: Restore the original "dvp" layout and copy what I currently have there under "dvp" into a new layout named "dvorak-booster".

Note:  
The **mnemonic character names** such as "quotedbl", "dead_acute" and all the others are defined in  
`/usr/include/X11/keysymdef.h`  
and as pointed out in that file, you don't actually need any of those mnemonic names because any possible Unicode character can simply be used by itself. E.g. instead of "quotedbl" you can use "U0022" (without quotation marks) just as well. And the key definitions such as `<TLDE>`, `<AE01>` etc. are in  
`/X11/xkb/keycodes/evdev`. 

See also [this documentation on X Keyboard Extension](https://www.x.org/wiki/guide/hutterer-kbd/) for more information regarding keycodes and keymap conversion.

`setxkbmap -print` lists current keymap components. 

To set the keyboard using the X Keyboard Extension, follow the [setxkbmap documentation here](https://www.x.org/releases/X11R7.7/doc/man/man1/setxkbmap.1.xhtml).

Here's another documentation page on [X keyboard extension](https://wiki.archlinux.org/index.php/X_keyboard_extension) that might be worth reading. Using `xev -event keyboard` command you can explore key codes for individual keyboard keys. 

Example output for the 'a' key: 

```shell script
KeyPress event, serial 28, synthetic NO, window 0x3000001,
    root 0x17c, subw 0x0, time 40419817, (1109,-96), root:(1334,584),
    state 0x10, keycode 38 (keysym 0x61, a), same_screen YES,
    XLookupString gives 1 bytes: (61) "a"
    XmbLookupString gives 1 bytes: (61) "a"
    XFilterEvent returns: False

KeyRelease event, serial 28, synthetic NO, window 0x3000001,
    root 0x17c, subw 0x0, time 40419933, (1109,-96), root:(1334,584),
    state 0x10, keycode 38 (keysym 0x61, a), same_screen YES,
    XLookupString gives 1 bytes: (61) "a"
    XFilterEvent returns: False
```

To add the option for selecting the Dvorak-Booster keyboard layout for US English on Linux, the file `us` located in `/usr/share/X11/xkb/symbols/` needs to be modified to add the `dvorak-booster` keymap variant there.

So, change into the `/usr/share/X11/xkb/symbols/` directory, create a backup copy of the "us" file there (`sudo cp us us_BK`) and then replace the contents of the "us" file with my version. 

To copy my "us" file from local to a remote server, `rsync` seems to be most suitable for the job. However, when doing it directly on CentOS 7 things seem to be getting blocked by SElinux. So, you'd probably have to do that in 2 steps.

First run the following command to copy (via ssh) the 'us' file 
which, in my case, is located in /home/alex/Desktop/ on the local machine to the Desktop of the remote server:  
`rsync -e ssh /home/alex/Desktop/us alex@192.168.1.8:~/usr/share/X11/xkb/symbols`.

Obviously, replace "alex@192.168.1.8" with your user name and server IP.

`-e "ssh options"` specifies ssh as the remote shell. 
And if you need to specify a non-standard port, you can do it like this:  
`-e "ssh -p <port-number>"`

Then login or ssh onto that remote server and use the following command to copy the 'us' file from the desktop of the remote server into the '/usr/share/X11/xkb/symbols/' folder:  
`sudo rsync /home/alex/Desktop/us /usr/share/X11/xkb/symbols`

As mentioned, trying to do that in one step i.e. from a local machine via:  
`sudo rsync -e ssh /home/alex/Desktop/us alex@192.168.1.8:/usr/share/X11/xkb/symbols`  
was yielding this error on CentOS 7:  
`rsync: mkstemp "/usr/share/X11/xkb/symbols/.us.ie2EEP" failed: Permission denied (13)`

That appears to be coming from SElinux but I didn't want to disable SElinux just to copy over a file.

And of course, you'll only need to go through the trouble of overwriting that "us" file at the beginning. As time progresses, more and more distros will start including the Dvorak-Booster keyboard layout variant. At that point, it will be just a matter of switching to this new layout the same way you'd switch to any other layout including Standard Dvorak or Programmer Dvorak. 


Here's an example of the commands I use to copy/rsync the files from the `linux-x11` folder (on the Desktop of the destination machine) to `/usr/share/X11/xkb/` folder: 

`sudo rsync /home/alex/Desktop/linux-x11/symbols/us /usr/share/X11/xkb/symbols/us` 

`sudo rsync /home/alex/Desktop/linux-x11/rules/evdev.lst /usr/share/X11/xkb/rules/evdev.lst`

`sudo rsync /home/alex/Desktop/linux-x11/rules/evdev.xml /usr/share/X11/xkb/rules/evdev.xml`

Here's a page that shows the frequency of punctuation and special characters used in programing languages: 

http://xahlee.info/comp/computer_language_char_distribution.html

However, those stats don't provide the whole story. 

For example, to create the code in this HTML snippet: 
```html
<div class="container"></div>
```
...only ONE special character, the dot `.` is required.

This is because typing `.container` and pressing the tab key is all that's needed for emmet to expand `.container` to the code shown above. So, while that code snippet technically contains 8 special characters, none of them are actually typed on a keyboard when you are using emmet or use similar tools for the programming language of your choice. 

And if I wanted to duplicate the above code (to add a second div with a class of container), I'd simply just use the shortcut `Ctrl+D` to achieve that. 

So, automated code snippet expansion and shortcuts that generate code is one thing to consider when looking at statistical data like the data on this page: http://xahlee.info/comp/computer_language_char_distribution.html i.e. how much of the analyzed code was actually typed in on a keyboard vs. the code that was brought in automatically without typing? 

Another important thing to consider are the special characters that you have to type in things like command line or in text editors like **vim** that are frequenty used in programming, git version control, server management etc. Those are very important things to consider because command line is a very important tool that almost all programmers use and the frequency of special characters that you need or have to use on the command line (or with an advanced text editor like vim) can be very different from the frequency of characters in code. 

Here are just two examples: 

The caret symbol (^) is used in vim as a command to jump to the beginning of a line i.e. very important and frequently used. 

As an advanced user on the command line, you'll frequently use the `!$` combination to recall the last argument of the previously typed command (because that saves you a lot of typing). The bang `!` in general is used in many extremely handy [event designators](https://www.gnu.org/software/bash/manual/html_node/Event-Designators.html) on the command line (in bash).

So, while the bang and the caret might *appear* to belong to the least frequently used when looking at the ["all programming languages" stats here](http://xahlee.info/comp/computer_language_char_distribution.html), in reality both the bang and the caret might be as much or more used as the less than `<` symbol when you only consider those things that you actually need to type on a keyboard as opposed to things that are being automatically generated for you with tools like emmet etc.

By the way, you'll absolutely LOVE how easy and pleasant it is to type the `!$` combination on the Dvorak-Booster layout! It's basically just one fluid motion! 

The Dvorak-Booster layout is designed so that ***typing ANY special characters is a JOY!!!*** On the Dvorak-Booster layout, ALL of the special characters that you'll ever need for coding or the command line are accessible on the two most easily accessible levels (base level and AltGr level) and (with the exception of the single and the double quote; both of which are on the base level) ALL of those special characters are located on the two most easily reachable rows (the home row and the top row). Think about that! 

That combined with the fact that the Dvorak-Booster layout also allows you to reach ALL of the arrow keys and the delete key as well as the escape key WITHOUT ever taking your hands off the keyboard... that makes the Dvorak-Booster layout an absolute pleasure to use!

It is probably only a slight exaggeration to say that the Dvorak-Booster layout is ***100 TIMES more pleasant to use*** than the Programmer Dvorak layout! And the Programmer Dvorak layout is already pretty good. 

Once you master the Dvorak-Booster layout — which, if you're coming from QUERTY is probably gonna take you 5 days and coming from classic Dvorak may take you 2-3 days — typing with the Dvorak-Booster layout is gonna feel like walking with an ***anti-gravity backpack!*** 

What??...  
You don't know what walking with an anti-gravity backpack feels like?... 

Well, in that case, you definitely need to learn the Dvorak-Booster layout! Take 5 days off and do it! That will be the best 5 days of your LIFE! 

After all, if somebody gave you an anti-gravity backpack, you'd be willing to spend 5 days on learning how to use it (to avoid fatal accidents and crashing into buildings), right? 

So, go ahead, spend a few days on learning the Dvorak-Booster layout because after that you'll feel like you gained a new superpower! Or... you'll feel like someone gave you a new anti-gravity backpack! :-) 

