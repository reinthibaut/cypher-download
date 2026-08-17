# Cypher App — Download

Write secret messages that only the people with your key can read.

**→ [Download page](https://reinthibaut.github.io/cypher-download/)**

Or grab the installer directly:

- **Windows** — [CypherApp-Setup.exe](https://github.com/reinthibaut/cypher-download/releases/latest/download/CypherApp-Setup.exe) (~80 MB, Windows 10 and 11, 64-bit)
- **Mac** — [CypherApp.dmg](https://github.com/reinthibaut/cypher-download/releases/latest/download/CypherApp.dmg) (~170 MB, macOS 11+, works on Apple Silicon and Intel)

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

## You'll also need a key

The app on its own can't read anything. A **key** is the shared secret that makes your
messages match up — two people can only read each other's messages if they have the exact
same key.

Rein will send you a small `.json` key file. To load it:

1. Save the file somewhere you'll find it again
2. Open Cypher App and click the **Key** tab at the top
3. Click **Import Key from File** and pick the file you saved

## Is this safe?

It's a personal project, not a commercial product. It runs entirely on your own computer —
nothing you type is uploaded, there's no account, and it needs no internet connection.
Your keys and messages are stored only on your own machine.

## Uninstalling

Windows **Settings** → **Apps** → **Cypher App** → **Uninstall**.

---

This repository contains only the installer and this page. The app's source code is private.
