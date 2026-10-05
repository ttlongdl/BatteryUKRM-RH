# BatteryUKRM-RH

BatteryUKRM-RH is the **Roothide build** of BatteryUKRM. Version 1.1.0 brings the same modular Battery Health controls and preference UI from the rootless release to Roothide.

Package: `com.ttlongdl.batteryukrm-rh`

## BatteryUKRM-RH 1.1.0

BatteryUKRM-RH now provides three independent modules:

- **Hide Battery Repair Warnings** — hides battery-related “Unknown Part / Repair Needed” information in Settings and About and suppresses the Settings repair badge.
- **Restore Maximum Capacity** — restores the native Maximum Capacity / Battery Health state on supported replacement batteries.
- **Show Cycle Count** — reads the real `CycleCount` value from `AppleSmartBattery` and displays it in Battery Health & Charging.

All three modules are **enabled by default**. A respring is required after changing switches.

### New in 1.1.0

- Ported the modular BatteryUKRM 1.1.0 hook architecture to Roothide.
- Added a native Settings preference pane with three independent switches.
- Added Vietnamese and English localization based on the system language.
- Added the BatteryUKRM preference icon.
- Added a Respring action.
- Disabled modules do **not install their corresponding hooks**, allowing problematic functionality to be isolated without uninstalling the package.
- Preserves the real Cycle Count implementation from 1.0.2.

## Compatibility and known issues

BatteryUKRM-RH uses the same private iOS Battery Health / Settings interfaces as the rootless build. Compatibility can therefore vary by iOS version even when the Roothide package itself installs correctly.

> **iOS 17.7 known compatibility issue:** testing of the BatteryUKRM hook set has shown that the **Maximum Capacity** portion may fail to hook correctly on iOS 17.7, potentially leaving Maximum Capacity loading/spinning or unavailable, while **Cycle Count may still work**. If this occurs, disable **Restore Maximum Capacity** and respring; the other modules can remain enabled.

The iOS 17.7 note concerns the hook compatibility itself and should not be interpreted as a battery hardware diagnosis.

## Roothide status

BatteryUKRM-RH 1.0.2 was confirmed working by community testers on real Roothide devices. Version 1.1.0 keeps the same underlying battery hook behavior but adds modular preferences and per-feature hook installation.

Because the maintainer does not currently have a dedicated Roothide test device, **1.1.0 should receive additional real-device testing**. The previous **1.0.2 DEB is intentionally retained in the package repository as a rollback build**.

## Implementation

The tweak uses system frameworks/runtime hooks rather than hard-coded rootless jailbreak paths for its battery logic. The package is built using the **Roothide Theos scheme** and uses the Roothide architecture/package format.

## Original reference configuration

The rootless BatteryUKRM implementation has been confirmed working on:

- **Device:** iPhone 12 Pro
- **iOS:** 17.0
- **Jailbreak:** Dopamine rootless
- **Battery:** replaced with an Apple battery
- **Battery BMS/flex:** original battery BMS/flex was **not transplanted** to the replacement battery

## Display / screen replacement

BatteryUKRM-RH is focused on **battery-related** repair information. Display/screen replacement behavior has not been validated, and no claim is made that the tweak hides or modifies replaced-display information.
