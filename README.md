# Get submodules
    git submodule update --init --recursive

# Build the modified mdloader
    cd mdloader
    make

# Enable Smart EEPROM using mdloader
    cd build
    ./mdloader --first --smarteep

# Build the modified default keymap
    cd qmk_firmware
    make massdrop/ctrl:default_md

# Load the new firmware on to the keyboard
    ./mdloader --first --restart --download path/to/qmk_firmware/.build/massdrop_ctrl_default_md.hex


