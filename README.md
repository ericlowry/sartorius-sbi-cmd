# sartorius-sbi-cmd
Sartorius Scale SBI command line interface

# Description
A simple command line interface for interacting with a sartorius scale.
This utility allows you to query the details of the scale, zero-tare the scale,
get the current weight and more.

# Installation
````
git clone https://github.com/ericlowry/sartorius-sbi-cmd.git
cd sartorius-sbi-cmd
npm install
node sbi-cmd.js --help
````

# Usage
````
$ node sbi-cmd.js

  Usage: sbi-cmd [options] [command]


  Commands:

    info           show information about the scale
    tare           zero-tare the scale
    weight         show current weight
    toggle         toggle the scale mode ( weight | parts/lb )
    message [msg]  send an operator message to the scale, like READY or ERROR
    monitor        monitor the weight and scale keys pressed

  Options:

    -h, --help              output usage information
    -V, --version           output the version number
    -d --ttyDevice <dev>    device name [/dev/tty.USB0]
    -b --baudRate <baud>    1200, [9600] or 38400
    --dataBits <bits>       7 or [8]
    --stopBits <bits>       0 or [1]
    --parity <parity>       odd, even or [none]
    --rtscts                ready-to-send, clear-to-send
    --xon                   xon handshake
    --xoff                  xoff handshake
    --xany                  xany handshake
    --responseTimeout <ms>  response timeout [200] milliseconds
    --precision <places>    weight precision [1] or 2 decimal places


$
````
# Examples

## Get the scale's model and serial #
````
$ node sbi-cmd.js info --ttyDevice /dev/tty.USB0 
Scale Type    : PMA7501-X00V1
Serial Number : 0034209055
$
````

## Get the current weight on the scale
````
$ node sbi-cmd.js weight --ttyDevice /dev/tty.USB0 
Weight: 249.1 g
$
````

## Zero-Tare the scale
````
$ node sbi-cmd.js tare --ttyDevice /dev/tty.USB0
Tared!
$
````

# Notes

For windows users, use "--ttyDevice COM1:" or similar.