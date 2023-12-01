# skPlaceholderField
LiveCode Text group-based widget providing a field with configurable placeholder text.<br>
This is a group with 3 fields that enables placeholder text (hiding instantly or with animation) and password field functions.<br>
Current version: 1.2 <br>[Change log](changelog.md)<br><br>
<img width="313" alt="Screenshot 2023-11-20 at 14 04 19" src="https://github.com/stam66/skPlaceholderField/assets/5677273/51013728-38c8-4c16-9a79-d0b3ecc071b3">

**Features**
 - If field is empty, will show a hint/placeholder text with an indicative text style (defult = italic, light gray)
 - If user has pasted or entered text, or if text set by script, will show the text with indicative text style (default = plain text, near-black)
 - The field will toggle visiblity of placeholder text while modfiying text, as needed
 - Textsize is determined by field height - and configurable as a percentagle of field height (from 10% to 90% - 0.1 to 0.9)
 - Text is centered vertically always, unless the text exceelds the formattedHeight of the field, in which case it's alight to top vertically
 - Properties are not hardcoded - they are configured as custom properties who's getter will provide a default value if empty and the setter will reformat the text as needed.
A controller stack/plugin is included to visually set custom properties.<br>
Longer term this will be converted to a script widget. <br><br>

The field can be configured as a password field by setting the custom property _passwordField_ to true. The text is by default obscured with bulletpoints and a new button appears to the right of the field that can show/hide the password text by setting the boolean custom property _obscureText_. <br>
A slight adjustable delay allows the letter typed to be viewed before quickly turning to a bullet point (set by the custom property _uBulletDelay_) <br><br>

The planceholder text by default simply disappears when typing (not just entering the field) and reappears of the text in the field is deleted. By setting the animatedPlaceholder custom property to true, this will swiftly move off to the right when the user types and if text is deleted will move back from the right. Speed disappearing and appearing is settable with customProperties _uHideDelay_ and _uShowDelay_. Note that 'move' is a blocking action so setting long delays may lead to text entry errors (the first letter typed appearing after the second), so long delays should be avoided and this is disabled if entering obscured text in passowrd field mode.

### Usage
Click or tab into the skPlaceholderField. If field is empty, the placeholder/hint text will show with color and style as set by custom properties. On typing or pasting text the colour/style changes as per custom properties. <br><br>
If setting the field text by script, send "exitField" to the field afterwards to trigger correct formatting.<br>
Reset the all properties to default with **_resetProps_** (the only public handler)<br><br>

### Custom properties
* **uPlaceholderText** -- the placeholder/hint text to show (defult = "Placeholder text")
* **uText** -- the text the field contains, used when passwordField = true
* **uNormalTextColor** -- textColor for user-entered text (default = 66,66,66)
* **uNormalTextStyle** -- textStyle for user-entered text (default = "Plain")
* **uScaleFactor** -- scales text relative to field height - defult = 0.4 (40% of the field's Height)
* **uPlaceholderTextColor** -- placeholder text's textColor (defualt = 170,170,170)
* **uPlaceholderTextStyle** -- placeholder text's textStyle (default = "Italic")
* **passwordField** -- setting this to true obscures text with bullet ponts (default = false)
* **ObscureText** -- shows/hides text if passwordField = true (defuault = true)
* **uBulletDelay** -- slight delay from 0 to 500 ms in typed letter changing to bullet,like on iOS (default 150 ms)
* **aminatedPlaceholder** - animates placeholder showing or hiding with moving in or out from the right (default = false)
* **uHideDelay** - speed at which animated placeholder text moves off to the right (default = 100 ms)
* **uShowDelay** - speed at which animated placeholder comes in from right when field text deleted (default = 200 ms)

### To use the controller stack
- either configure the field as you want and click the 'copy' icon to copy to mainstack, or
- select an existing skPlaceholderField and click the blue arrow top left. If no selected object or no skPlaceholderField selected, it defaults to the controller's prototype field

<img width="600" alt="Screenshot 2023-12-01 at 13 25 11" src="https://github.com/stam66/skPlaceholderField/assets/5677273/131f05f0-3b05-4cdd-9d3d-b6659a0315b3">
<br>
The stack is best used as a plugin. Change colors, styles, placeholder text and textScaling (proportionate to field height). To edit an existing skPlacehodlerField, select it in the IDE, open the plugin and click the arrow top left. If no skPlaceholderField selected it will edit the field included with the stack.
A 'reset' svg-button resets all properties to default; a "copy" svg-button copies the field in the controller stack to place in the developer's stack.
