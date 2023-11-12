# skPlaceholderField
LiveCode Text field with configurable placeholder text

### Custom properties
All properties have getter and setters - getters provide default values if empty

* **uPlaceHolderText** -- the text to display when field is empty, disappears on entering field and only reappears if field is empty on exit
* **uScaleFactor** -- scale textsize from 10% to 90% (0.1 - 0.9) of the height of the field. Auto-resizes and centers vertically on field resize. If formatted textheight exceeds the height of the field, it is aligned to top instead
* **Colors**
  * _uTextForLightBackground_ -- text color to apply to normal text if background of field is light
  * _uTextForDarkBackground_ --  text color to apply to normal text if background of field is dark
  * _uPlaceholderTextForLightBackground_ -- placeholder text color to apply to normal text if background of field is light
  * _uPlaceholderTextForDarkBackground_ -- placeholder text color to apply to normal text if background of field is dark
  * _uBackgroundColor_ -- field's backgroundColor
  * _uBorderColor_ -- field's borderColor (note: if 3D is true, the borderwidth of 2 will obscure color as it emulates system defaults - change borderwidth or set 3D to false to see color borders with width of 2)
* **uBorderWidth** -- border width
* **uPlaceholderTextStyle** -- text style for placeholder text (italic, bold or plain)
* **uNormalTextStyle** -- text style for normal text (plain, bold or italic)

### To use the controller stack
- either configure the field as you want and click the 'copy' icon to copy to mainstack, or
- select an existing skPlaceholderField and click the blue arrow top left. If no selected object or no skPlaceholderField found, it defaults to the controller's prototype field
