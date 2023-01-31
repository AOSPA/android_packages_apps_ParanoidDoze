# Setting up Paranoid Doze
To build Paranoid Doze you have to build the package in your device tree.
```bash
    # Paranoid Doze
    PRODUCT_PACKAGES += \
        ParanoidDoze
```
In order to have the proper options showing up you have to define the device related sensors in your build properties

- Set this to "0" only if the device uses the value for tilt_detector on pickup as 0 and on the rest as 1. (OPLUS Devices)
```bash
    ro.sensor.pickup.value
```
- Set this to "true" if the device uses the proximity sensor to check for pocket & handwave gestures.
```bash
    ro.sensor.proximity
```
- The device specific pickup sensor to enable pickup gesture.
```bash
    ro.sensor.pickup
```

### OEM Examples
These properties are not representative of all OnePlus/Xiaomi devices and serve as an example, you'll need to reconfirm which ones your device uses.
- `Oplus devices`
```bash
    ro.sensor.pickup.value=0
    ro.sensor.pickup=oneplus.sensor.pickup
```
- `Xiaomi`
```bash
    ro.sensor.proximity=true
    ro.sensor.pickup=xiaomi.sensor.pickup
```
