# LabPack: LabVIEW&trade; library for encoding/decoding MessagePack data

[About](#what-is-labpack) | [Installation](#installation) | [Documentation](#documentation) | [Tests](#tests) | [License](#license)

## What is LabPack?

[LabPack](http://sine.ni.com/nips/cds/view/p/lang/en/nid/215388) is a [LabVIEW&trade;](http://www.ni.com/labview) library for encoding and decoding [MessagePack](http://msgpack.org) data. 

The LabVIEW library uses the [LabPack shared library](https://github.com/fieldrndservices/labpack-c) for encoding and decoding MessagePack data. Pre-compiled Windows (DLL), macOS (dylib), Linux (so), and NI Linux RT (so) shared libraries are distributed with the LabPack LabVIEW library. The LabPack shared library and source code is maintained as a separate project and repository, respectively.

## Installation

A VI Package (VIP) is available on the [National Instruments (NI)](http://www.ni.com) [LabVIEW Tools Network](http://www.ni.com/labview-tools-network/). It is recommended to use the [VI Package Manager](https://vipm.jki.net/) published by [JKI](http://jki.net/) to install and update the library.

## Documentation

See the in-app LabVIEW Help system for more information and documentation about using the library after it has been installed, or visit the [web-based documentation](https://help.fieldrndservices.com/labpack). Examples are also available within the LabVIEW development environment using the `Help->Find Examples...` menu item.

## Tests

Tests are written in LabVIEW using the [Caraya](https://github.com/JKISoftware/Caraya) unit testing framework and included in the project via the `Tests` project library (.lvlib) and the `tests` on-disk folder. To run the tests, open the `LabPack.lvproj` file found in the root folder of the source code distribution in the LabVIEW Development Environment (32-bit or 64-bit) and run the `Run All` VI that is found in the `Tests` project library. The tests are organized in a hierarchy based on their relationship to the source code. There is a `Run All` VI within each child project library (.lvlib) to run all of the tests for a specific portion of the project.

## License

See the `docs` folder for all information about licensing and copyright.

