# OMA-Masquerading-as-APT

**OMA-Masquerading-as-APT** is a patched version of [OMA](https://github.com/AOSC-Dev/oma), designed to bypass strict User-Agent checks in certain Debian-derived distributions by impersonating APT.

> **OMA** = **O**MA **M**asquerading as **A**PT

## 🧠 What is OMA?

OMA (One Manager for All) is a universal package manager frontend developed by the [AOSC](https://aosc.io/) community. It provides a simplified interface for managing software across various package managers and platforms, aiming to be both powerful and user-friendly.

More information about the original OMA can be found at the [official OMA page](https://aosc.io/oma) and its [GitHub repository](https://github.com/AOSC-Dev/oma).

## 🚨 Why this fork?

On some Debian-derived systems, package repository servers **restrict access based on the User-Agent string** of the client. Only requests from official tools like `apt` are allowed. This behavior breaks OMA out-of-the-box, since it uses its own UA string.

This fork **modifies OMA's User-Agent to exactly mimic APT**, allowing it to bypass the whitelist and function normally with these repositories.

## 🔍 What's changed?

- The default User-Agent string sent by OMA has been changed to match:

