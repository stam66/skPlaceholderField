# skPlaceholderField
LiveCode Text field with configurable placeholder text<br>
[Change log](changelog.md)

### Usage
Click or tab into the skPlaceholderField. If field is empty, the placeholder/hint text will show with color and style as set by custom properties. On typing or pasting text the colour/style changes as per custom properties. <br><br>
If setting the field text by script, send "exitField" to the field afterwards to trigger correct formatting.<br>
Reset the all properties to default with **_resetProps_** (the only public handler)<br><br>
**Note:** to prevent users from being able to select the placehodler text, the fields lockText is set to true when this is showing, which has the side effect of hiding the cursor. However the field remains selectable and the user can freely enter text, paste, or set it by script.
### Custom properties
All properties have getter and setters - getters provide default values if empty<br>

* **uPlaceholderText** -- the placeholder/hint text to show (defult = "Placeholder text")
* **uNormalTextColor** -- textColor for user-entered text (default = 66,66,66)
* **uNormalTextStyle** -- textStyle for user-entered text (default = "Plain")
* **uScaleFactor** -- scales text relative to field height - defult = 0.4 (40% of the field's Height)
* **uPlaceholderTextColor** -- placeholder text's textColor (defualt = 190,190,190)
* **uPlacehodlerTextStyle** -- placeholder text's textStyle (default = "Italic")

### To use the controller stack
- either configure the field as you want and click the 'copy' icon to copy to mainstack, or
- select an existing skPlaceholderField and click the blue arrow top left. If no selected object or no skPlaceholderField found, it defaults to the controller's prototype field
