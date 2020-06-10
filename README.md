# Platformio Devcontainer Template

This is a [VSC Devcontainer](https://code.visualstudio.com/docs/remote/containers) for [Platformio](https://platformio.org/) based on Debian Buster.

- It uses Python 3.8.3
- Installs the nececessary udev rules
- Passtrough USB devices
- Forwards pio home on port 8008
- Uses default pio projects folder as workspace

It should work with all Unix based operating systems.
Windows 10 is currently not supported, because there is [no USB passtrough support in Docker for Windows](https://github.com/docker/for-win/issues/3926).

## License

Copyright 1996 Lennart Zebandt
SPDX-License-Identifier: Apache-2.0
