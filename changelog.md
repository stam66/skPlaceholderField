### Version 1.4
- Fixed animation issue thank to @BerndN
- With this fix, the separate hide/show delays removed and replaced with single uDuration custom property.
- Password field with obscured text can have animation as well now!
- Changed controller stack - prototype removed and switching between controls made more robust
- Fixed copy/paste/place issues
- Smaller bug fixes

### Version 1.3
- bug fixes to password field functions
- improvment to controller stack - added automated detection ojbect selection, will automatically load properties of an skPlaceholderFieldGroup when selected or default to prototype if none selected
- Controller stack simplified accordingly; the field top left shows the short name of the selected skPlaceholderFieldGroup, with its tooltip set to the long name of the selection
- added new custom property _skPlaceholderFieldGroup_ that always returns true and identifies the group as such.

### Version 1.2
Converted to from single field to a group to allow more flexbility and features.<br>
##### New features
- Placeholder is now a separate field, so both cursor and placeholder will behave as expected 
- passwordField - set this to true to obscure text with bulletpoints. Show/Hide password button (field "disclosure") appears when passwordField true using the boolean custom property _obscureText_. When entering text, there is an adjustable delay from typing the letter to it being replaced with bullet points (custom property _uBulletDelay_)
- animatedPlaceholder - set this to true to show the placeholder field quickly move off to the right on entering text and moving in from the right if field empty. Note that 'move' is a blocking action so necessarily the action is very brief to stop errors in text entry; it's also switched off if passwordField is true and the obscureText (= replace with bulletpoints) is true.

### Version 1.1
- Simplified properties to minimum required:
  - uPlaceholderText -- the placeholder/hint text to show (defult = "Placeholder text")
  - uNormalTextColor -- textColor for user-entered text (default = 66,66,66)
  - uNormalTextStyle -- textStyle for user-entered text (default = "Plain")
  - uScaleFactor -- scales text relative to field height - defult = 0.4 (40% of the field's Height)
  - uPlaceholderTextColor -- placeholder text's textColor (defualt = 190,190,190)
  - uPlacehodlerTextStyle -- placeholder text's textStyle (default = "Italic")

Only public handler is **resetProps** - resets all field properties to defaults

Behavior changes:<br>
To stop user from being able to select placeholder text (even though this would set the selection to the start of the field on releasing the mouse), the private handler *setTextStyle* was modified to set lockText = true on showing placeholder field and vice versa on hiding the placeholder text.<br>
This has the side effect of hiding the cursor when placeholder text is showing, but the field remains in focus and the cursor appears (and remains visible) on entering text.


### Version 1.0
*Initial release<br>*
uPlaceHolderText -- the text to display when field is empty, disappears on entering field and only reappears if field is empty on exit<br>
uScaleFactor -- scale textsize from 10% to 90% (0.1 - 0.9) of the height of the field. Auto-resizes and centers vertically on field resize. If formatted textheight exceeds the height of the field, it is aligned to top instead
Colors<br>
uTextForLightBackground -- text color to apply to normal text if background of field is light<br>
uTextForDarkBackground -- text color to apply to normal text if background of field is dark<br>
uPlaceholderTextForLightBackground -- placeholder text color to apply to normal text if background of field is light<br>
uPlaceholderTextForDarkBackground -- placeholder text color to apply to normal text if background of field is dark<br>
uBackgroundColor -- field's backgroundColor<br>
uBorderColor -- field's borderColor (note: if 3D is true, the borderwidth of 2 will obscure color as it emulates system defaults - change borderwidth or set 3D to false to see color borders with width of 2)<br>
uBorderWidth -- border width<br>
uPlaceholderTextStyle -- text style for placeholder text (italic, bold or plain)<br>
uNormalTextStyle -- text style for normal text (plain, bold or italic)<br>
