# HSP for Windows

[**Download HSP 0.1.14 for Windows (64-bit)**](https://github.com/TorMaMe/hsp-downloads/releases/latest/download/HSP-Setup-x64.exe)

HSP listens through your PC's microphone, sends speech to the hosted transcription and inference service, and projects accepted scripture references and versions through VideoPsalm.

## What the church PC needs

- Windows 10 or 11, 64-bit.
- VideoPsalm **1.29**, with the Bible translations you want to use.
- An internet connection and an API key supplied privately by your HSP administrator.
- The external projection screen configured in VideoPsalm.

You do not need Rust, Python, Node.js, source code, or local model downloads.

## Install or update

1. Close HSP and run **HSP-Setup-x64.exe** using the same Windows account as before. It updates the existing installation and retains the saved API key; uninstalling is unnecessary.
2. Open **HSP** from the Start menu.
3. On first use, open **API settings**, paste your key, and click **Save API key**. The key is checked and saved using Windows-account encryption. It is not included in the download.

The installer includes the audio helper and installs WebView2 if it is missing.
The first service connection after idle can take longer while the models start.

## Listen and project

1. Open VideoPsalm, show its Bibles panel, and turn its **Project** icon on.
2. In HSP, click **Connect to VideoPsalm**.
3. Click **Start** and wait for listening status.
4. Speak naturally, for example: "Read John chapter three verse sixteen in New Living Translation."
5. HSP displays what it heard and automatically projects accepted scripture results.
6. Click **Stop** when finished. This stops microphone capture and discards waiting results without clearing the external display.

A projection already underway may finish after Stop. Closing HSP also stops its audio helper.
The default Windows microphone is used. Audio is uploaded while listening; this app does not save recordings or play audio.
The shared service permits one active live-audio session at a time.

## Manual text

While listening is stopped, you can type a reference, quotation, or passage description into **Manual text**, then click **Project**.
Later text such as "Use Amplified" can update the last projected verse.

## Errors and versions

- Projection errors appear in the UI while listening continues. The next accepted result is processed, and a successful projection clears the error.
- Invalid individual scripture results are skipped. Failed or partial mouse actions are not automatically replayed.
- If the microphone, network connection, or audio helper actually stops, address the displayed error and click **Start** for a fresh session.
- HSP projects one verse at a time. A new scripture defaults to KJV unless another version is requested; later translation requests can update it.
- The exact requested Bible version must be installed in VideoPsalm. KJV does not select NKJV; NLT does not substitute NLT15 or NLT2007.
- If VideoPsalm restarts, stop listening and click **Connect** again.
- Check the external screen to confirm audience output. The displayed timings do not measure the external monitor's rendering.

Use the same Windows permission level for HSP and VideoPsalm. If VideoPsalm is running as administrator, ordinary HSP input may be blocked.

## Download details

The installer is unsigned, so Windows may show an unknown-publisher or SmartScreen prompt.
Download from this repository. Each release includes **SHA256SUMS.txt** for verification:

```powershell
Get-FileHash .\HSP-Setup-x64.exe -Algorithm SHA256
```

Compare the hash with that release's installer entry in SHA256SUMS.txt.

This repository contains downloads and usage instructions. Application source and API credentials are not included.
