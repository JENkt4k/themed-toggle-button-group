# ThemedToggleButtonGroup
![CI](https://github.com/Bryanx/themed-toggle-button-group/workflows/CI/badge.svg)
![API](https://img.shields.io/static/v1?label=API&message=14%2B&color=blue)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) 
![Download](https://api.bintray.com/packages/bryanx/themed-toggle-button-group/nl.bryanderidder.themed-toggle-button-group/images/download.svg) 

Customisable toggle buttons inside a [FlexboxLayout](https://github.com/google/flexbox-layout).

ThemedToggleButtonGroup is a highly modular lightweight toggle button library for Android. It can be configured for single selection or multi selection. For multi selection the minimum/maximum amount of buttons that are required/enabled can be specified. Icon's can be added. Selection includes a fun press and circular reveal animation.

The main class [ThemedToggleButtonGroup.kt](https://github.com/Bryanx/themed-toggle-button-group/blob/master/library/src/main/java/nl/bryanderidder/themedtogglebuttongroup/ThemedToggleButtonGroup.kt) extends Google's [FlexboxLayout](https://github.com/google/flexbox-layout). Allowing you to use styling similar to [CSS Flexbox](https://www.w3schools.com/css/css3_flexbox.asp) for the button's inside the toggle group.

## Installation
Add these dependencies in your app's `build.gradle` file:
```groovy
dependencies {
  implementation 'nl.bryanderidder:themed-toggle-button-group:1.1.0'
  implementation 'com.google.android:flexbox:2.0.1'
}
```

## Single selection
![demo](https://raw.githubusercontent.com/Bryanx/themed-toggle-button-group/master/demo-toggle-cards/assets/basic.gif)
```xml
<nl.bryanderidder.themedtogglebuttongroup.ThemedToggleButtonGroup
    android:id="@+id/time"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:justifyContent="center"> <!-- this attribute is from the underlying FlexboxLayout -->

      <nl.bryanderidder.themedtogglebuttongroup.ThemedButton
          android:id="@+id/btn1"
          android:layout_width="wrap_content"
          android:layout_height="38dp"
          app:toggle_text="5:30PM" />

      <nl.bryanderidder.themedtogglebuttongroup.ThemedButton
          android:id="@+id/btn2"
          android:layout_width="wrap_content"
          android:layout_height="38dp"
          app:toggle_text="7:30PM" />

      <nl.bryanderidder.themedtogglebuttongroup.ThemedButton
          android:id="@+id/btn3"
          android:layout_width="wrap_content"
          android:layout_height="38dp"
          app:toggle_text="8:00PM" />

</nl.bryanderidder.themedtogglebuttongroup.ThemedToggleButtonGroup>
```

## Multiple selection
![demo](https://raw.githubusercontent.com/Bryanx/themed-toggle-button-group/master/demo-toggle-cards/assets/labels.gif) \
Declare how many buttons **may** be selected with `toggle_selectableAmount`. \
Declare how many buttons **must** be selected with `toggle_requiredAmount`.
```xml
<nl.bryanderidder.themedtogglebuttongroup.ThemedToggleButtonGroup
    android:id="@+id/tags"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:toggle_selectableAmount="3"
    app:justifyContent="space_between"
    app:flexWrap="wrap">

    <nl.bryanderidder.themedtogglebuttongroup.ThemedButton
        android:id="@+id/tag1"
        android:layout_width="wrap_content"
        android:layout_height="30dp"
        android:layout_margin="3dp"
        app:toggle_text="social" />

    <nl.bryanderidder.themedtogglebuttongroup.ThemedButton
        android:id="@+id/tag2"
        android:layout_width="wrap_content"
        android:layout_height="30dp"
        android:layout_margin="3dp"
        app:toggle_text="music" />
  
    <!-- ... -->
  
  </nl.bryanderidder.themedtogglebuttongroup.ThemedToggleButtonGroup>
```

## Icon selection
![demo](https://raw.githubusercontent.com/Bryanx/themed-toggle-button-group/master/demo-toggle-cards/assets/icontoggle.gif) \
It is possible to add icons to the buttons and show a different icon when the button is selected. This example also shows how to add borders.
```xml
<nl.bryanderidder.themedtogglebuttongroup.ThemedToggleButtonGroup
    android:id="@+id/toggleGroup"
    android:layout_width="match_parent"
    android:layout_height="80dp"
    app:alignItems="center"
    app:justifyContent="center"
    app:toggle_requiredAmount="0"
    app:toggle_selectableAmount="3">

    <nl.bryanderidder.themedtogglebuttongroup.ThemedButton
        android:id="@+id/btnMic"
        android:layout_width="70dp"
        android:layout_height="70dp"
        app:toggle_btnCornerRadius="50dp"
        app:toggle_borderWidth="5dp"
        app:toggle_borderColor="#C6C6C6"
        app:toggle_selectedBorderColor="#5e6fed"
        app:toggle_icon="@drawable/ic_mic_off_black_24dp"
        app:toggle_iconColor="#C6C6C6"
        app:toggle_selectedIcon="@drawable/ic_mic_black_24dp"
        app:toggle_backgroundColor="@android:color/white"
        app:toggle_iconPadding="18dp" />

    <!-- ... -->

</nl.bryanderidder.themedtogglebuttongroup.ThemedToggleButtonGroup>
```

## Text + icon selection
![demo](https://raw.githubusercontent.com/Bryanx/themed-toggle-button-group/master/demo-toggle-cards/assets/togg.gif) \
A demo for this example can be found here: [demo-toggle-cards](https://github.com/Bryanx/themed-toggle-button-group/tree/master/demo-toggle-cards). You need to use SVG icons to allow the color to be altered. 
```xml
<nl.bryanderidder.themedtogglebuttongroup.ThemedToggleButtonGroup
    android:id="@+id/cards"
    android:layout_width="match_parent"
    android:layout_height="155dp"
    android:layout_marginHorizontal="32dp"
    app:alignItems="center">

    <nl.bryanderidder.themedtogglebuttongroup.ThemedButton
        android:id="@+id/card1"
        android:layout_width="0dp"
        android:layout_height="145dp"
        app:layout_flexGrow="1"
        app:toggle_selectedTextColor="@android:color/white"
        app:toggle_selectedBackgroundColor="#5e6fed"
        app:toggle_icon="@drawable/replace_with_svg_icon"
        app:toggle_iconGravity="top|center"
        app:toggle_iconPaddingTop="15dp"
        app:toggle_iconPaddingHorizontal="15dp"
        app:toggle_textPaddingBottom="20dp"
        app:toggle_text="Multiple choice"
        app:toggle_textGravity="bottom|center" />

    <!-- ... -->

</nl.bryanderidder.themedtogglebuttongroup.ThemedToggleButtonGroup>
```

# Customization
These lists include all custom attributes from this library. Please take a look [FlexboxLayout](https://github.com/google/flexbox-layout) to see all custom attributes that can also be applied to these Views.
## ThemedToggleButtonGroup custom attributes
Attribute | Default value | Description
--- | --- | ---
`app:toggle_selectableAmount` | 1 | The amount of buttons that are allowed to be selected. If the user tries to select more buttons, the button that was last selected will be deselected.
`app:toggle_requiredAmount` | 1 | The amount of buttons that are required to be selected. If the user tries to deselect a button below the required amount, the selection is blocked. You can programmatically specify which buttons should be selected initially by setting `ThemedButton.isSelected`. Otherwise a random button will be selected initially.

## ThemedButton custom attributes
![Color_customisation](https://github.com/Bryanx/themed-toggle-button-group/blob/master/demo-toggle-cards/assets/dark.gif?raw=true) \
You can fully customise colors, positioning, font size, etc. with these attributes.

Attribute | Default value | Description
--- | --- | ---
`app:toggle_text` | Empty string | Text of the button.
`app:toggle_selectedText` | `app:toggle_text` | Text when the button is selected. If not present the text of `toggle_text` is used.
`app:toggle_textSize` | 15sp | Size of the text in the button.
`app:toggle_textAlignment` | center | Alignment of the text.
`app:toggle_backgroundColor` | ![#EBEBEB](https://placehold.it/15/EBEBEB/000000?text=+) `#EBEBEB` | Background color when the button is not selected.
`app:toggle_selectedBackgroundColor` | ![#5E6FED](https://placehold.it/15/5E6FED/000000?text=+) `#5E6FED` | Background color when the button is selected.
`app:toggle_textColor` | ![#5E5E5E](https://placehold.it/15/5E5E5E/000000?text=+) `#5E5E5E` | Text color when the button is not selected. This also sets the color of the icon if it is not set.
`app:toggle_selectedTextColor` | ![#FFFFFF](https://placehold.it/15/FFFFFF/000000?text=+) `#FFFFFF` |  Text color when the button is selected. This also sets the color of the selected icon if it is not set.
`app:toggle_icon` | null | Optional icon inside the button.
`app:toggle_selectedIcon` | `app:toggle_icon` | Icon when the button is selected. By default the icon of `app:toggle_icon` is used.
`app:toggle_iconColor` | ![#5E5E5E](https://placehold.it/15/5E5E5E/000000?text=+) `#5E5E5E` | Color of the icon when the button is not selected.
`app:toggle_btnCornerRadius` | 21dp | Curve amount of the button's corners.
`app:toggle_circularCornerRadius` | false | This makes the button circular. This overrides the corner radius.
`app:toggle_borderWidth` | 0dp | The width of the border.
`app:toggle_selectedBorderWidth` | `app:toggle_borderWidth` | The width of the border when the button is selected. By default the width of `toggle_borderWidth` is used.
`app:toggle_borderColor` | ![#5E5E5E](https://placehold.it/15/5E5E5E/000000?text=+) `#5E5E5E` | The color of the border.
`app:toggle_selectedBorderColor` | `app:toggle_borderColor` | The color of the border when the button is selected.. By default the color of `app:toggle_borderColor` is used.
`app:toggle_padding` | 0dp | Padding of the button.
`app:toggle_textPadding` | 14dp (horizontal) | Padding of the text.
`app:toggle_iconPadding` | 0dp | Padding of the icon.
`app:toggle_iconGravity` | top\|start | Position of the icon.
`app:toggle_textGravity` | top\|start | Position of the text.

## Contributing
You can contributing by [opening an issue](https://github.com/Bryanx/themed-toggle-button-group/issues) or forking this repository and creating a pull request.

## License
[License for this library](https://github.com/Bryanx/themed-toggle-button-group/blob/master/LICENSE)\
[License for FlexboxLayout](https://github.com/google/flexbox-layout/blob/master/LICENSE)

