---
summary: Explore app customization options in OutSystems 11 (O11) using the Theme Editor for style adjustments in Service Studio.
tags: ui customization, style guide, design systems, color schemes, branding
locale: en-us
guid: 5ee100a0-6f04-4289-8f48-5ceff38331e7
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma: https://www.figma.com/file/iBD5yo23NiW53L1zdPqGGM/Developing%20an%20Application?node-id=199:119
audience:
  - mobile developers
  - frontend developers
  - full stack developers
outsystems-tools:
  - service studio
coverage-type:
  - apply
topic:
  - customize-app-styles
---

# Customize the look of your app with Theme Editor

If your app uses a OutSystems UI Theme as a Base Theme, you can use Theme Editor to customize the overall style of your app and preview your customized app without leaving Service Studio.

To open Theme Editor, open a Screen and click the **Theme Editor...** icon in the workspace toolbar.

![Screenshot of the Theme Editor interface in Service Studio](images/theme-editor-01-ss.png "Theme Editor Interface")

## Customize default colors of Screens and UI elements

Select one of the 18 default color palettes or use a custom palette based on the main colors from an image, like the logo of your company.

Once you select a color palette, Theme Editor sets a Primary color, a Header color, and a Background color. You can change each of these default colors by choosing one of the other three suggested colors or by defining a custom color.

![Screenshot showing color customization options in Theme Editor](images/theme-editor-02-ss.png "Color Customization in Theme Editor")

Get palette from an image
:   Create a custom color palette based on the main colors of an image (.png, .jpeg). Select the logo of your company to create a color palette that reflects your brand.

Color palette
:   Choose one of the 18 default color palettes. Each one of the default palettes provides a handpicked color scheme that is the basis of the style of your app.

Primary
:   Change the color of Widgets and OutSystems UI Patterns. This is the dominant color across the screens of your app.

Background
:   Change the background color of Screens, with the exception of the default Login and Splash screens. Choosing a dark background color changes the font color to white, making sure text is readable.

Header
:   Change the background color of the Header.

## Customize default font

Select one of the six font types and change the base size of your font.

![Screenshot displaying font type and size customization in Theme Editor](images/theme-editor-03-ss.png "Font Customization in Theme Editor")

Font 
:   Change the font type used in your app.

Font Size
:   Change the base size of the font used in your app.

## Customize structure and shape

Change the general structure of your Screens and UI elements by selecting spacing, header sizes, border shape and the style of border shadow.

![Screenshot of structure and shape customization settings in Theme Editor](images/theme-editor-04-ss.png "Structure and Shape Customization in Theme Editor")

Spacing
:   Change the spacing between UI elements.

Header size
:   Change the height of the Header between 40px and 100px.

Border
:   Change the shape of the border of UI elements.

Shadow
:   Toggle a shadow effect to the border of UI elements.

## Customize the Login Screen background

Change the background of the Login screen to a solid color, to a color with a gradient or to an image. Check your style changes by opening the **Login** screen, inside the **Common** UI flow. In Mobile apps it also changes the background of the Splash screen.

![Screenshot showing options for customizing the Login Screen background in Theme Editor](images/theme-editor-05-ss.png "Login Screen Background Customization")

Background color
:   Change the color of the Login Screen background.

Background color gradient
:   Change the type of gradient applied to the color of the Login Screen background. This gradient doesn't apply to a background image.

Background image
:   Select an image to use as the background of the Login Screen. If the background image has transparent areas, those areas appear with the selected background color.

## Resetting your Theme Editor customization

To delete all the style changes created using Theme Editor, press **Reset Theme Editor**.

![Screenshot of the Reset Theme Editor button to revert style changes](images/theme-editor-06-ss.png "Reset Theme Editor Customization")
