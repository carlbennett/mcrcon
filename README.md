# mcrcon

mcrcon is console based Minecraft [rcon](https://developer.valvesoftware.com/wiki/Source_RCON_Protocol) client for remote administration and server maintenance scripts.

---

### Installing:

##### via packet manager:
See https://pkgs.org/download/mcrcon for available packages in various Linux distros.

- Gentoo Linux: https://packages.gentoo.org/packages/games-util/mcrcon
- Arch Linux: https://aur.archlinux.org/packages/mcrcon/

##### from sources:
```sh
git clone https://github.com/Tiiffi/mcrcon.git
cd mcrcon
make
sudo make install
```
Check [INSTALL.md](INSTALL.md) for more details.

You can also download precompiled binaries*: https://github.com/Tiiffi/mcrcon/releases/latest

<sub>*At the moment binaries are provided for Linux and Windows.</sub>

---

### Usage:
mcrcon [OPTIONS] [COMMANDS]

Sends rcon commands to Minecraft server.

```
Option:
  -H            Server address (default: localhost)
  -P            Port (default: 25575)
  -p            Rcon password
  -t            Terminal mode
  -s            Silent mode
  -c            Disable colors
  -r            Output raw packets
  -h            Print usage
  -v            Version information
  -w            Wait for specified duration (seconds) between each command
```
Server address, port and password can be set using following environment variables:
```
MCRCON_HOST
MCRCON_PORT
MCRCON_PASS
```
###### Notes:
- mcrcon will start in terminal mode if no commands are given
- Command-line options will override environment variables
- Rcon commands with spaces must be enclosed in quotes

Example:
  ```mcrcon -H my.minecraft.server -p password "say Server is restarting!" save-all stop```

---

##### Enable rcon on server
Remember to enable rcon by adding following lines to [```server.properties```](https://minecraft.gamepedia.com/Server.properties) file.
```
enable-rcon=true
rcon.port=25575
rcon.password=your_rcon_pasword
```

---

##### Contact:

* WWW:            https://github.com/Tiiffi/mcrcon/
* MAIL:           tiiffi at gmail
* IRC:            tiiffi @ quakenet
* BUG REPORTS:    https://github.com/Tiiffi/mcrcon/issues/

---

### License

This project is licensed under the zlib License - see the [LICENSE](LICENSE) file for details.

---

<sub>Master:</sub> ![Master build](https://api.travis-ci.org/Tiiffi/mcrcon.svg?branch=master)
<sub>Develop:</sub> ![Develop build](https://api.travis-ci.org/Tiiffi/mcrcon.svg?branch=develop)
