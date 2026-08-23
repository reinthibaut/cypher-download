# Cypher App — Download

Write secret messages that only the people with your key can read.

**→ [Download page](https://reinthibaut.github.io/cypher-download/)**

> **Version 2 is not compatible with version 1.** Messages written in one cannot be read by
> the other, so everyone writing to each other has to update at the same time and use a new key.

Or grab the installer directly:

- **Windows** — [CypherApp-Setup.exe](https://github.com/reinthibaut/cypher-download/releases/latest/download/CypherApp-Setup.exe) (~80 MB, Windows 10 and 11, 64-bit) — version 2.0.0
- **Mac** — [CypherApp.dmg](https://github.com/reinthibaut/cypher-download/releases/latest/download/CypherApp.dmg) (~170 MB, macOS 11+, Apple Silicon and Intel) — version 2.0.0
- **Linux** — [CypherApp.AppImage](https://github.com/reinthibaut/cypher-download/releases/latest/download/CypherApp.AppImage) (any distro, no install) or
  [CypherApp.deb](https://github.com/reinthibaut/cypher-download/releases/latest/download/CypherApp.deb) (Ubuntu, Mint, Debian)

Linux has no SmartScreen or Gatekeeper equivalent, so there are no security warnings to click
through. For the AppImage you may need to mark it executable first — `chmod +x CypherApp.AppImage`,
or right-click → Properties → *Allow executing file as program*.

## Windows will show a warning — that's expected

When you open the file, Windows shows a blue box:

> **Windows protected your PC**
> Microsoft Defender SmartScreen prevented an unrecognised app from starting.

This happens to every program that hasn't been registered with Microsoft, which costs money
and isn't worth it for a small app like this one. To continue:

1. Click **More info** — the small grey text in that blue box
2. Click **Run anyway** — the button that appears at the bottom
3. The normal installer opens; click through it as usual

If you'd rather not, just ask Rein to install it for you.

## On a Mac, it takes a few more steps

Apple blocks apps that aren't registered with them, and won't let you click straight
through like Windows does.

1. Open the `.dmg` and drag **Cypher App** into **Applications**
2. Open **Applications** and double-click **Cypher App** — macOS will refuse:
   > **"Cypher App" Not Opened** — Apple could not verify "Cypher App" is free of malware
   > that may harm your Mac or compromise your privacy.
3. Click **Done**. It has to be refused once before Apple lets you allow it.
4. Open **System Settings** → **Privacy & Security**
5. Scroll to the bottom, to **Security**. Click **Open Anyway** next to "Cypher App was
   blocked to protect your Mac."
6. Enter your Mac password, then click **Open Anyway** again

You only do this once. After that it opens like any other app.

**On macOS Sonoma and earlier** it's quicker: right-click the app → **Open** → **Open**.
Apple removed that shortcut in newer versions.

## You'll also need a key and a password

The app on its own can't read anything. It needs two shared secrets, and both people must
have exactly the same ones:

- **The key** — a small `.json` file, like a codebook. Rein sends you this once.
- **The password** — a word or phrase you agree on together. It decides how the code
  scrambles, so the same message with a different password comes out completely differently.

To load the key file:

1. Save the file somewhere you'll find it again
2. Open Cypher App and click the **Key** tab at the top
3. Click **Import Key from File** and pick the file you saved

The password isn't stored anywhere — you type it in each time. **Never write the password
inside the letter**, and don't send it in the same message as the key file.

## Is this safe?

It's a personal project, not a commercial product. It runs entirely on your own computer —
nothing you type is uploaded, there's no account, and it needs no internet connection.
Your keys and messages are stored only on your own machine.

## Uninstalling

**Windows** — **Settings** → **Apps** → **Cypher App** → **Uninstall**.

**Mac** — open **Applications**, drag **Cypher App** to the Bin, empty the Bin. Macs have no
uninstaller; dragging it away is the normal way to remove an app.

Either way your keys are **not** deleted — they're kept separately, so reinstalling picks up
where you left off. To wipe them too:

- **Windows** — <kbd>Win</kbd>+<kbd>R</kbd>, paste `%APPDATA%\cypher-app`, Enter, delete the folder
- **Mac** — in Finder press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>G</kbd>, paste
  `~/Library/Application Support/cypher-app`, Enter, drag the folder to the Bin

That erases your keys permanently. Export any key you still need from the **Key** tab first.

---

This repository contains only the installer and this page. The app's source code is private.
