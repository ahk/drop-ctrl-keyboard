# Installing mainline QMK on a 2019 drop/ctrl

## The year is 2022 ... the war rages

As of 2022-7-19 (the date of my writing this article to my future self) QMK project and drop/Massdrop are in a disagreement. For a bit qmk was happy that Massdrop had done the thing, but now oh those scalliwags Massdrop has contributed infringing code. Oh woe. So now they are technically cut from the project but there is a several months stale PR that supposedly rewrites the base ... platform impl? That isn't infringing? And because that's true, the maintainers say they will continue to support drop keyboards, but that unless the new impl is merged eventually they will delete existing support.

Anyway, if you pull out a firmware from 'firmware_collection' and you install the QMK toolbox I have here, well then you've got QMK v0.17.4 and the QMK Toolbox v0.2.2, and guess what dogggonnit they just work together with a stock circa-2019-drop/ctrl keyboard.

INHALE

<https://github.com/qmk/qmk_firmware/tree/0.17.5>
<https://github.com/qmk/qmk_toolbox/releases/tag/0.2.2>

## Install QMK Toolbox

`qmk_toolbox_install.exe` is the installer. Do it. This thing will find and flash your keyboard once you've put it in flashing/reset mode.

## Select your firmware

My firmware right now is called `massdrop_ctrl_andy.bin` and it's just stock drop/ctrl as from the qmk project. In fact I created it using their web configurator tool <https://config.qmk.fm/#/massdrop/ctrl/LAYOUT>. Maybe eventually when I have some time I'll actually modify this.

## Enter flashing mode on keyboard

"while the mdloader command is waiting for a device, enter flashing mode on your keyboard with Fn + B or the tiny button on the back. After the new firmware uploads, unplug and plug in the keyboard to restart it (it will look dead, but it’s just not restarting)." - Massdrop

## Flash the new firmware on to the keyboard

Open QMK Toolbox, select the firmware file, make sure you've entered flashing mode (see above), and then you can hit flash. Wait and DO NOT DISTURB THIS TRANSACTION.

## Why did we do this

- Persistent EEPROM
- Better built-in goofs
- Any goofs we make ourselves will be portable to other 'boards

## Also

This repo contains an archive of the code used to build my firmwares. See `qmk_firmware_src`.
This was downloaded from the qmk repo artifacts, so I guess it comes from a checkout on a linux machine in the cloud somewhere.

## TODO

- occasionally make sure we aren't getting left behind by qmk forever actually
  - how long would a person reasonably expect their support?
- someone recommended adding a key to reset eeprom to map
