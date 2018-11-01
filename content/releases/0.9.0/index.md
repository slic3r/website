---
title: "0.9.0"
date: 2012-08-07
---




Exciting new release, with many improvements and new features including **support for multiple extruders** and a redesigned **graphical interface**.

This release and all recent work about support material and multiple extruders is sponsored by [**LulzBot**](http://www.lulzbot.com/). Check out their products!

Also thanks to Henrik Brix Andersen who worked on creating the wizard and improving the user experience, and to Mark Hindness who is focusing on speed and memory optimizations. New features are being researched on, stay tuned for next releases!

![](01.jpg)

#### New features:

*   new **graphical interface**, with **multiple presets** and automatic**loading of last settings**
*   support for **multiple extruders**
*   **wizard** for new users (developed by Henrik Brix Andersen)
*   new option to set a **different speed for external perimeters**
*   new option to set **extrusion width for support material**

#### Improvements:

*   **better flow math** to get more continuous surfaces and better dimensional accuracy (note: you might need to revert your extrusion multiplier to 1 if you had set it to a lower value)
*   fill the gaps during normal infill to **avoid extra travel**
*   **faster** thin walls processing
*   many **speed and memory optimizations** (contributed by Mark Hindness)
*   removed the confirmation modal dialogs, use Growl/DBus for notifications when available

#### Changes:

*   don't reset E when the Makerbot flavor is selected
*   allow scaling factor to be at least 2540 to allow the conversion of inch models
*   First layer extrusion width is set to 200% over layer height by default

#### Bugfixes:

*   fixed regression causing objects to be 0.1mm larger
*   flow settings were almost ignored
*   brim was extruded multiple times when sequential printing was enabled
*   brim did not take support material into account
*   some infill was still generated even when density was set to zero










