# Installation on a Mac

1) Install Karabiner-Elements.
2) Copy the contents of `dvorak_booster_karabiner_ascii_cmd_qwerty_v2.1.1.json` Note: this version is designed to work with what Apple calls "British-PC" layout i.e. British English ISO keyboard layout. But you can make adjustments for other layouts. (Read the descriptions inside that JSON to understand how it works.)
3) Paste the contents in Karabiner-Elements under **Complex Modifications**. 
4) Done.

This will enable the Dvorak-Booster layout (except dead keys for diacritics that let you type characters like ä, ö, ü, à, á, ô, ç, ñ etc; that's planned for version 3). 

### Revert to QWERTY on left Cmd

When pressing the *left command* key, it will revert to the regular QWERTY layout. So, shortcuts like Cmd+C, Cmd+V (or any other shortcuts containing Cmd) should work the same way as before. 

### Right Cmd = layer 3; right Cmd + Shift = layer 4

Holding down the *right command* key enables the AltGr layer. And right command + Shift enables the AltGr+Shift layer. 

### Right option = CapsLock toggle

The right option key will function as the CapsLock key. Because the regular CapsLock key is typing a semicolon on the base layer and a colon on the Shift layer. (Those 2 characters are frequently used in programming languages.)

### Dvorak-Booster layout on the ⚠️️login screen⚠️

After thorough testing, you can also open the Karabiner app and under "Misc" click "*Copy the current configuration to the system default configuration*". 

But do this ONLY after thorough testing BEFORE rebooting your Mac. Because this enables the Dvorak-Booster layout on the **login screen** and ⚠️️☢️ **ANY base layout goes through the Karabiner modifications!!!** ☢️️⚠️ In other words, once enabled, ⚠️☢️ it WILL NOT BE POSSIBLE ☢️⚠️ to switch to any other layout on the login screen! Make sure you understand what that means beforehand. (Technically you can switch to other layouts, but every one of them will go through the Karabiner modifications. At least that's how things worked at the time of my setup. And you can't switch off Karabiner when you are on the login screen.)

If you don't enable that option in Karabiner, then you won't have any of those limitations. But that also means you won't have the Dvorak-Booster layout enabled on the login screen. 

Personally, I haven't had any problems with enabling that option. And if something unexpected happens, you'd just have to look up in this file `dvorak_booster_karabiner_ascii_cmd_qwerty_v2.1.1.json` how Karabiner remaps the individual keys on your keyboard on the base and the Shift layer. I added descriptions for each remapping. So, it should be self-explanatory.

So, using Karabiner is a suboptimal and **temporary** solution for now.  
But hopefully, we'll have Dvorak-Booster as a proper, standalone keyboard layout in the future. Because that way we won't have to deal with those limitations. 

