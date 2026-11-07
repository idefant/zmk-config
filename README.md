# ZMK Firmware for Cornechon

This is a repository for a ZMK Firmware for Cornechon keyboard.

## Keymap

![Keymap Representation](./keymap-drawer/cornechon.svg?raw=true "Keymap Representation")

### Space shortcuts

Space preserves modifiers for shortcuts such as Alt+Space, Ctrl+Space and
GUI+Alt+Space. Holding both **left Ctrl and left Alt** sends Right Alt+Space
for non-breaking space in layouts that map it to that character. Either
modifier alone does not activate this substitution.

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

1. Make changes to the [cornechon.keymap](config/cornechon.keymap) file using your favorite text editor.
2. Commit changes to your repository.
3. Go to `Actions` tab in your Github repository, locate the latest build and wait for it to complete.
4. Grab the `firmware.zip` archive

### About firmware

#### If you use dongle

If you use nice!nano controller for dongle, load `cornechon_central_dongle-nice_nano-zmk.uf2`.

If you use xiao for dongle, load `cornechon_central_dongle-xiao_ble-zmk.uf2`.

Also, if you use dongle load "peripheral" uf2 for left and right parts.

#### If you don't use dongle

Load `cornechon_central_left-nice_nano-zmk.uf2` on the left part and `cornechon_peripheral_right-nice_nano-zmk.uf2` for the right part.

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
