# OMA-Masquerading-as-APT

**OMA-Masquerading-as-APT** is a patched version of [OMA](https://github.com/AOSC-Dev/oma), designed to bypass strict User-Agent checks in certain Debian-derived distributions by impersonating APT.

> **OMA** = **O**MA **M**asquerading as **A**PT

## 🧠 What is OMA?

[OMA](https://aosc.io/oma) (short for **Oh My Ailurus**) is a modern package management frontend designed for Debian-based distributions using `dpkg`. It is the default package management interface in [AOSC OS](https://aosc.io/), aiming to provide a more user-friendly, robust, and efficient experience than traditional APT tools.

Key features of OMA include:

- **Improved APT Interface**: Compatible with common APT workflows, but offers clearer guidance, simpler error messages, and a more streamlined command set.
- **Safer Operations**: Built-in guardrails, clear prompts, and undo functionality help users avoid damaging mistakes.
- **Better Network Performance**: Leverages HTTP/2 and multi-threaded downloads to accelerate package installation and updates.
- **Productivity-Oriented UX**: Combines powerful CLI and lightweight TUI interfaces for a clean and efficient system management experience.
- **System Integration**: Seamlessly integrates with AOSC OS features like testing channels and mirror list management for centralized control.
- **Cross-Distro Support**: Compatible with Debian, Ubuntu, Deepin, and other major `dpkg`-based systems.

For more details, visit the [official OMA website](https://aosc.io/oma) or the [upstream GitHub repository](https://github.com/AOSC-Dev/oma).


## 🚨 Why this fork?

On some Debian-derived systems, package repository servers **restrict access based on the User-Agent string** of the client. Only requests from official tools like `apt` are allowed. This behavior breaks OMA out-of-the-box, since it uses its own UA string.

This fork **modifies OMA's User-Agent to exactly mimic APT**, allowing it to bypass the whitelist and function normally with these repositories.

## 🔍 What's changed?

- The default User-Agent string sent by OMA has been changed to match:`Debian APT-HTTP/${oma_version}`

