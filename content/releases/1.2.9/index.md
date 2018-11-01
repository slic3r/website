---
title: "1.2.9"
date: 2015-06-16
stable: true
---

Finally a new stable release!

Dear Slic3r community: thank you for your support, testing, reports and love!

For the whole list of changes and new features see [this comprehensive blog post](/blog/new-stable-1.2.9/).

#### Improvements:



*   Limit bridge over sparse infill to areas that can absorb such extrudate in case of thin layers ([#2899](https://github.com/alexrj/Slic3r/issues/2899))
*   Adjustments to the thin wall logic for preventing small artifacts ([#2910](https://github.com/alexrj/Slic3r/issues/2910))



#### Changes:

*   The math applied to the _Infill Overlap_ option was slightly changed

#### Bugfix:



*   Fixed more situations where filenames and presets with non-ASCII characters were not handled correctly (thanks [Josef Prusa](http://www.prusa3d.com/))
*   Fixed regression causing some rare STL files not to be parsed correctly ([#2914](https://github.com/alexrj/Slic3r/issues/2914))

* * *

![](01.jpg)

![](02.jpg)
