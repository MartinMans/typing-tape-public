# Installing Typing Tape

## Requirements

- Windows 11, 64-bit. Windows 10 (64-bit) is expected to work but has not been tested.
- The Microsoft Edge WebView2 Runtime. It is already part of Windows 11. If it is missing,
  the installer downloads it from Microsoft; the portable version needs it to be present.
- No administrator rights.

## Which download?

| File | Use it if |
| --- | --- |
| `Typing-Tape_1.0.0_x64-setup.exe` | You want a normal install with a Start Menu entry and an uninstaller. Recommended. |
| `Typing-Tape_1.0.0_x64-portable.zip` | You do not want to install anything, or want to run it from a folder of your choice. |
| `SHA256SUMS.txt` | You want to check that your download is complete and unchanged. |

All three are on the [Releases page](https://github.com/MartinMans/typing-tape-public/releases/latest).

## Unsigned download warnings

Typing Tape is not code-signed. Windows may warn you or block it:

- **SmartScreen** may show "Windows protected your PC". Choose **More info**, then
  **Run anyway**, if you trust the download (check its checksum first, see below).
- **Smart App Control**, when it is turned on, may block unsigned apps outright. There is no
  "run anyway" option for that; Typing Tape cannot be guaranteed to run on such a PC.
- Antivirus software may also ask before running a new, unsigned program.

Whether a warning appears depends on your Windows settings and on Microsoft's reputation
services, so it can differ from one PC to another.

## Check the download (optional)

Each release lists the SHA-256 checksum of both files in `SHA256SUMS.txt`. In PowerShell, in
the folder where you saved the file:

```powershell
Get-FileHash -Algorithm SHA256 .\Typing-Tape_1.0.0_x64-setup.exe
```

The `Hash` shown must match the line for that file in `SHA256SUMS.txt` (case does not matter).
If it does not match, delete the file and download it again.

## Install

1. Run `Typing-Tape_1.0.0_x64-setup.exe`.
2. Follow the wizard. Typing Tape installs for your Windows user account only, into
   `%LOCALAPPDATA%\Typing Tape`; other users of the PC are not affected.
3. On the last page you can tick **Create desktop shortcut** and start the app.

Typing Tape then appears in the Start Menu and in **Settings > Apps > Installed apps**.

### Silent install

For scripted installs:

```
Typing-Tape_1.0.0_x64-setup.exe /S
```

To choose the folder, add `/D=C:\Path\To\Folder` as the last argument, without quotes.

## Start the app

Open **Typing Tape** from the Start Menu, or from the desktop shortcut if you created one.
Only one copy runs at a time: starting it again brings the open window to the front.

## Portable version

1. Unzip `Typing-Tape_1.0.0_x64-portable.zip` to any folder you can write to.
2. Run `Typing Tape\Typing Tape.exe`.

Nothing is installed or registered, and there is no Start Menu entry or uninstaller. The
portable version still saves its history and settings in the same place as the installed one
(`%LOCALAPPDATA%\com.martin.typingtape`, see [PRIVACY.md](PRIVACY.md)), not next to the exe,
so the two share their data.

## License and notices

The Typing Tape license is in `LICENSE.txt`. Typing Tape includes open-source components;
their license notices are in `THIRD-PARTY-NOTICES.txt`. Both files are installed next to
`typing-tape.exe` in the install folder (the uninstaller removes them) and are included in the
portable ZIP, in the `Typing Tape` folder next to `Typing Tape.exe`. The same files are in this
repository.

## Updating

Typing Tape does not update itself and does not check for updates. To update, download the
newer installer from the Releases page and run it over the existing installation. Your history
and settings are kept. For the portable version, replace the folder with the new one.

## Uninstall

**Settings > Apps > Installed apps > Typing Tape > Uninstall.**

The uninstaller asks whether to delete your data:

- **Leave the box unticked** (the default) to keep your history and settings. If you install
  Typing Tape again later, they come back.
- **Tick "Also delete my saved history and settings (cannot be undone)"** to remove them as
  well.

Silent uninstall: `"%LOCALAPPDATA%\Typing Tape\uninstall.exe" /S`, and add `/DELETEUSERDATA`
to delete the data too.

After a normal uninstall that keeps your data, a small registry entry that records the install
folder (`HKCU\Software\Martin\Typing Tape`) is also left behind. It is removed when you choose
to delete your data.

### Portable version

Delete the folder you unzipped. To remove your saved data as well, delete
`%LOCALAPPDATA%\com.martin.typingtape` while Typing Tape is closed. To open that folder, paste
the path into the address bar of File Explorer or into **Win+R**.
