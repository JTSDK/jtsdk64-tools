# Setup Overview

This section will walk users through (step-by-step) the process of installing all required components for compiling [Hamlib], [Boost], and finally  [WSJT-X][]. If you follow this guide you should have a working [WSJT-X] package that can be installed upon completion.

It is highly recommended that users `uninstall` all previous JTSDK components before using this guide. There are ways to work around this requirement, however, it can be tedious and error prone. For the best results, a clean install is the development teams recommendation.

## Installation Order

While some areas can be skipped, or added later, this guide--and this authors personal recommendation--will proceed in the order listed. Advanced users may elect to move through the order as they see fit, however, be aware of the limitation and potential for issues in doing so.

## Living Document

Many sections of this site are `under construction`. As new content is made available it will be added to the site after review. All content will remain relevant to the latest release of the `JTSDK64-Tools v3.2.x Stream`. Any Change to the Major or Minor version schema will result in a tag of the existing main branch and migration to the next release.

## Preferred Environment

If and where possible, users should first install `JTSDK64-Tools` in a Virtual Machine (VM). While the process aims to prevent unforeseen events to the users main system, there is always the potential for issues to arise, thus, using a VM will help mitigate such risk.

## System Requirements

There is no question, the more system resources (CPU cores, RAM, Disk IO, Network Speed, etc) the compiling system has, the better the overall performance will be. Completion times, based on a number of end-user reports, have ranged from `2.5 hours` to a `full day`, so plan accordingly.

By far, the most time intensive elements for the the entire setup process is related to downloading installing [Qt][], followed by a lengthy compile time for [Boost][].

While one can get away with a small commodity-based computer for development work, the following would be a safe-minium for those wanting somewhat reasonable performance:

- CPU with 4 cores (8 threads) or more
- RAM of at least 8GB, 16GB or more preferred
- SSD disk IO wherever possible, or a high RPM (10K+) SAS/SATA spin drive
- At least 15Gb to 20GB of free disk space
- Network Speed, the higher the better, but 2Mbps to 4Mbps at a minimum.

## Major Components

While there are many tools and applications included in the `JTSDK64-Tools` kit, it is important to understand (at a high level) the primary environments used for setup, administration, and the building of artifacts; those being:

