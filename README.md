# 🍀[KISS Linux](https://k1ss.org/) for users of the Intel GMA3600/GMA3650 Cedarview GPU

This repo has one goal:
 * To keep the original binary driver for the Cedarview platform working.

All while:
 * Keeping the rest of the system packages (that don't need to be held back) up-to-date.

These packages that need to be held back, patched or modified are what is situated in this repo.
The most notable of them are:
 * __Mesa__ (v7.11) - required by `cedarview-userspace`
 * __Xorg__ (1.11) - required by `cedarview-userspace`
 * __Linux__ (3.2) - again, `cedarview-userspace`
 * __Udev__ (173) - required by Linux 3.2 (due to buggy firmware loading)
 * __Glibc__ (2.24) - required by Linux 3.2 (due to missing getrandom() syscall)
 * __mesa-demos__ (8.1) - required by Mesa (insufficient symbols)

Full information on these system requirements are documented here:
* [https://www.intel.com/content/dam/support/us/en/documents/motherboards/desktop/sb/enabling_hardware_accelerated_playback_fedora_16_v.pdf](https://www.intel.com/content/dam/support/us/en/documents/motherboards/desktop/sb/enabling_hardware_accelerated_playback_fedora_16_v.pdf)

![scrot](https://github.com/arvl130/kiss32-cdv-repo/blob/master/scrot.png)

This project is mostly a test on how far we can push outdated kernels to run current software.
It should not be used for anything mission-critical or security-related.

For most people, using the upstream driver should be enough as it already provides a good-enough experience with resolutions (up to 1080p) and video playback (480p, maybe 720p).

However, if you're interested in getting 1080p playback working again in these devices.
This repo might be something you'll find useful.

# Installation

The chroot script and tarball can be downloaded from the [Releases](https://github.com/arvl130/kiss32-cdv-repo/releases) page of this respository.

General instructions on how to install can be found on the upstream KISS website: [https://k1ss.org/install](https://k1ss.org/install)
