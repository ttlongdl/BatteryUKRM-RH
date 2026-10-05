# BatteryUKRM-RH

BatteryUKRM-RH is the **Roothide** build of BatteryUKRM. It preserves the native Battery Health experience on supported replaced-battery configurations and adds the real battery cycle count.

> **Status:** Roothide port. The original BatteryUKRM 1.0.2 behavior is preserved, but this Roothide build still needs broader testing on real Roothide devices.

## 1.0.2

- Ported the package to the Roothide Theos scheme.
- Preserves the 1.0.1 repair-warning and genuine-battery behavior.
- Keeps the native Maximum Capacity value supplied by iOS.
- Adds the real Battery Cycle Count read from AppleSmartBattery.
- Adds localized Vietnamese/English Cycle Count text.
- Suppresses the Settings repair badge.

## Source / implementation

The tweak logic is intentionally kept aligned with the original BatteryUKRM 1.0.2. BatteryUKRM-RH does not access jailbreak files or hard-code `/var/jb`; its system-framework and runtime-hook logic therefore does not require Roothide path translation.

## Original tested configuration

The original rootless BatteryUKRM 1.0.2 was tested successfully on:

- **Device:** iPhone 12 Pro
- **iOS:** 17.0
- **Jailbreak:** rootless
- **Battery:** replaced with an Apple battery
- **Battery BMS/flex:** original battery BMS/flex was **not transplanted** to the replacement battery

The Roothide package should be treated as **testing** until confirmed on real Roothide configurations.

### Display / screen replacement

BatteryUKRM-RH is currently focused on battery-related repair information. Display/screen replacement behavior has **not been tested**, and no claim is made that the tweak hides or modifies replaced-display information.

The existing repair/Unknown Part hooks may potentially affect other repair warnings, but this has not been verified.

Package: `com.ttlongdl.batteryukrm-rh`
