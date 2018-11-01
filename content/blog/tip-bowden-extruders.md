---
title: "Tip: printing with Bowden extruders"
date: 2013-03-30
author: Alessandro Ranellucci
---

I learned that the main goal with Bowden extruders is to reduce the number of retractions in a print. Even fast and long retractions often leave blobs, so we have to fight those.

Slic3r 0.9.9 contains a number of features for that purpose. Here are the recommended settings:

*   **avoid crossing perimeters** (Print Settings): on
*   **only retract when crossing perimeters** (Print Settings): on
*   **retract on layer change** (Printer Settings): off

The first setting will also cause Slic3r to finish each island completely before moving to the next one, reducing the need for retraction.

Slic3r 0.9.10 introduced a new useful setting to avoid blobs upon retraction:

*   **wipe** (Printer Settings): on

These settings should help you getting good prints with your Rostock, RepRapPro, Ultimaker or whatever.

Thanks to [SeeMeCNC](http://www.seemecnc.com/) and [Wasproject](http://www.wasproject.it/) who donated printers to test these features.
