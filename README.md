# morse-key-ble-bridge
Connect Morse key as a Bluetooth keyboard.

This repo contains firmware meant to allow you to connect a Morse key as a keyboard to drive your device. For example, it can be used to connect to the Morse Chat mobile app running on a mobile phone.

When the firmware is running on a Nordic nRF dev board (an nRF5340-DK, for example), then pressing button one will cause a space character to be sent to a paired Bluetooth device. With this setup, it is then a simple matter of connecting a Morse key (either a straight key, or a keyer) to button one by soldering the connections across the button one contacts so that whenever keyed, button one will effectively be closed (low resistance).

In order to pair to mobile device, select it in the Bluetooth configuration, and then when prompted to pair, press button one (or activate your connected Morse key).

[![Morse Key BLE Bridge Demo](http://img.youtube.com/vi/O0wdYhWQfyg/0.jpg)]([http://www.youtube.com/watch?v=piJPrP3BKIk](https://youtu.be/O0wdYhWQfyg) "Morse Key BLE Bridge Demo")

### Do not clone directly from git!

This is a Zephyr-based firmware repo.
Read the getting-started guide here: <https://docs.zephyrproject.org/latest/getting_started/index.html>

This repo is using **Workflow 4: Application as the manifest repository**,
as described in <https://developer.nordicsemi.com/nRF_Connect_SDK/doc/1.6.0/nrf/dm_adding_code.html#user-workflows>


## How to use

This repo is NOT to be cloned directy from git!
Use it with Zephyr's `west` metatool, e.g.:
```
mkdir morse-key-ble-bridge
cd morse-key-ble-bridge
west init -m git@github.com:mfikes/morse-key-ble-bridge.git
west update
```

For more information about `west`, see <https://docs.zephyrproject.org/1.14.0/guides/west/repo-tool.html>


## Building

* `cd` to the application directory.
 _e.g._:
 ```
 cd /path/to/morse-key-ble-bridge/application/apps/bridge
 ```

* Build using west. The first time, the board needs to specified:
 ```
 west build --board=nrf5340dk_nrf5340_cpuapp -p always
 ```
 or
 ```
 west build --board=nrf52840dk_nrf52840 -p always
 ```

 Next time, you can just invoke the build command:
 ```
 west build
 ```

* Flash or debug your application:
 ```
 west flash
 # or
 west debug
 ```
