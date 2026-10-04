# gf — Gefüge CLI

gf connects people and agents to the tools of a Gefüge instance. A person signs in once on their computer; subsequent commands use the permissions of that person.

This repository distributes binaries and installation information. It does not contain the Gefüge Core source code.

## Downloads

Versioned binaries and SHA-256 checksums are published under [Releases](https://github.com/gefuege/gf/releases). If no release is listed, the first release is still being prepared.

- macOS, Apple Silicon and Intel: Developer ID signed and notarized DMG.
- Windows x64: portable ZIP containing `gf.exe`, initially without an Authenticode signature.
- Linux x64: tar.gz containing `gf`.

After the first release is published, the macOS package is installed through the existing Homebrew tap:

```sh
brew install --cask sebastian-breitzke/tap/gf
brew upgrade --cask gf
```

The Windows release includes a WinGet manifest. Availability through the public WinGet catalog requires a separate accepted submission; a downloadable manifest alone does not mean that submission is complete.

## Use

```sh
gf login https://your-instance.example
gf status
gf tool list
gf tool show <tool-name>
```

Login opens a browser and is completed by a person. Login data stays in the macOS Keychain, Windows Credential Manager, or Linux kernel keyring. Linux kernel-keyring credentials do not survive a reboot.

If an earlier manual installation is already on your PATH, check `which gf` (macOS/Linux) or `Get-Command gf` (PowerShell) after installation to confirm which executable is being used.
