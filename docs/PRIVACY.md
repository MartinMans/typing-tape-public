# Privacy and your data

Short version: Typing Tape has no accounts, no cloud sync, no ads, no analytics and no
telemetry. It does not connect to the internet. Everything it saves stays on your PC.

## What Typing Tape saves

| Data | Why |
| --- | --- |
| Your finished rounds: date and time, words per minute, accuracy, errors, words, round length and the options you used | The results screen, your best score and the analytics chart |
| Your menu choices: volume, view (Standard or Focus), round length, text kind, mistake mode, covered words | Volume and view are restored next time; the other choices are stored alongside them but reset to their defaults every time the app starts |
| A list of recently shown sentences (numbers, not the text) | So the same sentences do not come back soon |
| Only if saved history is ever found damaged: a backup copy of it | So it can be recovered by hand instead of being overwritten |

Typing Tape does not save the text you type, keystroke timings, or anything about your PC.

## Where it is saved

In your Windows user profile, in the folder:

```
%LOCALAPPDATA%\com.martin.typingtape
```

The data is kept in the local storage of the app's own WebView2 profile inside that folder
(`EBWebView`). Both the installed and the portable version use this folder. Other Windows
users on the same PC have their own, separate folder.

## Network use

- **The app.** Typing Tape makes no network connections. Its content security policy only
  allows it to load its own built-in files, and it contains no update checker, crash reporter
  or analytics.
- **The installer.** If the Microsoft Edge WebView2 Runtime is missing (it is part of Windows
  11), the installer downloads it from Microsoft. On a PC that already has it, the installer
  does not need the internet.
- **WebView2.** Typing Tape draws its window with the WebView2 Runtime, a Windows component
  made and updated by Microsoft. That component is covered by Microsoft's own privacy terms,
  not by Typing Tape.

Typing Tape works fully offline.

## Deleting your data

- **Analytics only:** in the app, open **Analytics** and use **Reset analytics** (click it
  twice to confirm). This deletes your round history. Your volume, view and the sentence list
  are kept.
- **Everything, when uninstalling:** tick **"Also delete my saved history and settings (cannot
  be undone)"** in the uninstaller. This deletes the whole folder above.
- **Everything, by hand:** close Typing Tape, then delete the folder above. The portable version
  has no uninstaller, so this is the way to remove its data.

A normal uninstall, an update and a reinstall all keep your data.

## Contact

Questions about privacy can be asked through the
[issue tracker](https://github.com/MartinMans/typing-tape-public/issues). Do not post personal
information there; issues are public.
