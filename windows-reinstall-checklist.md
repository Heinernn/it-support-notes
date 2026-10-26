# Windows reinstall checklist

Use it when a computer cannot be repaired in a reasonable time. The order matters: protect the data first.

## Before you start

- [ ] Ask the user what must be kept (documents, desktop, browser bookmarks, email, license keys).
- [ ] Copy the user data to an external drive or network share and check that the files open.
- [ ] Note the installed programs and the licenses that must be re-entered.
- [ ] Check the Windows license is tied to the device (look in Settings > System > Activation).
- [ ] Download the drivers for the model in advance (network and chipset first), in case the installer does not
      detect them.

## Installation

1. Create the installation USB with Microsoft's Media Creation Tool.
2. Boot from the USB (boot menu key depends on the brand: F12, F10, Esc, F2...).
3. Choose a **custom install** and delete or format only the system partition. Do not touch the data drive if there is one.
4. Finish the setup. Create the local or organisation account the user will use.

## After installing

- [ ] Run Windows Update until it has nothing left to install.
- [ ] Install the drivers that Windows did not find (check Device Manager for yellow marks).
- [ ] Install the antivirus or security tool used by the organisation.
- [ ] Install the user's programs (Office, browser, PDF reader, VPN, the line-of-business apps).
- [ ] Reconnect printers and shared folders.
- [ ] Restore the user's data and check permissions.
- [ ] Rename the computer following the naming rule and join it to the domain if needed.

## Handover

- [ ] Sit with the user and test the things they use every day.
- [ ] Explain what changed.
- [ ] Record in the ticket: date, backup location, what was installed and any pending item.
- [ ] Keep the backup for the agreed time before deleting it.
