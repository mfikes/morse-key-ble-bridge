# morse-key-ble-bridge
Connect Morse key as a Bluetooth keyboard.

This repo provides firmware that enables connecting a Morse key to your device as a keyboard, such as for use with the Morse Chat mobile app.

To use, install the firmware on a Nordic nRF development board (e.g., nRF5340-DK). Pressing button one on the dev board sends a space character to a paired Bluetooth device. Simply connect a Morse key (straight or keyer) to button one by soldering diagonal contacts, making it function as a low-resistance switch when keyed. Since there is a perceptible delay as key signals are transmitted via Bluetooth, it is worth having a keyer that generates the sidetone, while simultaenously turning off the sidetone in the receiving app.

To pair with a mobile device, choose _Morse Key BLE Bridge_ in the Bluetooth settings and press button one (or activate the connected Morse key) when prompted to pair.

[![Morse Key BLE Bridge Demo](http://img.youtube.com/vi/O0wdYhWQfyg/0.jpg)](http://www.youtube.com/watch?v=O0wdYhWQfyg "Morse Key BLE Bridge Demo")

## How to use

This is a Zephyr-based firmware repo.
Read the getting-started guide here: <https://docs.zephyrproject.org/latest/getting_started/index.html>

This repo is using **Workflow 4: Application as the manifest repository**,
as described in <https://developer.nordicsemi.com/nRF_Connect_SDK/doc/1.6.0/nrf/dm_adding_code.html#user-workflows>

This repo is not to be cloned directy from git!
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
 
## License

This project is derived from the Nordic HID keyboard sample app. The derivations are licensed under the MIT License. See the LICENSE file for more details.
