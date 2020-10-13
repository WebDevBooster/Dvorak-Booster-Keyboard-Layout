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

So, on Linux, change into the `/usr/share/X11/xkb/symbols` directory, create a backup copy of the "us" file there and then replace the contents of the "us" file with my version. 

To copy that file to a remote server, `rsync` seems to be most suitable for the job. 

I first ran the following command to copy (via ssh) the 'us' file 
which, in my case, is located in /home/alex/Desktop/ on the local system to the Desktop of the remote server:  
`rsync -e ssh /home/alex/Desktop/us alex@192.168.1.8:~/usr/share/X11/xkb/symbols`.

Obviously, replace "alex@192.168.1.8" with your user name and server IP.

`-e "ssh options"` specifies ssh as the remote shell. 

Then I login or ssh onto that remote server and use the following command to copy the 'us' file from the desktop to the '/usr/share/X11/xkb/symbols' folder:  
`sudo rsync /home/alex/Desktop/us /usr/share/X11/xkb/symbols`

Trying to do that in one step via this command:  
`sudo rsync -e ssh /home/alex/Desktop/us alex@192.168.1.8:/usr/share/X11/xkb/symbols`  
was yielding this error on CentOS 7:  
`rsync: mkstemp "/usr/share/X11/xkb/symbols/.us.ie2EEP" failed: Permission denied (13)`

That error appears to be coming from SElinux but I didn't want to disable SElinux just to copy over a file.

