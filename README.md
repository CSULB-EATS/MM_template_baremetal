# MCU Driver Template

Welcome to the generic MCU driver template! This repository provides a minimal CMake-based structure for writing and organizing MCU drivers. Only the essential build scripts, CMake configuration, and mcu_support/ folder are included (only f4,f7,h5,l4).

# Need more info?

If you want a step-by-step guide to setting up STM32 projects bare-metal (without CubeIDE), check out this helpful article:
[STM32 Without CubeIDE: The Bare Necessities](https://kleinembedded.com/stm32-without-cubeide-part-1-the-bare-necessities/)

---

# MCU Driver Template

Welcome to the generic MCU driver template! This repository provides a minimal CMake-based structure for writing and organizing MCU drivers. Only the essential build scripts, CMake configuration, and mcu_support/ folder are included.

## Quick Start for New Members

1. Clone this repository.
2. Install the prerequisites below.
3. Use the provided scripts to build for your target MCU.
4. Write your ST specific drivers in the `platform/` folder. Write your test drivers in `app/`. Add as much folder as you need but please account for cmake and compiling tree.
5. If you get stuck, check the link above or ask a teammate/leads/mentors!

## Installing Prerequisites
First, install the arm toolchain. If you are on a Unix system, simply use your package installer, for example in Ubuntu: `sudo apt-get install arm-none-eabi-gcc`.
On Windows, you can download it from online, try [here](https://developer.arm.com/downloads/-/gnu-rm) - you may have to add it to your path. Make sure it worked: `arm-none-eabi-gcc --version`

If you want to cross-compile for 32-bit RPI, also install the arm32 toolchain: `gcc-arm-linux-gnueabihf`.
On Windows, try [here](https://developer.arm.com/downloads/-/gnu-a). Make sure it worked: `arm-linux-gnueabihf-gcc --version`

Next, install CMake. `sudo apt-get install cmake`
On Windows, try [here](https://cmake.org/download/). Again, may have to add to path.
Make sure it worked: `cmake --version`

Also, install Ninja `sudo apt-get install ninja-build`
On Windows, try [here](https://github.com/ninja-build/ninja/releases). Same with adding to path.
Make sure it worked: `ninja --version`

## Building
To build:
If you are on Windows, use the `.ps1` script in powershell. If on Linux, use the `.sh` script. The minimum parameters look like this:
`./make.ps1 -t <name of preset>`.
For example, `./make.ps1 -t stm32f746` (see CMakePresets.json).

For a clean build, do:
`./make.ps1 -t <name of preset> -c`

Builds are by default done in Debug mode, but Release mode can be selected with the -r parameter: `./make.ps1 -t stm32f746 -r`

## Debugging
To debug, make sure you have openocd installed `sudo apt-get install openocd`
On Windows, try [here](https://openocd.org/pages/getting-openocd.html). Also may have to add to path.
Additionally, grab the cortex-debug extension for VSCode.
There are reference launch.json files found in the repository already under .vscode.

## Developing Drivers
Write your MCU drivers in the `mcu_support/` directory. This template is intentionally minimal to allow you to add only what you need for your project.

Install clang-format to auto-format your code - on Windows, try `<python> -m pip install clang-format`. On Linux, try `sudo apt install clang-format`. In VSCode, you can go to settings > Text Editor > Formatting > Format On Save to enable auto-formatting on save.