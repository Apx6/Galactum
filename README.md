Galactum - generator
==================

A python / bash Cryptonote source creator. Generate and compile new or maintain old code with a single command.
Modified Version for maintaining Galactum. It's limited to Galactum, any other options are disabled.

#### Table of Contents

* [Features](#features)
* [Usage](#usage)
  * [Downloading & Installing](#1-downloading--installing)
  * [Configuration](#2-configuration)
  * [Generate coin](#3-generate-coin)
  * [Print genesis tx hex](#4-print-genesis-tx-hex)
* [Examples (real life)](#examples_real_life)
  * [Dashcoin](#1-dashcoin)
  * [Forknote](#2-forknote)
* [Coins Using This Software](#coins-using-this-software)
* [Community / Support](#community--support)
* [Contributing](#contributing)

#### Features

* Cryptonote source code creation, based on:
   * Bytecoin code (latest version)
* Single command code and binaries update
* Simple update for existing code
* Compile for
  * Ubuntu (tested on 14.04)
  * Mac OS X (tested on Yosemite)

Usage
===

#### 1) Downloading & Installing

Clone the repository:

```bash
	git clone https://github.com/Apx6/Galactum.git Galactum
	cd Galactum
```

Install dependencies:

* Windows - [follow this instructions](https://github.com/dashcoin/cryptonote-generator/blob/master/docs/windows-requirements-install.md)
* Linux / Mac OS X
```
bash install_dependencies.sh
```

#### 2) Configuration


Configuration File is Pre-Generated in config.json




#### 3) Generate coin

The file `config.json` is used by default but a file can be specified using the `-f file` command argument, for example:

```bash
	bash generator.sh -f [CONFIG_FILE] [-c COMPILE_OPTIONS]
```

By default, the cryptonote generator is not using multithread. I strongly recommend to use this arguments, if you are not building on a on VPS with no swap defined

###### Windows:
```bash
	bash generator.sh -f config_example.json -c '/maxcpucount:3'
```

###### Linux / Mac OS X (Cmake 2.8.x):
```bash
	bash generator.sh -f config_example.json -c '-j3'
```

#### 4) Print genesis tx hex

If you are creating a new coin, you need to create the genesis tx hex:

```
	cd generated_files/binaries/yourcoin   # yourcoin-linux for Linux, yourcoin-mac for Mac
	./yourcoind --print-genesis-tx
```
Change the _GENESIS_COINBASE_TX_HEX_ in your configuration file, then [3) Generate coin](#3-generate-coin) again.


### Community / Support

* IRC (freenode)
  * Support / general / development discussion join #dashcoin: [https://webchat.freenode.net/?channels=#dashcoin](https://webchat.freenode.net/?channels=#dashcoin)
* [CryptoNote Forum](https://forum.cryptonote.org/)


#### Projects Using This Software

* [Dashcoin](https://bitcointalk.org/index.php?topic=1020627.0)
* [Forknote](https://bitcointalk.org/index.php?topic=1079306.0)


#### Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

Extensions must be located in *extensions* folder.


Donations
---------
* BTC: `1EYiA8o1KsDZxMHXvptxXyaVwuhTVNBMFp`
* DSH: <sup><sub>`D3z2DDWygoZU4NniCNa4oMjjKi45dC2KHUWUyD1RZ1pfgnRgcHdfLVQgh5gmRv4jwEjCX5LoLERAf5PbjLS43Rkd8vFUM1m`</sup></sub>
* BCN: <sup><sub>`21YR5mw5BF2ah3yVE3kbhkjDwvuv21VR6D7hnpm4zHveDsvq5WEwyTxXLXNwtU5K4Pen89ZZzJ81fB3vxHABEUJCAhxXz2v`</sup></sub>
* XMR: <sup><sub>`47LEJyhCgNFcoz6U8x7tUk6LEHe38NobAfn4ou8d588jY5nddvgEANLMMcwxsbfbkJRw4xPwcG583Gq189hjusShEyk9FXz`</sup></sub>

*Donate XMR if you want to XMR version to be developed*

Additional credits
------------------
* [piotaak](https://github.com/piotaak) (tests for cryptonotecoin-core extension)

License
-------
Released under the GNU General Public License v2

http://www.gnu.org/licenses/gpl-2.0.html
