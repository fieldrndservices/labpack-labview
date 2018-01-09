# Field R&D Services: LabPack Change Log

All notable changes to this project will be documented in this file, which is written in plain text (ASCII) using the [Markdown](http://daringfireball.net/projects/markdown/syntax) lightweight markup language. This project adheres to [Semantic Versioning](http://semver.org). 

## [Unreleased][Unreleased]

### Changed

- On-disk organization of help files to match VI organization.
- All help URLs to paths relative to the root location.

### Fixed

- Help file URLs for VIs.

## [1.0.0] - 2017-11-13

### Added

- Help documentation.
- Descriptions to all controls and indicators for all public VIs.
- Example of using the high level VIs (`To Msgpack` and `From Msgpack`).
- Example of using the lower level `Writer` and `Reader` classes.
- Shared libraries for Windows 32-bit, Windows 64-bit, macOS, Linux, NI Linux RT x86-64, and NI Linux RT ARM targets.
- The top-level `To Msgpack` VI that converts anything into MessagePack binary data.
- The top-level `From Msgpack` VI that converts MessagePack binary data into a schema.
- The `Writer` class for low-level encoding of MessagePack binary data.
- The `Reader` class for low-level decoding of MessagePack binary data.

