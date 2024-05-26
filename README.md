# GATT Thermocouple Reader

A simple thermocouple reader project that sends temperature measurements every second over GATT notifications.

## Hardware

For this project I'm using a cheap ESP32-C3 dev board (`esp32c3_luatos_core`) and a MAX31855 (Thermocouple-to-Digital Converter) module. Any BLE-capable board that is supported by Zephyr should work, you just need to update the dtoverlay accordingly.

## Software

Firmware is based on the ESS example from Zephyr, and the client was based on the GATT notification example from Bleak.

## Usage

On a computer that has BLE support, run `python ./client.py --name "THERMOCOUPLE" 00002a6e-0000-1000-8000-00805f9b34fb` to start logging temperat readings to a csv file. The Bluetooth device name is defined with `CONFIG_BT_DEVICE_NAME` in `prj.conf` and can be changed.
