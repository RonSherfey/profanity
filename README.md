# profanity
Profanity is a high performance (probably the fastest!) vanity address generator for Ethereum. Create cool customized addresses that you never realized you needed! Recieve Ether in style! Wow!

![Screenshot](/img/screenshot.png?raw=true "Wow! That's a lot of zeros!")

### Releases
Latest release compiled for 64-bit Windows & Linux can be found [here](https://github.com/johguse/profanity/releases).

### Disclaimer
Always verify that a private key generated by this program corresponds to the public key printed by importing it to a wallet of your choice. This program like any software might contain bugs and it does by design cut corners to improve overall performance.

### Usage
```
usage: ./profanity [OPTIONS]

  Basic modes:
    --benchmark             Run without any scoring, a benchmark.
    --zeros                 Score on zeros anywhere in hash.
    --letters               Score on letters anywhere in hash.
    --numbers               Score on numbers anywhere in hash.

  Modes with arguments:
    --leading <single hex>  Score on hashes leading with given hex character.
    --matching <hex string> Score on hashes matching given hex string.

  Advanced modes:
    --leading-range         Scores on hashes leading with characters within
                            given range.
    --range                 Scores on hashes having characters within given
                            range anywhere.

  Range:
    -m, --min <0-15>        Set range minimum (inclusive), 0 is '0' 15 is 'f'.
    -M, --max <0-15>        Set range maximum (inclusive), 0 is '0' 15 is 'f'.

  Misc:
    -s, --skip <index>      Skip device given by index.
    -w, --work <size>       Set OpenCL local work size. [default = 64]
    -W, --workmax <size>    Set OpenCL maximum work size. [default = 1048576]

  Examples:
    ./profanity --leading f
    ./profanity --matching dead
    ./profanity --matching badXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXbad
    ./profanity --leading-range -m 0 -M 1
    ./profanity --leading-range -m 10 -M 12
    ./profanity --range -m 0 -M 1

  About:
    profanity is a vanity address generator for Ethereum that utilizes
    computing power from GPUs using OpenCL.

    Author: Johan Gustafsson <profanity@johgu.se>
    Beer donations: 0x000dead000ae1c8e8ac27103e4ff65f42a4e9203
```
### Benchmarks
|Model|Clock Speed|Memory Speed|Modified straps|Speed|Time to match eight characters|
|:-:|:-:|:-:|:-:|:-:|:-:|
|R9 290|1150|1400|NO|100 MH/s| ~43 s
|R9 290|1040|1300|NO|91 MH/s| ~47 s
|RX 480|1266|2000|YES|83 MH/s| ~52 s
|RX 580|1366|1750|YES|79 MH/s | ~54 s
|RX 470|1206|1650|YES|72 MH/s| ~60 s
|RX VEGA56|1408|1100|YES|146 MH/s| ~35 s

