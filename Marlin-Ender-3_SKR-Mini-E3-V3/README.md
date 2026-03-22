# Marlin Ender 3 SKR Mini E3 V3 Configuration

This directory contains the modified `Configuration.h` and `Configuration_adv.h` files for Marlin firmware, tailored for _my_ Ender 3 using with a SKR Mini E3 V3.0 board.  These files should be used by copying them into the github.com/MarlinFirmware/Marlin/Marlin directory, replacing the existing files.  Read the comments below for details on how this repository uses branching and tagging go manage these files.  _The `main` branch **does not** contain the correct files._  Use the tagged version with my username, `vW.X.Y.Z_egustafson` to get my printer specific configuration files.

### Version Control Strategy

The `main` branch of this repository holds direct copies of the configuration files as taken from [github.com/MarlinFirmware/Configurations/config/examples/Creality/Ender-3 Pro/BigTreeTech SKR Mini E3 3.0](https://github.com/MarlinFirmware/Configurations/tree/import-2.1.x/config/examples/Creality/Ender-3%20Pro/BigTreeTech%20SKR%20Mini%20E3%203.0) on the appropiately versioned branch.  The `main` branch holds direct copies from the example configuration files and is tagged with the same tag as used in the "Configurations" repository.

_Customization Branch_:  The changes made for my specific printer configuration are made as a branch off of the `main` branch and are tagged as `vW.X.Y.Z_egustafson` where `W.X.Y.Z` is the same version as the `main` branch.  This allows me to easily track changes in the example configuration files and merge them into my customized branch as needed.

### Updating to a New Version of Marlin

1. Check out the `main` branch.
2. Copy the new `Configuration.h` and `Configuration_adv.h` files from the appropriate version in the Marlin Configurations repository (linked above) into the `main` branch, replacing the existing files.
3. Commit the changes to the `main` branch with a message indicating the update (e.g., "Update to Marlin v2.1.0").
4. Tag the `main` branch with the same tag as used in the Marlin Configurations repository (e.g., `release-2.1.2.7`).
5. Create a new branch from the `main` branch for your custom configuration (e.g., `b2.1.2.7`).
6. Merge, cherry-pick, or manually apply the necessary changes from the `main` branch to your custom branch.
7. Commit the changes to the custom branch with a message indicating the update (e.g., "Merge Marlin v2.1.0 changes into custom configuration").
8. Tag the custom branch with the appropriate tag (e.g., `v2.1.2.7_egustafson`).

### Using the Configuration Files

After updating the configuration files, copy them manually into the `Marlin` directory of the Marlin firmware source code, replacing the existing `Configuration.h` and `Configuration_adv.h` files. Then compile and upload the firmware to your printer as usual.

### `STM32G0B1RE_btt` vs `STM32G0B1RE_btt_xfer` Images

The `STM32G0B1RE_btt` image creates a `firmware.bin` file that can be directly copied to the SD card for flashing the SKR Mini E3 V3.0 board.  The `STM32G0B1RE_btt_xfer` image is used for remote/USB based firmware flashing from the OctoPrint controller.  Additional changes must be made in the `Configuration_adv.h` to enable this process.
