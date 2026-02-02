# Installation on a Mac

1) Install Karabiner-Elements.
2) Copy the contents of `dvorak_booster_karabiner_ascii_cmd_qwerty_v2.1.0.json` Note: this version is designed to work with what Apple calls "British-PC" layout i.e. British English ISO keyboard layout. But you can make adjustments for other layouts. (Read the descriptions inside that JSON to understand how it works.)
3) Paste the contents in Karabiner-Elements under **Complex Modifications**. 
4) Done.

This will enable the Dvorak-Booster layout (except dead keys for diacritics that let you type characters like ä, ö, ü, à, á, ô, ç, ñ etc; that's planned for version 3). 

### Revert to QWERTY when pressing left Cmd

When pressing the *left command* key (or left command + Shift), it will revert to the regular QWERTY layout. So, shortcuts like Cmd+C, Cmd+V (and all other shortcuts containing Cmd) should work the same way as before. 

### Right Cmd = layer 3; right Cmd + Shift = layer 4

Holding down the *right command* key enables the AltGr layer. And right command + Shift enables the AltGr+Shift layer. 

### Right option = CapsLock toggle

And the right option key will function as the CapsLock key.

### Dvorak-Booster layout on the ⚠️️login screen☢⚠️

After thorough testing, you can also, under "Misc" click "*Copy the current configuration to the system default configuration*". 

But do this ONLY after thorough testing BEFORE rebooting your Mac. Because this enables the Dvorak-Booster layout on the **login screen** and ⚠️⚠️⚠️☢️ **ANY base layout goes through the Karabiner modifications!!!** ☢️⚠️⚠️⚠️ In other words, once enabled, ⚠️☢️ it WILL NOT BE POSSIBLE ☢️⚠️ to switch to any other layout on the login screen! Make sure you understand what that means beforehand. (Technically you can switch to other layouts on the login screen, but every one of them will go through the Karabiner modifications. At least that's how things worked at the time of my setup.)

