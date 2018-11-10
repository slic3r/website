---
title: "1.3.0"
date: 2018-05-10
---

A new version, finally! Despite the long time since the last versioned release, work on Slic3r has never stopped. Daily automated builds are available on this website, so this release is not entirely new for all people who have been following development.

This release was curated by Joseph Lenox (Lordofhyphens).

Please [join the discussion](https://github.com/slic3r/Slic3r/issues) on GitHub and report issues and ideas.

#### New features:

- **Controller**: print via USB directly from Slic3r! Spool your prints in a queue and print to multiple printers at the same time.
- **3MF** format read/write ([#4046](https://github.com/slic3r/Slic3r/pull/4046))
- Experimental support for **SLA/DLP** machines (USB/video output)
- **Bonjour** detection of Octoprint instances
- Custom G-code now can have some **logic and math**, see [the manual](https://manual.slic3r.org/advanced/conditional-gcode) ([#3390](https://github.com/slic3r/Slic3r/issues/3390))
- **Solarized color scheme** now available. ([#4322](https://github.com/slic3r/Slic3r/pull/4322))
- Support for long retracts (Marlin/Repetier)
- **New infill patterns**: gyroid, cubic, stars Infill pattern ([#3666](https://github.com/slic3r/Slic3r/issues/3666))
- **Adaptive Slicing** (let Slic3r vary the layer thickness according to the slopes in the model) ([#1386](https://github.com/slic3r/Slic3r/pull/1386))
- You can now nudge/move models with the keyboard arrows in the 2D plater. ([#4102](https://github.com/slic3r/Slic3r/issues/4102))
- **Generic modifier meshes** -- the powerful and well-known modifier meshes, already available in Slic3r, can be now created and positioned directly from the visual interface of Slic3r without the need for an external CAD program! ([#3590](https://github.com/slic3r/Slic3r/pull/3590))
- Option to force M190/M109 for extruder and bed heater
- You can turn off automatic centering and alignment in Z.
- Optimistic **time estimation** for prints. ([#3747](https://github.com/slic3r/Slic3r/pull/3747))
- Slic3r will now tell you **cost of material** used after exporting Gcode ([°3669](https://github.com/slic3r/Slic3r/pull/3669))
- Linux AppImage and tarball builds.
- **Undo/Redo** for rotate, mirror, split, cut ([#3265](https://github.com/slic3r/Slic3r/issues/3265))
- Custom G-code can now be entered for between objects in sequential object mode.
- Reprapfirmware/Duet print server support ([#4028](https://github.com/slic3r/Slic3r/pull/4028))
- Custom G-code can be set for filament profiles. Its start G-code is placed after printer start G-code and its end G-code is placed before printer end G-code. ([#3309](https://github.com/slic3r/Slic3r/issues/3309))
- Slic3r now can limit your print speed to a given **volumetric** amount.
- **Autospeed**: Slic3r manages the print to maintain **constant flow rate**. Should result in fewer needed retractions.
- Support can now be restricted to only areas that touch the build plate.
- Support material generation now allows for % of perimeter width for overhang. 
- Average Print speed in mm^3/s is now output in gcode.
- "Move to bed center" option in object menu.
- Experimental option z_steps_per_mm to have slic3r auto-align layer height to integer Z steps. ([#1827](https://github.com/slic3r/Slic3r/issues/1827))
- **Top and bottom fill pattern** can now be specified separately.
- Brim can now be specified for inside holes.
- Seams can now be specified in "rear" position.
- Detect thin walls can produce variable-thickness perimeters now in some situations.
- **Brim connections**
- Bed temperature can now be specified at 0.
- New option to tell Slic3r if your printer has a heatbed (and whether or not to bother putting bed heat gcode in).
- **Smoothieware** G-code flavor (primarily affects retraction) ([#3373](https://github.com/slic3r/Slic3r/pull/3373))
- You can now specify some overrides for Printer settings from Filament. ([#3770](https://github.com/slic3r/Slic3r/pull/3770))
- The pattern angle for rafts is now configurable.
- Doxygen-generated documentation for **libslic3r**.
- Print and filament profiles can be marked as compatible with specific printer profiles. ([#3770](https://github.com/slic3r/Slic3r/pull/3770))

#### Improvements

- New build/packaging system for Windows
- New build/packaging system for OSX
- Configuration options shortcuts are available in the main plater ([#3912](https://github.com/slic3r/Slic3r/pull/3912))
- More code was ported to C++, including infill, bridge detection, cooling, GCodeReader and SpiralVase
- Antialiasing for the plater. ([#3343](https://github.com/slic3r/Slic3r/pull/3343))
- Switching to the 3D Preview now starts a slice if background processing is off.
- Gap fill is much, much smarter now.
- Rectilinear fill has been improved.
- External perimeters are not slowed down even more if possible.
- Lots of things are done in parallel in libslic3r.
- Speed improvements in some cases.
- If auto-arrange fails, ignore bed shape.
- Speed settings now default to "auto" instead of "0" (same behavior, but more clear)
- small_perimeter_speed is now ignored for overhangs.
- Slic3r warns you when objects are outside of the print bed area.
- UI: You can zoom without the mousewheel now. ([#3233](https://github.com/slic3r/Slic3r/issues/3233))
- MotionPlanner should be much smarter now.
- Mac Retina displays are now supported. ([#2888](https://github.com/slic3r/Slic3r/issues/2888))
- Numerous C++11 related code cleanup.
- Bridge detection is improved

#### Changes

- Simple/Expert Mode is no more, we are all experts now.

#### Bugfix

- External perimeters are now chosen to be 1.1*(nozzle width) when using auto.
- 3D Honeycomb Infill switches
- Brims are now nudged slightly closer to models. 
- DLP SVG export works now. ([#4311](https://github.com/slic3r/Slic3r/issues/4311))
- Setting acceleration for reprapfirmware works now.
- STL imports in big-endian architectures works now. ([#4143](https://github.com/slic3r/Slic3r/pull/4143))
- Several crash bugs have been fixed, especially around custom gcode handling.
- Bridging should be improved when there are narrow gaps under bridge anchors.
- Scaling objects with multiple copies in the plater should now be consistent.
- Fixes to background processing. 
- flowrate.pl now handles negative coordinates.
- Windows build shouldn't hang forever on a C++ Exception
- Fewer copies are made when multi-object AMF files are converted to a multi-part onject
- solid_infill_below_area is ignored when fill_density is 100%
- Title labels for the layer height editor aren't cut off.
- Correct extruder order should be used now if more than 10 extruders are used. ([#3235](https://github.com/slic3r/Slic3r/issues/3235))
- If there is a raft, print brims using the support material extruder.
- Auto width now does not assume your hotend can produce infinitely wide traces.
- Mousewheel zoom is now consistent.
- Diagonal gaps (due to slopes) should now properly place extra perimeters.
- Trimmed down the axis lengths on the plater.
- Temperature standby works now on Makerbot/Sailfish firmware
- Nonexistant config options should not cause Slic3r to crash (instead it just ignores them)
- Variable-width perimeters can't cause negative extrusion.
- Combined infill (infill-every-n-layers) now correctly draws thicker infill than perimeters.
