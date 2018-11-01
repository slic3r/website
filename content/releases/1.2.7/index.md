---
title: "1.2.7"
date: 2015-05-23
---

More bugfixes. We want to make 1.2.x stable soon. Dear Slic3r community: thank you for your support, testing, reports and love!

For the whole list of changes and new features see the release notes for [1.2.0](/releases/1.2.0), [1.2.1](/releases/1.2.1), [1.2.2](/releases/1.2.2), [1.2.3](/releases/1.2.3), [1.2.5](/releases/1.2.5) and [1.2.6](/releases/1.2.6).

#### New features:

*   Added support for **Machinekit** G-code flavor.
*   **Pan & zoom** with mouse in the 2D Layers preview.

#### Improvements:



*   Load files into GUI when supplied from command line along with the --gui switch ([#2644](https://github.com/alexrj/Slic3r/issues/2644)).
*   **Better gap fill** ([#2560](https://github.com/alexrj/Slic3r/issues/2560)).
*   Simpler and more robust implementation of _**Extra perimeters**_, which are now added only when at least 30% of the upper perimeters loops will benefit from them ([#2395](https://github.com/alexrj/Slic3r/issues/2395), [#2664](https://github.com/alexrj/Slic3r/issues/2664), [#2610](https://github.com/alexrj/Slic3r/issues/2610)).
*   3D views are now synced ([#2628](https://github.com/alexrj/Slic3r/issues/2628)).
*   Better and more robust implementation of _**Infill only where needed**_.
*   When using raft, _First layer height_ is now validated only with nozzle diameter of support material extruder thus allowing the usage of a **larger nozzle** for it ([#2701](https://github.com/alexrj/Slic3r/issues/2701), [#2722](https://github.com/alexrj/Slic3r/issues/2722)).
*   Support material layer height is used for raft layers instead of object layer height ([#2723](https://github.com/alexrj/Slic3r/issues/2723)).
*   A **[scale] placeholder** is now available for filenames and custom G-code ([#2791](https://github.com/alexrj/Slic3r/issues/2791)).
*   Better and more robust medial axis implementation for **thin wall handling** ([#2800](https://github.com/alexrj/Slic3r/issues/2800), [#2829](https://github.com/alexrj/Slic3r/issues/2829)).
*   **Brim and skirt** are now rendered in the 3D toolpaths preview ([#2649](https://github.com/alexrj/Slic3r/issues/2649)).
*   Speed improvements to _**Avoid crossing perimeters**_ ([#2777](https://github.com/alexrj/Slic3r/issues/2777)).



#### Changes:

*   The [layer_num] placeholder now uses a single continuous series also when using interlaced support material layers ([#2634](https://github.com/alexrj/Slic3r/issues/2634)).

#### Bugfix:



*   Fixed crash occurring on version check on Linux ([#2641](https://github.com/alexrj/Slic3r/issues/2641)).
*   Fixed buttons size on Linux ([#2642](https://github.com/alexrj/Slic3r/issues/2642)).
*   Don't use bridge speed for first object layer above raft when support_material_contact_distance > 0 ([#2656](https://github.com/alexrj/Slic3r/issues/2656)).
*   Fixed upstream issue causing some infill paths not being clipped correctly to object contours ([#2448](https://github.com/alexrj/Slic3r/issues/2448)).
*   Fixed regression causing [input_filename] and [input_filename_base] not to be available anymore in custom G-code ([#1507](https://github.com/alexrj/Slic3r/issues/1507)).
*   Background processing was not restarted when the previous one failed because of a config validation error ([#2633](https://github.com/alexrj/Slic3r/issues/2633)).
*   Fixed support material not always honoring the custom first layer extrusion width ([#2662](https://github.com/alexrj/Slic3r/issues/2662)).
*   Fixed upstream issue causing shortcutting perimeters ([#2639](https://github.com/alexrj/Slic3r/issues/2639)).
*   Fixed infill/perimeters overlap setting not correctly working in some edge cases ([#2632](https://github.com/alexrj/Slic3r/issues/2632)).
*   Fixed first layer support material spacing ([#2662](https://github.com/alexrj/Slic3r/issues/2662)).
*   Fixed too many skirt layers being printed when using tall skirts and support material ([#2695](https://github.com/alexrj/Slic3r/issues/2695)).
*   Fixed regression causing failures in bridge direction detection ([#2636](https://github.com/alexrj/Slic3r/issues/2636)).
*   Fixed Z clipping in OpenGL 3D rendering.
*   Fixed error in executability check for post-processing scripts on Windows ([#2616](https://github.com/alexrj/Slic3r/issues/2616)).
*   Fixed temperature not being set correctly when using sequential printing ([#2702](https://github.com/alexrj/Slic3r/issues/2702)).
*   Fixed potential collision when using wipe and sequential printing ([#2691](https://github.com/alexrj/Slic3r/issues/2691)).
*   Fixed problems with non-ASCII filenames and directory paths on Windows ([#2710](https://github.com/alexrj/Slic3r/issues/2710)).
*   Fixed layers view not being resized when inactive ([#2708](https://github.com/alexrj/Slic3r/issues/2608)).
*   Fixed order of concentric infill loops.
*   Fixed object Z alignment after cut + rotate ([#2724](https://github.com/alexrj/Slic3r/issues/2724)).
*   Fixed superflous and potentially harmful travel moves when moving between objects with sequential printing ([#2691](https://github.com/alexrj/Slic3r/issues/2691)).
*   Fixed dirty filament options being ignored when using multiple extruders ([#2740](https://github.com/alexrj/Slic3r/issues/2740), patch by @markwal).
*   Fixed GUI issue in numeric comboboxes ([#2752](https://github.com/alexrj/Slic3r/issues/2752), patch by @markwal)
*   Fixed the Export G-code button not being re-enabled after a cancelled export job ([#2754](https://github.com/alexrj/Slic3r/issues/2754)).
*   Fixed the object parts editor being opened in an invalid status until user clicked on an item in the parts tree ([#2762](https://github.com/alexrj/Slic3r/issues/2762)).
*   Fixed regression causing spiral vase logic not to be disabled on layers with multiple loops ([#2761](https://github.com/alexrj/Slic3r/issues/2761)).
*   Fixed Resolution option not triggering automatic reslicing ([#2795](https://github.com/alexrj/Slic3r/issues/2795)).
*   Fixed wrong object positions caused by splitting a rotated object ([#2772](https://github.com/alexrj/Slic3r/issues/2772)).
*   Fixed crash on Windows when deleting the first object part ([#2774](https://github.com/alexrj/Slic3r/issues/2774)).
*   Fixed double or overlapping gap fill in some cases ([#2836](https://github.com/alexrj/Slic3r/issues/2836), [#2474](https://github.com/alexrj/Slic3r/issues/2474)).
*   Fixed regression causing skirt not to be exported in G-code when Raft layers were used ([#2843](https://github.com/alexrj/Slic3r/issues/2843)).
*   Added workaround for upstream wxWidgets bug causing numeric controls to revert their value on OS X ([#2612](https://github.com/alexrj/Slic3r/issues/2612)).



* * *

![](01.jpg)

![](02.jpg)