- [JTSDK64-Setup](#jtsdk64-setup) is an Windows/PowerShell environment
- [JTSDK64-Tools](#jtsdk64-tools) is an Windows/PowerShell environment
- [JTBuild](#jtbuild) is a PowerShell script used to compile WSJT-X
- [Qt Maintenance](#qt-maintenance) is an Windows application / component installer
- [MSYS2](#msys2) is an GNU/Unix style environment
- [Hamlib-Build](#hamlib-build-script) is a Bash script used in the MSYS2 environment to compile Hamlib

The following is a brief overview of each, and how they relate to the overall `JTSDK64-Tools` package.

### JTSDK64-Setup

The `JTSDK64-Setup` environment is used for initial installation and follow up modification(s) of major components that control what will eventually be used in to build artifacts (`WSJT-X`, `Hamlib`, `Boost`). By default, its display gives users a snapshot of their tool chain components (`Installed`, `Not Installed`). The setup environment also provides access to two key functions:

- Postinstall
- msys2

**`Postinstall`** is used for, as the name suggests, installing components after the `Base Installation`. The `postinstall` function downloads, installs and configures VS Redist, Qt, Git-SCM, VS Code, and MSYS2 in addition to checking the install status of critical components.

**`MSYS2`**, from within the `JTSDK64-Setup` environment, launches the shell for the first time in preparation for package updates, Hamlib dependency installation, Key Ring updates, and more.

Generally, `msys2` is launched from within `JTSDK64-Tools` environment where it receives path variables needed for compiling Hamlib. It provides access to hundreds, if not thousands, of GNU/Unix based applications in a robust `Bash` shell.

<figure>
  <img src="../images/0-overview-1.PNG" width=auto />
  <figcaption>JTSDK64-Setup After Full Installation</figcaption>
</figure>

### JTSDK64-Tools

**`JTSDK64-Tools`** is provides access to all tools and frameworks outside of the `MSYS2` ecosystem. It is used for, among other things, building `WSJT-X`, `JTDX`, `JS8CALL`. The main display gives user the status of all the major tool chain components in use and their version, where applicable. The three primary commands in this environment are:

- Deploy-Boost
- MSYS2 Environment
- JTBuild

**`Deploy-Boost`** is used for downloading `Boost` source code, compiling artifacts, and moving them into the `JTSDK64-Tools` folder structure for later use by `JTBuild`.

**`msys2`** is a shell command that will launch the `MSYS2` environment with critical path variables pointing to libraries such as `FFTW`, `Libusb` and tool chain components like GCC 5.12.10 [mingw73_64]. Many, but not all, are required for compiling Hamlib.

**`jtbild`** is a shell script that is used for building all facets of `WSJT-X` which include:

- Release Configuration, config only
- Debug Configuration, config only
- Release Install, Non-Package Install
- Debug Install, Non-Package Debug Enabled
- Package, Windows Installer
- Docs, the WSJT-X documentation

<figure>
  <img src="../images/0-overview-2.PNG" width=auto />
  <figcaption>JTSDK64-Tools After Full Installation</figcaption>
</figure>

### JTBuild

As mentioned previously, `jtbuild` is a Windows PowerShell script used to configure and compile `WSJT-X`. The invocation is run from within the `JTSDK64-Tools` environment. For a list of options, a simple help menu is provided:

```powershell
# In JTSDK64-Tools Environment, type:

jtbuild -h

```

<figure>
  <img src="../images/0-overview-3.PNG" width=auto />
  <figcaption>JTBuild Help Screen</figcaption>
</figure>

### Qt Maintenance

After initial setup, you will have an Windows application named `Qt Maintenance`. It's primary purpose is to manage (install/update/remove) pre-compiled components against varying GCC versions. It also keeps the component dictionary updated. When the `Qt` development team releases new artifacts, they will automatically be made available through the maintenance tool.

With the `Qt Maintenance` tool you can:

- Add or remove components
- Update components
- Remove all components (this is the preferred method of de-installation)

<figure>
  <img src="../images/0-overview-4.PNG" width=auto />
  <figcaption>Qt Maintenance Options</figcaption>
</figure>

Using the Drop-Down widgets, within the Add or Remove Components option, you can select what you want to manage.
In the figure below you can see that the installation has Qt 5.12.10 and Development Design tools installed.

<figure>
  <img src="../images/0-overview-5.PNG" width=auto />
  <figcaption>Qt Maintenance Add or Remove Components</figcaption>
</figure>

### MSYS2

>MSYS2 is a collection of tools and libraries providing you with an easy-to-use environment for building, installing and running native Windows software.
>
--<cite>[The MSYS2 Project](https://www.msys2.org/)</cite>

For the purposes os `JTSDK64-Tools`, we use `MSYS2` for compiling `Hamlib`, but that only scratches the surface of what it can to. In later sections of this guide we will explore it's capabilities in more detail, but for now, the screen shots below are what's of interest.

The main screen displays two important commands:

- menu
- jthelp

The **`menu`** option is where you will perform most of the setup and actions. The `MSYS2` section of the setup guide will go into more details.

```bash
# At the MSYS2 prompt, type:

menu

```

<figure>
  <img src="../images/0-overview-7.PNG" width=auto />
  <figcaption>MSYS2 Tools Main Menu</figcaption>
</figure>


The **`jthelp`** options will list the commands (scripts) made available via the `JTSDK64 Development Team`.

```bash
# At the MSYS2 prompt, type:

jthelp

```

<figure>
  <img src="../images/0-overview-6.PNG" width=auto />
  <figcaption>MSYS2 Help Information</figcaption>
</figure>

### Hamlib Build Script

For the most part, users have little to no interaction with this script other than running it from within `MSYS2`. However,
It's a vital component to the overall build for `WSJT-X`.

As shown in the [MSYS2](#msys2) section, using menu option (5) is all the user needs to produce ready-to-use Hamlib artifacts. More advanced options can and will be explored in later sections.

<figure>
  <img src="../images/5-Build-Hamlib-3.PNG" width=auto />
  <figcaption>Hamlib Finished Build</figcaption>
</figure>

<!-- Page URL Links -->
[WSJT-X]: http://physics.princeton.edu/pulsar/K1JT/wsjtx.html
[Hamlib]: https://github.com/Hamlib
[Boost]: https://www.boost.org/
[Qt]: https://www.qt.io/download
[The MSYS2 Project]: https://www.msys2.org/