# dm3k Retro Labs

A collection of automation utilities for maintaining, provisioning, and managing storage for vintage computing hardware.

Currently focused on **Classic Macintosh** and **Vintage PC** workflows.

## 🛠 Active Tools

### BlueSCSI v2 SD Card Prep (`BlueSCSI_Prep.py`)
**Current Version:** v1.0.0

A utility to automate the provisioning of MicroSD cards for BlueSCSI v2 devices. It handles filesystem formatting and generates pre-allocated blank hard drive images optimized for vintage Mac use.

**Features:**
* **Automated Formatting:** Formats target SD cards to exFAT to support files larger than 4GB.
* **Directory Structure:** Automatically creates the `CD2` and `CD4` directories for ISO mounting.
* **Disk Image Generation:** Creates pre-sized `.hda` disk images with specific SCSI ID assignments:
    * `ID 0`: 4GB Fixed (System/Boot)
    * `ID 1`: 4GB Fixed (Applications)
    * `ID 3`: User-selectable size (4GB–30GB) for Data/Games

**Usage:**
1.  Run the script as Administrator (required for disk formatting) on Windows 10/11.
2.  Follow the prompts to select your SD card drive letter.
3.  Specify the desired size for the Data Drive (ID 3).

**Post-Install (Mac OS 8.x):**
Once the card is prepared, boot your Macintosh. Use "Drive Setup" to initialize the new drives.
* **ID 0 & 1:** Format as Mac OS Standard (HFS).
* **ID 3:** Format as Mac OS Extended (HFS+) for storage efficiency.

## 📋 Requirements
* Windows 10 or 11
* Python 3.x
* Administrator privileges

## ⚠️ Warning
The provisioning scripts perform disk formatting. **All data on the target drive will be permanently erased**. Always verify your drive letters before confirming execution.

## 📜 Version History
* **v1.0.0** - Initial Release.
