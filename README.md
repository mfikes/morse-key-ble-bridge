# morse-key-ble-bridge
Connect Morse key as a Bluetooth keyboard.

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
