# PocketShell

An iPhone-first, dark terminal app prototype inspired by MSYS2.

## Current prototype

- SwiftUI terminal interface with command history and a monospace display
- A small, sandboxed built-in command interpreter: `help`, `pwd`, `ls`, `cd`, `echo`, `cat`, `mkdir`, `touch`, `clear`, and `whoami`
- Files stay inside the app's Documents directory
- No jailbreak, root access, or access to iOS system files

## Important limitation

This prototype is **not yet MSYS2, Bash, or a Linux distribution**. iOS does not let an ordinary app launch an unrestricted system shell or run arbitrary native executables. To reach the full goal, the next major step is integrating an iOS-compatible userland/runtime (for example, studying the open-source iSH project and its license/architecture) and packaging it for sideloading.

## Open in Xcode

1. On a Mac with Xcode installed, create a new iOS App project named `PocketShell` using SwiftUI.
2. Set the deployment target to iOS 16 or later.
3. Add `PocketShellApp.swift`, `TerminalView.swift`, and `ShellEngine.swift` from this folder to the app target.
4. Choose your own signing Team under **Signing & Capabilities**.
5. Build to a connected iPhone, or Archive and export using your own signing setup.

## Sideloading

An IPA must be signed for your device. This repository does not contain a signed IPA or signing credentials. You can use Xcode with your Apple ID, or a compatible sideloading workflow such as AltStore/Sideloadly. Never commit Apple signing certificates, private keys, or passwords.

## Security

Commands are implemented in Swift and operate only in the app's Documents directory. This is intentionally a safe starter, not an arbitrary-code execution environment.
