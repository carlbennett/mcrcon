<!-- vim: set colorcolumn=: -->
# mcrcon
**mcrcon** is a console program that sends remote console ([rcon](https://developer.valvesoftware.com/wiki/Source_RCON_Protocol)) commands to a Mojang Minecraft server.
Its purpose is to be a client for remote administration and server maintenance scripts.

See [Commands](https://minecraft.gamepedia.com/Commands) for available commands and [RCON](https://wiki.vg/RCON) for protocol documentation.

[![Master build](https://api.travis-ci.org/carlbennett/mcrcon.svg?branch=master)](https://travis-ci.org/carlbennett/mcrcon)

## Installing

### Package Manager
See https://pkgs.org/download/mcrcon for available packages in various Linux distros (note that available packages might be outdated).

- Gentoo Linux: https://packages.gentoo.org/packages/games-util/mcrcon
- Arch Linux: https://aur.archlinux.org/packages/mcrcon/

### Building from sources
```sh
git clone https://github.com/carlbennett/mcrcon.git
cd mcrcon
make
sudo make install
```

Check [**INSTALL.md**](./INSTALL.md) for more details.

### Pre-compiled releases

You can also download pre-compiled binaries [from Tiiffi's GitHub](https://github.com/Tiiffi/mcrcon/releases/latest).

## Usage
```
Usage: mcrcon [OPTIONS] [COMMANDS]

Sends rcon commands to Minecraft server.

Option:
  -H  Server address (default: localhost)
  -P  Port (default: 25575)
  -p  Rcon password
  -t  Terminal mode
  -s  Silent mode
  -c  Disable colors
  -r  Output raw packets
  -w  Wait for specified duration (seconds) between each command (1 - 600s)
  -h  Print usage
  -v  Version information
```

Server address, port and password can be set using following environment variables:

```
MCRCON_HOST
MCRCON_PORT
MCRCON_PASS
```

## Notes
* mcrcon will start in terminal mode if no commands are given
* Command-line options will override environment variables
* Rcon commands with spaces must be enclosed in quotes

Example:
> Send three commands ("say", "save-all", "stop") and wait five seconds between the commands.

  `mcrcon -H my.minecraft.server -p password -w 5 "say Server is restarting!" save-all stop`

## Enable rcon on server

Remember to enable rcon by adding the following lines to the [`server.properties`](https://minecraft.gamepedia.com/Server.properties) file.

```
enable-rcon=true
rcon.port=25575
rcon.password=your_rcon_pasword
```

## Contact

This is a fork of Tiiffi's original code. Please contact the original author at [github.com/Tiiffi/mcrcon](https://github.com/Tiiffi/mcrcon/).

* WWW:         https://github.com/Tiiffi/mcrcon/
* MAIL:        tiiffi at gmail
* IRC:         tiiffi @ quakenet
* BUG REPORTS: https://github.com/Tiiffi/mcrcon/issues/

## License

This project is licensed under the zlib License, see the [LICENSE.txt](./LICENSE.txt) file for details.
