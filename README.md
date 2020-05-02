# LabPack: LabVIEW&trade; library for encoding/decoding MessagePack data

[About](#what-is-labpack) | [Installation](#installation) | [Documentation](#documentation) | [Tests](#tests) | [License](#license)

## What is LabPack?

[LabPack](http://sine.ni.com/nips/cds/view/p/lang/en/nid/215388) is a [LabVIEW&trade;](http://www.ni.com/labview) library for encoding and decoding [MessagePack](http://msgpack.org) data. 

The LabVIEW library uses the [LabPack shared library](https://github.com/fieldrndservices/labpack-c) for encoding and decoding MessagePack data. Pre-compiled Windows (DLL), macOS (dylib), Linux (so), and NI Linux RT (so) shared libraries are distributed with the LabPack LabVIEW library. The LabPack shared library and source code is maintained as a separate project and repository, respectively.

## Installation

A [VI Package (VIP)](https://www.vipm.io/package/field_rnd_services_labpack/) is available at [VIPM.io](https://www.vipm.io). The recommended installation instruction is to:

1. Navigate to the [LabPack package](https://www.vipm.io/package/field_rnd_services_labpack/) at [VIPM.io](https://www.vipm.io/).
2. Click on the _Install_ button to the right. The [VI Package Manager (VIPM)](https://www.vipm.io/download/) (freely available from [JKI](https://jki.net)) will start automatically.
3. Follow the on-screen instructions to complete the installation.

Alternatively, the toolkit can be installed by: (i) downloading the source code and building the VIP, (ii) downloading a VIP from the [releases](https://github.com/fieldrndservices/labpack/releases) section of this project, or (iii) manually copying the VIs from the source code into a project.

## Documentation

See the in-app LabVIEW Help system for more information and documentation about using the library after it has been installed, or visit the [web-based documentation](https://help.fieldrndservices.com/labpack). Examples are also available within the LabVIEW development environment using the `Help->Find Examples...` menu item.

## Tests

Tests are written in LabVIEW using the [Caraya](https://github.com/JKISoftware/Caraya) unit testing framework and included in the project via the `Tests` project library (.lvlib) and the `tests` on-disk folder. To run the tests, open the `LabPack.lvproj` file found in the root folder of the source code distribution in the LabVIEW Development Environment (32-bit or 64-bit) and run the `Run All` VI that is found in the `Tests` project library. The tests are organized in a hierarchy based on their relationship to the source code. There is a `Run All` VI within each child project library (.lvlib) to run all of the tests for a specific portion of the project.

## License

See the `docs` folder for all information about licensing and copyright.

