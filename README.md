# [KISS Linux](https://k1ss.org/) for users of the dreaded _Intel GMA3600_ and _GMA3650_ (Cedarview) 🍀 GPU

This repo has one goal:
 * To keep the original binary driver for the Cedarview platform working.

All while:
 * Keeping the rest of the system packages (that don't need to be held back) up-to-date.

These packages that need to be held back, patched or modified are
what is situated in this repo. The most notable of them are:
 * __Mesa__ (v7.11) - required by `cedarview-userspace`
 * __Xorg__ (1.11) - required by `cedarview-userspace`
 * __Linux__ (3.2) - again, `cedarview-userspace`
 * __Udev__ (173) - required by Linux 3.2 (because of buggy Wi-Fi firmware loading)
 * __Glibc__ (2.24) - required by Linux 3.2 (due to missing getrandom() syscall)
 * __mesa-demos__ (8.1) - required by Mesa (insufficient symbols)

Full information on these system requirements are documented here:
* [https://www.intel.com/content/dam/support/us/en/documents/motherboards/desktop/sb/enabling_hardware_accelerated_playback_fedora_16_v.pdf](https://www.intel.com/content/dam/support/us/en/documents/motherboards/desktop/sb/enabling_hardware_accelerated_playback_fedora_16_v.pdf)

Put simply, what we're basically trying to do is replicate the system described in the documentation
to have a reasonably working hardware acceleration. Then from there, we update the components of the
system that do not contribute, hinder, or affect that acceleration. So that while certain components
of the system are forever extremely out-of-date, certain other essential things (like games, browsers,
and certificates) are kept up-to-date (and working!). Granted, this project is still
__Work-in-Progress__ so you may only use it at your _own risk_!

Needless to say, if you ever manage to make any developments to this front, feel free to [submit a PR](https://github.com/arvl130/kiss32-cdv-repo/pull/new/master) as those are very much welcome.

There's only very few of us still using this hardware as it stands ([that's why we never got an open source VA-API driver!](https://www.phoronix.com/scan.php?page=news_item&px=MTAxMTA)).
So we have to stick together and help each other if we ever want this hardware kept completely working and free of headaches!
