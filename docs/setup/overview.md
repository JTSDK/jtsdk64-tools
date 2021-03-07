# Setup Overview

This section will walk users through (step-by-step) the process of installing all required components for compiling [Hamlib], [Boost], and finally  [WSJT-X][]. If you follow this guide you should have a working [WSJT-X] package that can be installed upon completion.

It is highly recommended that users `uninstall` all previous JTSDK components before using this guide. There are ways to work around this requirement, however, it can be tedious and error prone. For the best results, a clean install is the development teams recommendation.

## Installation Order

While some areas can be skipped, or added later, this guide--and this authors personal recommendation--will proceed in the order listed. Advanced users may elect to move through the order as they see fit, however, be aware of the limitation and potential for issues in doing so.

## Living Document

Many sections of this site are `under construction`. As new content is made available it will be added to the site after review. All content will remain relevant to the latest release of the `JTSDK64-Tools v3.2.x Stream`. Any Change to the Major or Minor version schema will result in a tag of the existing main branch and migration to the next release.

## Preferred Environment

If and where possible, users should first install `JTSDK64-Tools` in a Virtual Machine (VM). While the process aims to prevent unforeseen events to the users main system, there is always the potential for issues to arise, thus, using a VM will help mitigate such risk.

## System Requierments

There is no question, the more system resources (CPU cores, RAM, Disk IO, Network Speed, etc) the compiling system has, the better the overall performance will be. Completion times, based on a number of end-user reports, have ranged from `2.5 hours` to a `full day`, so plan accordingly.

By far, the most time intensive elements for the the entire setup process is related to downloading installing [Qt][], followed by a lengthy compile time for [Boost][].

While one can get away with a small commodity-based computer for development work, the following would be a safe-minium for those wanting somewhat reasonable performance:

- CPU with 4 cores (8 threads) or more
- RAM of at least 8GB, 16GB or more preferred
- SSD disk IO wherever possible, or a high RPM (10K+) SAS/SATA spin drive
- At least 15Gb to 20GB of free disk space
- Network Speed, the higher the better, but 2Mbps to 4Mbps at a minimum.

[WSJT-X]: http://physics.princeton.edu/pulsar/K1JT/wsjtx.html
[Hamlib]: https://github.com/Hamlib
[Boost]: https://www.boost.org/
[Qt]: https://www.qt.io/download