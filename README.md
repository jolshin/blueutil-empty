# Description

Blueutil is a CLI for bluetooth on OSX currently maintained by Ivan Kuchin [https://github.com/toy](https://github.com/toy) and the original version is located at [https://github.com/toy/blueutil](https://github.com/toy/blueutil)

This fork has been made to add a functinality in the code `blueutil.m` to pair bluetooth keyboard without PIN code hosted by OSX, instead keyaboard hosts the PIN and this resolves problem for modern OSX (theoretically Monterey 12 and above / Tested on Ventura 13) pairing with the A1016 Apple Wireless Keyboard.

Full description of the `blueutil` can be found at [https://github.com/toy/blueutil](https://github.com/toy/blueutil)

This code based on the `blueutil` version 2.13.0

## Notes

Uses private API from IOBluetooth framework (i.e. `IOBluetoothPreference*()`).

Opening Bluetooth preference pane always turns on discoverability if bluetooth power is on or if it is switched on when preference pane is open, this change of state is not reported by the function used by `blueutil`.

## Example

Pairing request:
```sh
blueutil --pair XX:XX:XX:XX:XX:XX empty
```

Enter the PIN code (eg "0000" and press the Return key) on the A1016 keboard and the terminal will prompt you to enter the PIN code you typed on the keyboard.

```sh
Type pin code (up to 16 characters) for "XX:XX:XX:XX:XX:XX" (xx-xx-xx-xx-xx-xx) and press Enter:
```

Enter the PIN into the terminal and pairing will be completed.

## Install/uninstall

### From source

```sh
git clone https://github.com/jolshin/blueutil-empty.git
cd blueutil-empty

# build
make

# install
make install

# uninstall
make uninstall
```

You may need to prefix install/update and uninstall make commands with `sudo`.

## Copyright

Originally written by Frederik Seiffert ego@frederikseiffert.de http://www.frederikseiffert.de/blueutil/

Maintained by Ivan Kuchin (2011-2025) https://github.com/toy

Copyright (c) 2026 Nikolay Jolshin. See [LICENSE.txt](LICENSE.txt) for details.
