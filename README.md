# ottobon patchset instructions
### Get submodules
    git submodule update --init --recursive

### Build the modified mdloader
    cd mdloader
    make

### Enable Smart EEPROM using mdloader
    cd build
    ./mdloader --first --smarteep

### Build the modified default keymap
    cd qmk_firmware
    make massdrop/ctrl:default_md

### Load the new firmware on to the keyboard
"while the mdloader command is waiting for a device, enter flashing mode on your keyboard with Fn + B or the tiny button on the back. After the new firmware uploads, unplug and plug in the keyboard to restart it (it will look dead, but it’s just not restarting)."

https://www.travisgeis.com/2020/10/05/adding-persistent-settings-to-drop-ctrl/

    ./mdloader --first --restart --download path/to/qmk_firmware/.build/massdrop_ctrl_default_md.hex

# TODO:
- pursue this thread: https://github.com/Massdrop/mdloader/pull/16
- recommends adding a key to reset eeprom to map
- doesn't seem to need `ottobonn` branch of qmk, runs mainline qmk drop/ctrl support ... merges instead this PR: https://github.com/qmk/qmk_firmware/pull/6068
- uses the full qmk env/toolchain for building
