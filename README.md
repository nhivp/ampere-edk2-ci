# Ampere EDK2 Continuous Integration (CI)

[![Build Status](https://github.com/nhivp/ampere-edk2-ci/actions/workflows/daily-build.yml/badge.svg)](https://github.com/nhivp/ampere-edk2-ci/actions/workflows/daily-build.yml)

## Overview

The repository is designed to validate the daily build of the Ampere platforms based on the Tianocore/edk2-platforms repository. 
This CI system ensures that any changes made to the edk2 or edk2-platforms repositories do not break the platform builds.

While the initial focus is on the Mt. Jade platform, the CI workflow is flexible and can be extended to support later Ampere-powered platforms.

## Build Types

The workflow performs daily builds with multiple configurations to catch errors across different build settings. 
The build matrix includes the following variants:

### Build Configurations:
- **RELEASE**: Standard production build.
- **DEBUG**: Development build with debugging features enabled.
- **NOOPT**: Build without optimizations, used for identifying certain classes of bugs.

### Compilers:
- **GCC**: The GNU Compiler Collection, widely used for building firmware and other system-level software.
- **CLANGDWARF**: The Clang compiler with DWARF debugging information format.

Each build configuration is tested across both compilers to ensure robustness.

## How It Works

The GitHub Actions workflow is triggered daily at 7:00 AM UTC+7 and runs a matrix of builds combining the above configurations and compilers. 
The results of the build tests are displayed in the Actions tab.

You can view the current build status here:
[![Build Status](https://github.com/nhivp/ampere-edk2-ci/actions/workflows/build.yml/badge.svg)](https://github.com/nhivp/ampere-edk2-ci/actions)

## Extending to New Platforms

Additional platforms can be added to this CI system by modifying the workflow configuration.

## Contributing

Contributions are welcome! If you'd like to improve the CI pipeline or add support for additional platforms, feel free to submit a pull request.
