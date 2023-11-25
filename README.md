# WRCG Throttle Mod

This mod fixes the auto-clutch, and hopefully fixes the weird throttle response.

**NOTE:** Not all cars have been fixed, see list below.

Pull requests welcome.

## How to install

1. First [Enable Modding](https://github.com/Avery3R/WRCGModTools#how-do-i-enable-mods-in-my-wrcg-install)
2. Then either clone, or [Download](https://github.com/Avery3R/WRCGThrottleMod/archive/refs/heads/master.zip) a copy of this repository.
3. Copy the `Common` folder to your WRCG install, overwriting all file and folder conflicts.

## How to help expand this mod

Grab the cheat table from the modding tools repository and use cheat engine to enable the WrcVehicleSDK debug visualizations, they will be useful.

Please test the cars before you submit a pull request, just in case something weird and unexpected happens.

### How do I fix the auto-clutch on a car that hasn't been fixed yet?

1. Locate the `Auto Gearbox Down ratios` propery.
2. Add a `0` after the first element in the list.

For example, take:

`<prop name="Auto Gearbox Down ratios" value="0.5,0.5,0.45,0.45,0.5,0.5" />`

and turn it into

`<prop name="Auto Gearbox Down ratios" value="0.5,0,0.5,0.45,0.45,0.5,0.5" />`

### How do I fix the throttle response?

This one is more tricky, I don't fully understand it yet but this is my best guess so far. Replace the `Gearbox Accel  curve` and `Gearbox Clutch curve` properties with:

```xml
<prop name="Gearbox Accel  curve" value="-3.40282e+38,-3.40282e+38,5,0.0000;1.0000,0.0000;1.0000,0.0704;1.0000,0.7746;1.0000,1.0000;1.0000" />
<prop name="Gearbox Clutch curve" value="-3.40282e+38,-3.40282e+38,5,0.0000;0.0000,0.2251;0.4292,0.5047;0.9898,0.7573;0.4393,1.0000;0.0000" />
```

These values were taken from WRC10, I have no idea wtf they do I'm not a car person.

## Which cars are fixed? / Changelog

**v1.0:**

* JWRC
* WRC1 Ford Puma