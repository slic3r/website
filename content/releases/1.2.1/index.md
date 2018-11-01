---
title: "1.2.1"
date: 2014-11-07
---



Thanks for the massive amount of feedback about all the new features in [1.2.0](/releases/1.2.0) (see [release notes](/releases/1.2.0) for the full list)!  
This release contains many bugfixes but also some large internal refactorings, so help us test it.

#### Improvements:



*   A _G92 E0_ command is now always appended after _G11_ ([#2201](https://github.com/alexrj/Slic3r/issues/2201))



#### Changes:



*   The experimental option --g0 was removed because no firmware implements G0 in a useful way.



#### Bugfix:



*   3D preview in Linux had visualization glitches because of faulty Z depth buffer ([#2197](https://github.com/alexrj/Slic3r/issues/2197))
*   Changes in the extruder count were not propagating to the plater tab, thus making impossible to choose filament presets
*   Enabling/disabling support material didn't cause skirt to be recalculated in background
*   Changing number of object copies didn't cause skirt/brim to be recalculated in background
*   GUI options weren't enabled/disabled upon preset change
*   **3D honeycomb was not nice as intended** because truncated octahedrons were stretched vertically ([#1646](https://github.com/alexrj/Slic3r/issues/1646))
*   3D honeycomb didn't honor _Infill every 'n' layers_ ([#2194](https://github.com/alexrj/Slic3r/issues/2194))
*   3D honeycomb wasn't correctly aligned among skewed layers ([#2194](https://github.com/alexrj/Slic3r/issues/2194))
*   Concentric infill was generated with wrong collision check logic ([#2194](https://github.com/alexrj/Slic3r/issues/2194))
*   The _Spiral vase_ checkbox couldn't be disabled under some circumstances
*   Fixed regression in configuration wizard ([#2210](https://github.com/alexrj/Slic3r/issues/2210))
*   The new implementation for _avoid crossing perimeters_ was crashing under some circumstances ([#2271](https://github.com/alexrj/Slic3r/issues/2271) [#2266](https://github.com/alexrj/Slic3r/issues/2266))
*   Bridge acceleration wasn't applied anymore ([#2296](https://github.com/alexrj/Slic3r/issues/2296))
*   Bridge speed was not used for first object layer above raft ([#2301](https://github.com/alexrj/Slic3r/issues/2301))
*   Per-part settings were ignored in background processing ([#2277](https://github.com/alexrj/Slic3r/issues/2277))
*   Support material flow was not adjusted for each layer's height ([#2269](https://github.com/alexrj/Slic3r/issues/2269))
*   _Seam position = random_ didn't work with a single perimeter ([#2179](https://github.com/alexrj/Slic3r/issues/2179))
*   Worked around a Clipper issue causing random crashes in G-code export on 32-bit platforms ([#2306](https://github.com/alexrj/Slic3r/issues/2306))
*   Slider controls were rendered with zero width on Linux
*   Choice fields were not populated correctly in object and part settings



#### Known issues:



*   When Lift on retraction is enabled and Z offset contains a value that is greater than the amount of the lift, an initial move will be generated that pushes the extruder below the configured Z offset ([#2349](https://github.com/alexrj/Slic3r/issues/2349))



* * *

This is how 3D honeycomb looks like after the improvements in this release:

![](01.jpg)
