# SinghFlow for Mac

Dictation for macOS: hold a key, speak, and the text is typed where your cursor is. Speaks English and Punjabi (written in Gurmukhi). It can also record meetings and write notes.

This repository holds only the Mac downloads. The source code is private.

## Download

Get the `.dmg` from the [latest release](https://github.com/singhparveen/SinghFlow-releases/releases/latest).

Needs macOS 15 Sequoia or later, on Apple Silicon or Intel.

## Install

1. Open the `.dmg` and drag **SinghFlow** into **Applications**.
2. The app is signed but not notarized by Apple, so macOS blocks the first launch:
   - Open SinghFlow from Applications. When macOS says it cannot verify the app, click **Done**.
   - Open **System Settings > Privacy & Security**, scroll down and click **Open Anyway** next to SinghFlow.
   - Confirm with your password or Touch ID. After this it opens normally.
3. Allow **Microphone**, and switch SinghFlow on under **System Settings > Privacy & Security > Accessibility** so it can type into other apps.

**Read me first.txt** inside the disk image has the full steps.

## Azure

SinghFlow sends your speech to your own Azure resources. You need:

- An **Azure AI Speech** resource (for MAI-Transcribe).
- An **Azure OpenAI** resource with three deployments: `gpt-4o-transcribe` (backup transcription), `gpt-5.4-mini` (cleanup) and `gpt-4.1` (meeting notes).

In SinghFlow, click the menu bar icon > **Settings > Azure**, enter each resource's address and key, and change the deployment names if yours differ. Keys are stored in your Keychain only.

## Without Azure

Without Azure keys, only English dictation works, and only on macOS 26:

- In **Models & Cost**, set Transcription to **Apple on-device**. The speech stays on your Mac. Names and technical terms come out less accurately.
- Set Cleanup to **Apple Intelligence**. This needs Apple Intelligence turned on in System Settings. Otherwise your words are typed as heard, with no cleanup.

These need Azure:

- Punjabi dictation. Apple's on-device speech has no Punjabi, so Punjabi speech comes out in English letters, not Gurmukhi.
- Polish and Prompt Engineer (rewriting selected text).
- Meeting transcripts and notes.
- Everything on macOS 15.

## Use it

- Hold **Control + Option + Space**, speak, release: the text goes where your cursor is.
- Tap the shortcut once for hands-free listening; tap again to finish, **Esc** to cancel.

## Remove it

Quit SinghFlow from its menu bar panel, delete it from Applications, and delete `~/Library/Application Support/SinghFlow`.
