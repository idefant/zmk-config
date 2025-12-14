# ZMK Firmware for Corne

This is a repository for a ZMK Firmware for Corne keyboard.

## Keymap

![Keymap Representation](./keymap-drawer/corne.svg?raw=true "Keymap Representation")

## FAQ

### How to change the keymap?

1. Fork this repository.
2. Enable Github Actions for your repository.

You have two options on how to configure your desired keymap:

#### Option 1. Keymap Editor

1. Open [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/).
2. Connect it to your Github account and give an access to your repository to Keymap Editor's app.
3. Make changes to your keymap and press `Save` - it will trigger software build. Wait for it to complete.
4. Grab the `firmware.zip` archive.

#### Option 2. Manual

1. Make changes to the [corne.keymap](config/corne.keymap) file using your favorite text editor.
2. Commit changes to your repository.
3. Go to `Actions` tab in your Github repository, locate the latest build and wait for it to complete.
4. Grab the `firmware.zip` archive

### About firmware

#### If you use dongle

If you use nice!nano controller for dongle, load `corne_central_dongle-nice_nano-zmk.uf2`.

If you use xiao for dongle, load `corne_central_dongle-xiao_ble-zmk.uf2`.

Also, if you use dongle load "peripheral" uf2 for left and right parts.

#### If you don't use dongle

Load `corne_central_left-nice_nano-zmk.uf2` on the left part and `corne_peripheral_right-nice_nano-zmk.uf2` for the right part.

### How to flash the keyboard?

1. Obtain `firmware.zip`
2. Unzip `firmware.zip`
3. Turn off the power for selected halve (move slider to position `OFF`)
4. Connect selected halve to the PC via USB-C cable
5. Press `RESET` button **twice** to enter DFU mode - you should see new USB device in your file manager
6. Copy the corresponding firmware to the root directory of the new USB device
7. Disconnect selected halve from the PC
8. Repeat steps 3-7 for the other halve

### How to pair halves?

1. Turn off the power for both halves (move slider to position `OFF`)
2. Turn on the power for both halves (move slider to position `ON`)
3. Press `RESET` button **once** on both halves **simultaneously**

### Problems

#### I'm getting File Transfer Error after copying firmware to the keyboard

It's OK. Proof: https://zmk.dev/docs/troubleshooting#file-transfer-error
