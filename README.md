# skPlaceholderField
LiveCode Text group-based widget providing a field with configurable placeholder text.  
This is a group with 3 fields that enables placeholder text (hiding instantly or with animation) and password field functions.  
Current version: 1.4 - [Change log](changelog.md)    
<img width="699" alt="Screenshot 2023-12-02 at 18 43 58" src="https://github.com/stam66/skPlaceholderField/assets/5677273/c45128c2-b2cc-4c6a-b669-b3e06c61f88a">

**Features**
 - If field is empty, will show a hint/placeholder text with an indicative text style (defult = italic, light gray)
 - If user has pasted or entered text, or if text set by script, will show the text with indicative text style (default = plain text, near-black)
 - The field will toggle visiblity of placeholder text while modfiying text, as needed
 - Textsize is determined by field height - and configurable as a percentagle of field height (from 10% to 90% - 0.1 to 0.9)
 - Text is centered vertically always, unless the text exceelds the formattedHeight of the field, in which case it's alight to top vertically
 - Properties are not hardcoded - they are configured as custom properties who's getter will provide a default value if empty and the setter will reformat the text as needed.
A controller stack/plugin is included to visually set custom properties.<br>
Longer term this will be converted to a script widget.  

The field can be configured as a password field by setting the custom property _passwordField_ to true. The text is by default obscured with bulletpoints and a new button appears to the right of the field that can show/hide the password text by setting the boolean custom property _obscureText_.  
A slight adjustable delay allows the letter typed to be viewed before quickly turning to a bullet point (set by the custom property _uBulletDelay_)  

The planceholder text by default animates by being pushed to the right when typing (not just entering the field) and moves back in from the right if the text in the field is deleted. By setting the animatedPlaceholder custom property to false, the placeholderText will simply disappear/appear if typing in field or text deleted respectively. The speed of animation can be set in the controller stack or simply by setting the custom property _uDuration_.

### Usage
Click or tab into the skPlaceholderField. If field is empty, the placeholder/hint text will show with color and style as set by custom properties. On typing or pasting text the colour/style changes as per custom properties. <br><br>
If setting the field text by script, send "exitField" to the field afterwards to trigger correct formatting.  
Reset the all properties to default with **_resetProps_** (the only public handler)<br><br>

### Custom properties
* **skPlaceholderFieldGroup** a custom property that always returns true and identifies the group as an skPlaceholderFieldGroup
* **uPlaceholderText** -- the placeholder/hint text to show (defult = "Placeholder text")
* **uText** -- the text the user types in, read-only
* **uNormalTextColor** -- textColor for user-entered text (default = 66,66,66)
* **uNormalTextStyle** -- textStyle for user-entered text (default = "Plain")
* **uScaleFactor** -- scales text relative to field height - defult = 0.4 (40% of the field's Height)
* **uPlaceholderTextColor** -- placeholder text's textColor (defualt = 170,170,170)
* **uPlaceholderTextStyle** -- placeholder text's textStyle (default = "Italic")
* **passwordField** -- setting this to true obscures text with bullet ponts (default = false)
* **ObscureText** -- shows/hides text if passwordField = true (defuault = true)
* **uBulletDelay** -- slight delay from 0 to 500 ms in typed letter changing to bullet,like on iOS (default 250 ms)
* **aminatedPlaceholder** - animates placeholder showing or hiding with moving in or out from the right (default = false)
* **uDuration** - speed at which animated placeholder text moves in or out from the right (default = 250 ms)

### The controller stack
- Plugin for creating or modifying skPlaceholderFieldGroup controls - drop into Plugins folder and restart IDE to install
- If a topStack is present, the copy button will simply place the group on the current card of the topStack. To copy instead, option-click. If no topStack present (ie no normal windows) it will copy the group control to the clipboard instead.
- select an existing skPlaceholderField to edit it's properties within the controller stack.
  - When an placeHolderGroup is selected, it's short name appears top left and the long name is set to the tooltip of the short name.
  - To reset the properties of a selected placeholderGroup, click the red reset button.
- if no placeholderGroups selected, the controls are inaccessible.
<img width="393" alt="Screenshot 2023-12-11 at 15 14 26" src="https://github.com/stam66/skPlaceholderField/assets/5677273/140d91c2-de77-4436-a553-2405c2dd3391">


