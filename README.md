# Setting up Paranoid Doze
To build Paranoid Doze you have to build the package in your device tree.
```bash
    # Paranoid Doze
    PRODUCT_PACKAGES += \
        ParanoidDoze
```
In order to have the proper options showing up you have to define the device related sensors in your build properties

- Set this to "true" if the device uses the proximity sensor to check for pocket & handwave gestures.
```bash
    ro.sensor.proximity
```
- The device specific pickup sensor to enable pickup gesture, if present.
```bash
    ro.sensor.pickup
```
- Set this to the value which the pickup sensor reports when the device is picked up (lifted), if it is different from the default value (1).
```bash
    ro.sensor.pickup.value
```
- Set this to the value which the pickup sensor reports when the device is put back down (lowered) after pickup, if supported.
```bash
    ro.sensor.pickup.lower.value
```

### OEM Examples
These properties are not representative of all OnePlus/Xiaomi devices and serve as an example, you'll need to reconfirm which ones your device uses.
- `Oplus devices`
```bash
    ro.sensor.value=0
    ro.sensor.pickup=android.sensor.tilt_detector
```
- `Xiaomi`
```bash
    ro.sensor.proximity=true
    ro.sensor.pickup=xiaomi.sensor.pickup
    ro.sensor.pickup.lower.value=2
```
