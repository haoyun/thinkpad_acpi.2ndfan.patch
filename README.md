# Thinkpad ACPI 2nd fan control patch

Forked from: https://github.com/civic9/thinkpad_acpi.2ndfan.patch  
Updated with patch from github user: lhofhansl  
Based on patches found in discussion: https://github.com/vmatare/thinkfan/issues/58  
Credits where credits are due: https://github.com/civic9/thinkpad_acpi.2ndfan.patch/issues/4

Patch for vanilla Linux kernel 5.4.28, 5.5.13 (tested) to enable 1nd and 2nd fan as a single unit.

2nd fan control is enabled for these models (bios version prefix):
- Thinkpad P50 (N1E)
- Thinkpad P51 (N1U)
- Thinkpad P52 (N2C)
- Thinkpad P70 (N1D)
- Thinkpad P71 (N1T)
- Thinkpad P72 (N2C)
- Thinkpad P1 1st gen (N2E)
- Thinkpad X1 Extreme 1st gen (N2E)
- Thinkpad P1 2nd gen (N2O)
- Thinkpad X1 Extreme 2nd gen (N2O)

You can add other models/prefixes in fan\_quirk\_table. Let me know if you know another thinkpad model with 2nd fan which should be separately controlled, so I can add it to the list. 

Patch in the file thinkpad\_acpi.2ndfan.patch. 

build\_install.sh is a helper script for Arch Linux to download the kernel sources, patch it, make and install module. Don't use without inspecting it and understanding what it does. The script probably won't be working on another distro.

The patch works with default thinkfan settings:
fan control in /proc/acpi/ibm/fan.
temperature inputs in /proc/acpi/ibm/thermal.
