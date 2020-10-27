# LabPack: A LabVIEW&trade; library for encoding/decoding MessagePack data

[LabPack](http://sine.ni.com/nips/cds/view/p/lang/en/nid/215388) is a [LabVIEW&trade;](http://www.ni.com/labview) library for encoding and decoding [MessagePack](http://msgpack.org) data. 

This LabVIEW library uses the [LabPack shared library](https://github.com/fieldrndservices/labpack-c) for encoding and decoding MessagePack data. Pre-compiled Windows (DLL), macOS (dylib), Linux (so), and NI Linux RT (so) shared libraries are distributed with the LabPack LabVIEW library. The LabPack shared library and source code is maintained as a separate project and repository, respectively.

## Table of Contents

- [Example Usage](#example-usage)
- [Dependencies](#dependencies)
    - [Installation](#dependencies-installation)
    - [Development](#dependencies-development)
- [Installation](#installation)
- [Build](#build)
    - [Packaging using VIPM Pro (recommended)](#build-vipm-pro)
    - [Packaging using VIPM Free](#build-vipm-free)
- [Documentation](#documentation)
- [Tests](#tests)
- [License](#license)

## Example Usage

A [VI snippet](http://www.ni.com/tutorial/9330/en/) of encoding a cluster to a MessagePack binary data:

![Encoding a cluster to a MessagePack binary data](https://github.com/fieldrndservices/labpack-labview/blob/main/docs/encoding.png)

A VI snippet of decoding a cluster from MessagePack binary data:

![Decoding a cluster from MessagePack binary data](https://github.com/fieldrndservices/labpack-labview/blob/main/docs/decoding.png)

## Dependencies

### Installation

- LabVIEW 2009 or newer (All systems)

### Development

- [Caraya](http://sine.ni.com/nips/cds/view/p/lang/en/nid/215909)
- [HTML Help Workshop](https://docs.microsoft.com/en-us/previous-versions/windows/desktop/htmlhelp/microsoft-html-help-downloads) (for compiling the help documentation)
- [JKI State Machine](http://sine.ni.com/nips/cds/view/p/lang/en/nid/209025)
- LabVIEW 2009 or newer (for building)
- LabVIEW 2018 or newer
- Labricator (only for automated builds, private package available upon request)
- [OpenG Array Library](http://sine.ni.com/nips/cds/view/p/lang/en/nid/209027)
- [OpenG File Library](http://sine.ni.com/nips/cds/view/p/lang/en/nid/209027)
- [VIPM Pro](https://vipm.jki.net/get) (only for automated builds)
- [VIPM API](https://support.jki.net/hc/en-us/articles/214136183-VIPM-API) (only for automated builds)

## Installation

A [VI Package (VIP)](https://www.vipm.io/package/field_rnd_services_labpack/) is available at [VIPM.io](https://www.vipm.io). The recommended installation instructions are to:

1. Navigate to the [LabPack package](https://www.vipm.io/package/field_rnd_services_labpack/) at [VIPM.io](https://www.vipm.io/).
2. Click on the _Install_ button to the right. The [VI Package Manager (VIPM)](https://www.vipm.io/download/) (freely available from [JKI](https://jki.net)) will start automatically.
3. Follow the on-screen instructions to complete the installation.

Alternatively, the toolkit can be installed by: (i) downloading the source code and building the VIP, (ii) downloading a VIP from the [releases](https://github.com/fieldrndservices/labpack/releases) section of this project, or (iii) manually copying the VIs from the source code into a project.

## Build

Each component in the LabPack-LabVIEW project has a Source Distribution build specification. The destination of each source distribution build is the `builds` folder relative to the project root, i.e. same folder as the `LabPack.lvproj` file. Additionally, the output for the compiled help documentation is also the `builds` folder. The `builds` folder should _not_ be included in the version control repository. A `Build.vi` script is available in the `Scripts.lvlib` project library that will build all of the components and the help documentation automatically (VIPM Pro is not needed, but the [HTML Help Workshop](https://docs.microsoft.com/en-us/previous-versions/windows/desktop/htmlhelp/microsoft-html-help-downloads) is needed).

The VI Package Build (.vipb) specification, located in the `configs` folder relative to the project root, is configured for the package source to be the `builds` folder. Thus, the Source Distribution for each component must be built **before** opening the `LabPack.vipb` file in the <abbr title="VI Package Manager">VIPM</abbr>; otherwise, the package configuration will be lost.

### Packaging using VIPM Pro (recommended) <a name="build-vipm-pro"></a>

__Important__, if creating a package for LabVIEW 2009 from LabVIEW 2018, the [VI Server TCP/IP ports](http://zone.ni.com/reference/en-XX/help/371361P-01/lvhowto/configuring_the_vi_server/) must be different for each version of LabVIEW and verified with the [VIPM](https://knowledge.ni.com/KnowledgeArticleDetails?id=kA00Z000000P9YmSAK) application _before_ proceeding. An error will occur when the VIPM is started if both LabVIEW 2009 and 2018 are running at the same time. Basically, VIPM will not know which VI server to use if both versions of LabVIEW are using the same TCP/IP port.

If VIPM Pro is available, then open the `LabPack.lvproj` file in any version of LabVIEW newer than 2009 and run the `Package.vi` located in the `Scripts.lvlib` project library of the Project Explorer window. Ensure all dependencies are installed before running the `Package.vi` script.

Note, the version number for the package is set in the `configs\LabPack.vipb` file. The version number in the VIP build specification file should be modified and saved _before_ running the `Package.vi` script.

### Packaging using VIPM Free <a name="build-vipm-free"></a>

If VIPM Pro is _not_ available, then the following steps can be executed to do essentially the same thing as the `Package.vi` script. Ensure all dependencies, except VIPM Pro and the VIPM API, are installed before completing these steps.

1. Start LabVIEW 2018 or newer and open the `LabPack.lvproj` file.
2. From the Project Explorer window, **File>>Save for Previous Version...**, a new dialog will appear.
3. Select **9.0** from the drop down menu.
4. Click **Save...**. A new dialog will open.
5. Create the `target\9.0` folder hierarchy in the project root, i.e. the same folder as the `LabPack.lvproj` file, if it does not already exists.
6. Click **Save**.
7. Close LabVIEW 2018 or newer and the `LabPack.lvproj` file.
8. Navigate to `<project root>\src`.
9. Copy the `Help` folder to `<project root>\target\9.0\src`.
10. Start LabVIEW 2009.
11. Open the `<project root>\target\9.0\LabPack.lvproj` file. Do NOT open the project in any other version of LabVIEW.
12. Open each Source Distribution build specification under the "Build Specifications" tree item in the Project Explorer and change the _Output Destination_ to `<project root>\target\9.0\builds`. Save and close each build specification.
13. Run the `Build.vi` in the `Scripts` project library to build each Source Distribution under the "Build Specifications" tree item and the compiled help documentation file (`LabPack.chm`). The output of each build will be available in `<project root>\target\9.0\builds`.
14. Open the `<project root>\target\9.0\configs\LabPack.vipb` file in VIPM.
15. Build the VI package with VIPM. The output will be available at `<project root>\target\9.0\packages`. Do NOT modify anything in the package build specification, but ensure the "2009" version of LabVIEW is selected in the upper, right-hand corner of the VIPM application window.
16. Close VIPM.
17. Close LabVIEW 2009 and the `<project root>\target\9.0\LabPack.lvproj` file.

## Documentation

See the in-app LabVIEW Help system for more information and documentation about using the library after it has been installed, or visit the [web-based documentation](https://help.fieldrndservices.com/labpack). Examples are also available within the LabVIEW development environment using the `Help->Find Examples...` menu item.

## Tests

Tests are written in LabVIEW using the [Caraya](https://github.com/JKISoftware/Caraya) unit testing framework and included in the project via the `Tests` project library (.lvlib) and the `tests` on-disk folder. To run the tests, open the `LabPack.lvproj` file found in the root folder of the source code distribution in the LabVIEW Development Environment (32-bit or 64-bit) and run the `Run All` VI that is found in the `Tests` project library. The tests are organized in a hierarchy based on their relationship to the source code. There is a `Run All` VI within each child project library (.lvlib) to run all of the tests for a specific portion of the project.

## License

LabPack-LabVIEW is licensed under either the [BSD-3-Clause](https://opensource.org/licenses/BSD-3-Clause), and it contains statically compiled code from the [mpack](https://github.com/ludocode/mpack) project, which is licensed under the [MIT license](https://github.com/ludocode/mpack/blob/master/LICENSE). See the `docs` folder for more information about licensing and copyright. 

