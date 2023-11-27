# skPlaceholderField
LiveCode Text field with configurable placeholder text<br>
A controller stack/plugin is included to visually set custom properties.<br>
Longer term this will be converted to a script widget. <br>
[Change log](changelog.md)<br><br>
<img width="313" alt="Screenshot 2023-11-20 at 14 04 19" src="https://github.com/stam66/skPlaceholderField/assets/5677273/51013728-38c8-4c16-9a79-d0b3ecc071b3">

### Usage
Click or tab into the skPlaceholderField. If field is empty, the placeholder/hint text will show with color and style as set by custom properties. On typing or pasting text the colour/style changes as per custom properties. <br><br>
If setting the field text by script, send "exitField" to the field afterwards to trigger correct formatting.<br>
Reset the all properties to default with **_resetProps_** (the only public handler)<br><br>
**Note:** to prevent users from being able to select the placehodler text, the fields lockText is set to true when this is showing, which has the side effect of hiding the cursor. However the field remains selectable and the user can freely enter text, paste, or set it by script (keeping in mind that if used in IDE and not standalone, you have to '_Suspend development tools_' for Paste to work).
### Custom properties
All properties have getter and setters - getters provide default values if empty<br>

* **uPlaceholderText** -- the placeholder/hint text to show (defult = "Placeholder text")
* **uNormalTextColor** -- textColor for user-entered text (default = 66,66,66)
* **uNormalTextStyle** -- textStyle for user-entered text (default = "Plain")
* **uScaleFactor** -- scales text relative to field height - defult = 0.4 (40% of the field's Height)
* **uPlaceholderTextColor** -- placeholder text's textColor (defualt = 190,190,190)
* **uPlaceholderTextStyle** -- placeholder text's textStyle (default = "Italic")

### To use the controller stack
- either configure the field as you want and click the 'copy' icon to copy to mainstack, or
- select an existing skPlaceholderField and click the blue arrow top left. If no selected object or no skPlaceholderField selected, it defaults to the controller's prototype field

<img width="611" alt="Screenshot 2023-11-27 at 01 50 11" src="https://github.com/stam66/skPlaceholderField/assets/5677273/0f754c94-597b-4552-ae41-d426e7c515fd">
<br>
The stack is best used as a plugin. Change colors, styles, placeholder text and textScaling (proportionate to field height). To edit an existing skPlacehodlerField, select it in the IDE, open the plugin and click the arrow top left. If no skPlaceholderField selected it will edit the field included with the stack.
A 'reset' svg-button resets all properteis to default; a "copy" svg-button copies the field in the stack to place in the developer's stack.
