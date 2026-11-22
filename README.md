# HSP for Windows

[**Download HSP for Windows (64-bit)**](https://github.com/TorMaMe/hsp-downloads/releases/latest/download/HSP-Setup-x64.exe)

HSP uses hosted Qwen to interpret a scripture request, Bible quotation, or Biblical-event description, then projects the reference and requested version through VideoPsalm.

## What the church PC needs

- Windows 10 or 11, 64-bit.
- VideoPsalm **1.29**, installed separately, with the Bible translations you want to use.
- An internet connection and an API key supplied privately by your HSP administrator.
- The external projection screen configured in VideoPsalm.

You do not need Rust, Python, Node.js, the source code, or local inference models.

## Install and set up

1. Download and run **HSP-Setup-x64.exe**. The installer installs HSP for your Windows account and handles WebView2 if it is missing.
2. Open **HSP** from the Start menu.
3. On first launch, paste your API key into **API settings** and click **Save API key**. The app checks the key and saves it with Windows-account encryption. The key is not included in this download.
The first API connection after idle can take a few minutes while the model starts.

4. Open VideoPsalm, show its Bibles panel, and turn its **Project** icon on.
5. In HSP, click **Connect to VideoPsalm**.
6. Enter text such as “Please show John 3:16 in NLT” and click **Project**.

Use the same Windows permission level for HSP and VideoPsalm. If VideoPsalm is running as administrator, ordinary HSP input may be blocked.

## Current scope

- This build projects one verse at a time.
- The requested Bible version must be installed in VideoPsalm. Without an explicit version, inference defaults to KJV.
- **Start/Stop** captures the microphone and shows its level. It does not transcribe audio or trigger automatic speech projection in this build.
- The result shows inference and VideoPsalm timing. Check the external screen to confirm audience output.
- If VideoPsalm restarts, click **Connect** again.

## Download details

The installer is currently unsigned, so Windows may show an unknown-publisher or SmartScreen prompt. Check that you downloaded it from this repository. Each release includes **SHA256SUMS.txt** for integrity verification.

To check a downloaded installer in PowerShell:

```powershell
Get-FileHash .\HSP-Setup-x64.exe -Algorithm SHA256
```

Compare the hash with the installer entry in that release's SHA256SUMS.txt.

This repository contains Windows downloads and usage instructions. Application source and API credentials are not included.

## Updating HSP

Close HSP and run the latest installer using the same Windows account. It updates the existing installation and retains the saved API key. You do not need to uninstall first.

If HSP says to check the external display after interrupted activation verification, projection may already be visible. HSP stops further clicks and never replays a partial click automatically.
