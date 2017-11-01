# LabPack: LabVIEW&trade; library for encoding/decoding MessagePack data

[About](#what-is-labpack) | [Installation](#installation) | [Documentation](#documentation) | [License](#license)

## What is LabPack?

[LabPack](http://sine.ni.com/nips/cds/view/p/lang/en/nid/215388) is a [LabVIEW&trade;](http://www.ni.com/labview) library for encoding and decoding [MessagePack](http://msgpack.org) data. 

The LabVIEW library uses the [LabPack shared library](https://github.com/fieldrndservices/labpack) for encoding and decoding MessagePack data. Pre-compiled Windows (DLL), macOS (dylib), Linux (so), and NI Linux RT (so) shared libraries are distributed with the LabPack LabVIEW library. The LabPack shared library and source code is maintained as a separate project and repository, respectively.

## Installation

A VI Package (VIP) is available on the [National Instruments (NI)](http://www.ni.com) [LabVIEW Tools Network](http://www.ni.com/labview-tools-network/). It is recommended to use the [VI Package Manager](https://vipm.jki.net/) published by [JKI](http://jki.net/) to install and update the library.

## Documentation

See the in-app LabVIEW Help system for more information and documentation about using the library after it has been installed, or visit the [web-based documentation](https://help.fieldrndservices.com/labpack). Examples are also available within the LabVIEW development environment using the `Help->Find Examples...` menu item.

### Build

The [HTML Help Workshop](https://www.microsoft.com/en-us/download/details.aspx?id=21138) developed and published by Microsoft must be installed to complete the build.

1. Open a VI to create the documentation.
2. Select `File->Print...` from the menu bar. A new dialog will appear.
3. In the Print dialog that appears, select the VI option between the two radio buttons. Do NOT select _Multiple VIs_ as this will combine all VI documentation into a single HTML file. Click _Next >_. A new page will appear.
4. Use the _Add File(s)..._ button to add multiple VIs to the _Select VIs_ list on the left. Once all of the VIs have been added to the list, click _Next >_. A new page will appear.
5. Select _VI documentation_ option from the radio buttons that appear in the _Print Contents_ box. Click _Next >_. A new page will appear.
6. Select _Using as a subVI_ for the _VI Documentation Style_. Most of the appropriate settings will be selected automatically when selecting the style. However, change _Connected controls_ to _All Controls_ in the dropdown menu under the _Controls_ checkbox. The _VI Documentation Style_ will change to _Custom_, but this is acceptable. Click _Next >_. A new page will appear.
7. Select the _HTML file_ from the radio buttons that appear in the _Destination_ box. Click _Next >_. A new page will appear.
8. Click _Save..._. Nothing needs to be changed in the _HTML_ box. Save the HTML file to the `src/Help` folder on-disk.
9. Repeat steps 1-8 for each VI that needs help documentation, i.e. all public VIs and controls.
10. Move all PNG files into the `images` sub-folder.
11. Remove the `LabPack_lvlib_` prefix from all HTML files in the `src/Help` folder.
12. Open each HTML file into a text editor and append all paths for images with the `images` folder. For example, in vim, the following can be done:

    :%s/IMG SRC="/IMG SRC="images\//g

13. Start the HTML Help Workshop (`C:\Program Files (x86)\HTML Help Workshop`). Open the `LabPack.hhp` file in the `src/Help` folder. Due to a bug in the application, the `LabPack.hhp` file cannot be opened by double-clicking on it. An error occurs when saving. 
14. Use the HTML Help Workshop to compile the HTML files into the CHM file.

## License

See the LICENSE.txt file for information about licensing and copyright.

