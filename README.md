# mcrcon
**mcrcon** is a program that sends remote console (rcon) commands to a Mojang Minecraft server.

See [Commands](https://minecraft.gamepedia.com/Commands) for available commands and [RCON](https://wiki.vg/RCON) for protocol documentation.

[![Master build](https://api.travis-ci.org/carlbennett/mcrcon.svg?branch=master)](https://travis-ci.org/carlbennett/mcrcon)

## Installing

**Source:**

```sh
git clone https://github.com/carlbennett/mcrcon.git
cd mcrcon
make
sudo make install
```

Check [**INSTALL**](./INSTALL.md) for more details.

**Releases:**

You can also download precompiled binaries [from Tiiffi's GitHub](https://github.com/Tiiffi/mcrcon/releases/latest).

## Usage

```
Usage: mcrcon [OPTIONS]... [COMMANDS]...

Sends rcon commands to Minecraft server.

Option:
  -h            Print usage
  -H            Server address
  -P            Port (default is 25575)
  -p            Rcon password
  -t            Interactive terminal mode
  -s            Silent mode (do not print received packets)
  -c            Disable colors
  -r            Output raw packets (debugging and custom handling)
  -v            Output version information

Server address, port and password can be set using following environment variables:
  MCRCON_HOST
  MCRCON_PORT
  MCRCON_PASS

Command-line options will override environment variables.
Rcon commands with arguments must be enclosed in quotes.

Example:
        mcrcon -H my.minecraft.server -p password "say Server is restarting!" save-all stop
```

## Enable rcon on server

Remember to enable rcon by adding following lines to the `server.properties` file.

```
enable-rcon=true
rcon.port=25575
rcon.password=your_rcon_pasword
broadcast-rcon-to-ops=false
```

## Contact

This is a fork of Tiiffi's original code. Please contact the original author at [github.com/Tiiffi/mcrcon](https://github.com/Tiiffi/mcrcon/).
