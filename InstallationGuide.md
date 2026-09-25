# Mélange Installation Guide

> **Complete installation guide for Mélange — a modular Wabbajack mod list and modding framework for Dune: Awakening.**

This guide walks through installing Mélange from beginning to end.

Mélange uses **Wabbajack** to create a complete, portable **Mod Organizer 2** environment for Dune: Awakening.

You do **not** need to install Mod Organizer 2, UE4SS, WPS Dune Framework components, or other Mélange framework components manually unless specifically instructed by the Mélange documentation.

---

## Table of Contents

- [Before You Begin](#before-you-begin)
- [Requirements](#requirements)
- [Step 1 — Install Dune: Awakening](#step-1--install-dune-awakening)
- [Step 2 — Run Dune: Awakening Once](#step-2--run-dune-awakening-once)
- [Step 2A — Prevent Automatic Game Updates](#step-2a--prevent-automatic-game-updates)
- [Step 3 — Download Wabbajack](#step-3--download-wabbajack)
- [Step 4 — Download Mélange](#step-4--download-mélange)
- [Step 5 — Choose Your Installation Folders](#step-5--choose-your-installation-folders)
- [Step 6 — Install Mélange](#step-6--install-mélange)
- [Step 7 — Launch Mod Organizer 2](#step-7--launch-mod-organizer-2)
- [Step 8 — Launch Dune: Awakening](#step-8--launch-dune-awakening)
- [Verifying Your Installation](#verifying-your-installation)
- [Understanding the Mélange Installation](#understanding-the-mélange-installation)
- [Adding Your Own Mods](#adding-your-own-mods)
- [Updating Mélange](#updating-mélange)
- [After a Dune: Awakening Update](#after-a-dune-awakening-update)
- [Troubleshooting](#troubleshooting)
- [Getting Help](#getting-help)

---

## Before You Begin

Mélange is currently intended for **single-player modded gameplay**.

Dune: Awakening modding is still developing rapidly. Game updates may temporarily affect mods, UE4SS, WPS components, or other parts of the Mélange framework.

Before installing or updating Mélange, check the current Mélange release information for any known compatibility issues.

> [!IMPORTANT]
> Always use the **latest available version of Wabbajack**.
>
> Older Wabbajack versions may not contain the Dune: Awakening support required to install Mélange.

---

## Requirements

### Dune: Awakening — Steam

You must own and install **Dune: Awakening through Steam**.

Mélange is built specifically around the Steam version of Dune: Awakening.

Other versions of the game are not supported.

### Windows

Mélange requires:

- **Windows 10 or Windows 11**
- **64-bit operating system**

Mélange does not impose additional hardware requirements beyond those required by Dune: Awakening itself.

**If your PC can run the base game, it can run Mélange.**

### Required Windows Components

The following Windows components are required:

| Requirement | Notes |
| --- | --- |
| **[.NET Framework 4.8](https://learn.microsoft.com/en-us/dotnet/framework/install/)** | Required Windows component. Install or enable it if it is not already present on your system. |
| **[Microsoft Visual C++ v14 Redistributable (x64)](https://aka.ms/vc14/vc_redist.x64.exe)** | Required 64-bit Microsoft Visual C++ runtime. Install or repair it using Microsoft's official installer if needed. |

### Storage

An **SSD is strongly recommended** for both Dune: Awakening and Mélange.

The game and Mélange installation do not need to be located on the same drive.

The amount of disk space required by Mélange will change as the mod list grows. Check the current Mélange release information before installation for current storage requirements.

---

# Step 1 — Install Dune: Awakening

Install **Dune: Awakening through Steam** normally.

A typical Steam installation may look something like:

```text
C:\Program Files (x86)\Steam\steamapps\common\DuneAwakening
```

or, when using a separate Steam library:

```text
D:\SteamLibrary\steamapps\common\DuneAwakening
```

Your installation does **not** need to use either of these exact paths.

> [!IMPORTANT]
> Do not manually copy Mélange files into the Dune: Awakening installation directory.
>
> Mélange is designed to manage its modding environment through Mod Organizer 2 wherever practical.

---

# Step 2 — Run Dune: Awakening Once

Before installing Mélange:

1. Start **Dune: Awakening normally through Steam**.
2. Allow the game to reach the main menu.
3. Confirm that the unmodded game launches correctly.
4. Exit the game.

This establishes a known-good base game installation before Mélange is introduced.

If the unmodded game does not launch correctly, resolve that problem **before** installing Mélange.

---

# Step 2A — Prevent Automatic Game Updates

Modded games and automatic updates generally do not mix well.

A Dune: Awakening update can change game files, engine behavior, or other components that mods and modding frameworks depend upon. When that happens, previously working mods may stop functioning until their authors or framework developers release compatible updates.

For that reason, it is good practice with any heavily modded game to **avoid automatically updating the game until you know that your modding environment is compatible with the new version**.

This is particularly important for Mélange because components such as **UE4SS and other runtime modifications can be sensitive to changes in the game executable or engine**.

An automatic update can turn a perfectly functional Mélange installation into a temporarily incompatible one without anything actually being wrong with your mod list.

## Change Dune: Awakening's Steam Update Setting

In Steam:

1. Open your **Library**.
2. Right-click **Dune: Awakening**.
3. Select **Properties**.
4. Select **Updates**.
5. Find **Automatic Updates**.
6. Change the setting to:

   **Only update this game when I launch it**

This prevents Steam from automatically updating Dune: Awakening in the background simply because an update becomes available.

> [!IMPORTANT]
> Steam does not normally provide a permanent **"Never update this game"** option.
>
> **Only update this game when I launch it** is therefore the recommended Steam setting for Mélange users.

This way, so long as you only Run the game from MO2, you won't have to update the game until you are ready to do so... usually after the Melange Mod List updates to the current game verison.

## When Dune: Awakening Receives an Update

If Steam shows that an update is available, check the current **Mélange release information and support channels before allowing the update whenever practical**.

Ideally, wait until the relevant mods and frameworks have been confirmed compatible with the new game version.

> [!WARNING]
> Do not assume that launching through Mod Organizer 2 makes a pending Steam update impossible.
>
> Steam ultimately controls the installed game and may require an update before allowing the game to launch. Treat the Steam setting as a way to gain control over **when** an update occurs, not as an absolute update blocker.

If Steam requires the game to update before it can launch, **do not attempt to defeat Steam's update system by randomly modifying manifests or game files**.

Instead, check Mélange's current compatibility status and follow any release-specific instructions.

## Why This Matters

With an unmodded game, updating immediately is usually desirable.

With a modded game, the better order is often:

**Game Update → Framework/Mod Compatibility Check → Mod Updates → Then Update the Game**

That gives mod authors and framework developers time to determine what changed and prevents an unexpected game update from unnecessarily disrupting a working installation.

Once the current Mélange release has been confirmed compatible with the new Dune: Awakening version, the game can be updated normally.

---

# Step 3 — Download Wabbajack

Download the **latest available version of Wabbajack**.

Mélange requires a Wabbajack version containing official Dune: Awakening game support.

> [!WARNING]
> Do not use an old Wabbajack executable that has been sitting in your Downloads folder.
>
> Download the current version before installing Mélange.

Place Wabbajack somewhere convenient outside of protected Windows folders.

For example:

```text
C:\Wabbajack
```

You may use another location if preferred.

Run Wabbajack and allow it to complete any initial setup or update process.

---

# Step 4 — Download Mélange

Mélange will be distributed as a **Wabbajack mod list**.

Download the current Mélange release using the distribution method specified on the Mélange GitHub page and release documentation.

> [!IMPORTANT]
> Always read the release notes for the version you are installing.
>
> A particular release may contain additional installation instructions, compatibility warnings, or requirements that supersede this general guide.

Do not use an older Mélange installer unless you specifically intend to install that version.

---

# Step 5 — Choose Your Installation Folders

Wabbajack will require locations for the Mélange installation and its downloaded files.

## Installation Location

Choose a simple location outside of protected Windows directories.

Recommended examples:

```text
C:\Modlists\Melange
```

or:

```text
D:\Modlists\Melange
```

> [!WARNING]
> Do **not** install Mélange inside:
>
> - `Program Files`
> - `Program Files (x86)`
> - The Dune: Awakening game folder
> - The Steam `steamapps` folder
> - Another Mod Organizer 2 installation

Using a short, simple path helps avoid permissions problems and makes troubleshooting easier.

Although the project is displayed as **Mélange**, using the ASCII name `Melange` for filesystem paths is recommended.

## Downloads Location

Wabbajack will also require a download location.

For example:

```text
D:\Modlists\Melange Downloads
```

Do not use the Dune: Awakening game directory as either location.

---

# Step 6 — Install Mélange

Once your paths are configured, begin the Mélange installation in Wabbajack.

Wabbajack will download and assemble the files required to create the Mélange environment.

Installation time will vary depending on:

- Internet connection speed
- Storage performance
- The size of the current Mélange release
- Whether required downloads are already present (if you are updating the Mod List)

Allow Wabbajack to finish completely.

Do not launch Mod Organizer 2 or Dune: Awakening while Wabbajack is actively building the installation.

### If Wabbajack Reports an Error

Do not immediately delete the entire installation.

Read the error displayed by Wabbajack first.

Common causes of installation problems can include:

- An outdated Wabbajack version
- A failed or interrupted download
- Insufficient disk space
- Antivirus or security software interfering with files
- A required download becoming temporarily unavailable
- Incorrect folder permissions
- A game installation that Wabbajack cannot locate

If retrying the installation does not resolve the problem, save the relevant Wabbajack log before asking for support.

---

# Step 7 — Launch Mod Organizer 2

After Wabbajack reports a successful installation, open the Mélange installation folder.

For example:

```text
D:\Modlists\Melange
```

Launch:

```text
ModOrganizer.exe
```

This is the copy of Mod Organizer 2 configured specifically for Mélange.

> [!CAUTION]
> **Do not install or use a separate copy of Mod Organizer 2 for Mélange.**
>
> Mélange includes its own portable, preconfigured Mod Organizer 2 environment.

When Mod Organizer 2 opens, allow it to finish loading before launching the game.

---

# Step 8 — Launch Dune: Awakening

Inside Mélange's Mod Organizer 2 installation, locate the executable selector near the upper-right portion of the MO2 window.

Select:

```text
Dune: Awakening - Singleplayer (Modded)
```

Then click:

**Run**

Steam should already be running in the background.

> [!IMPORTANT]
> When you want to play with Mélange, launch Dune: Awakening using **Dune: Awakening - Singleplayer (Modded)** from Mélange's Mod Organizer 2.
>
> Do not use Steam's normal **Play** button for a Mélange session.

The Mélange launch entry starts Dune: Awakening through the configured modded environment required by its components.

---

# Verifying Your Installation

After launching through Mélange, confirm that Dune: Awakening reaches the main menu normally.

A successful basic test establishes that:

- Dune: Awakening can launch through Mélange
- Mod Organizer 2 is correctly locating the game
- The Mélange virtual filesystem is functioning
- The configured modded launch environment is working

Depending on the current Mélange release, additional mods or framework components may provide their own visible confirmation that they are active.

The exact verification procedure may change as Mélange grows.

If the game launches successfully through:

```text
Dune: Awakening - Singleplayer (Modded)
```

you have completed the basic Mélange installation.

---

# Understanding the Mélange Installation

Mélange is designed around a **portable Mod Organizer 2 environment**.

This means all Mélange-managed files are kept separate from the base Dune: Awakening installation wherever practical.

Mod Organizer 2 presents those files to the game when you launch through Mélange.

This provides several advantages:

- Mods can be enabled and disabled individually.
- Files remain organized by mod.
- Conflicts are easier to inspect.
- Different configurations can be managed through profiles.
- The original game installation remains clean.
- Troubleshooting individual components becomes easier.

## The Left Pane

The left side of Mod Organizer 2 contains the installed mods and framework components.

## The Right Pane

The right side contains Mélange's configured executables and other MO2 functions.

The primary game launcher is:

```text
Dune: Awakening - Singleplayer (Modded)
```

Additional diagnostic or modding tools may also appear depending on the Mélange release.

## Separators

Mélange may use MO2 separators to organize related components.

Separators are organizational tools and make a large mod list easier to navigate.

As Mélange grows, categories may include framework components, gameplay modifications, interface mods, graphics options, utilities, user-added mods, and other groups.

---

# Adding Your Own Mods

Mélange is intentionally modular.

You are welcome to add mods and experiment with the installation.

That freedom comes with one important distinction:

> **Mélange**

and

> **Your Mélange**

The official Mélange configuration is the version tested and supported by the project.

Once you add, remove, update, replace, or modify components, you are creating your own customized Mélange environment.

That is encouraged — but those changes become your responsibility to maintain.

## Recommended Practice

Before making extensive changes:

1. Keep the official Mélange configuration intact.
2. Consider creating a separate **Mod Organizer 2 Profile** for your customized setup.
3. Keep your own mods clearly identifiable from official Mélange components.
4. Avoid replacing Mélange-supplied framework components unless you understand their dependencies.
5. Make one significant change at a time and test it.

A separate profile makes it easier to return to the official Mélange configuration when diagnosing a problem.

> [!NOTE]
> A separate MO2 Profile should not be treated as a complete backup of user-added files.
>
> Recommendations for protecting custom mods during Mélange updates will be documented once the public update process has been fully tested.

---

# Updating Mélange

Mélange updates will be distributed through **Wabbajack**.

Before updating:

1. Read the release notes.
2. Close Dune: Awakening.
3. Close Mod Organizer 2.
4. Make note of any personal modifications you have made.
5. Use the **latest available version of Wabbajack**.

Some updates may change:

- Mods
- Framework versions
- Configuration files
- Executables
- Separators
- Priorities
- Compatibility settings
- Other parts of the Mélange environment

Occasionally, an update may require a new game save and/or clean installation.

If that is necessary, the release notes will say so explicitly.

> [!IMPORTANT]
> Do not assume that every Mélange update requires deleting and reinstalling the entire mod list.

A detailed, tested update procedure will be added once Mélange's public Wabbajack update process has been finalized.

---

# After a Dune: Awakening Update

Dune: Awakening updates may temporarily affect the functionality of mods or modding frameworks.

This can include components involving:

- UE4SS
- WPS-based mods
- Runtime modifications
- ReShade or graphics modifications
- Other version-sensitive components

If Dune: Awakening has just updated and Mélange suddenly stops working, **do not immediately begin deleting or reinstalling components**.

Check the Mélange GitHub page, release notes, and support channels first.

The problem may be a known compatibility issue that requires an updated framework or mod.

This is particularly important while Dune: Awakening modding remains young and the tooling continues to develop.

---

# Troubleshooting

## The Base Game Does Not Launch

First test Dune: Awakening normally through Steam without Mélange.

If the unmodded game does not launch correctly, the problem must be resolved before Mélange can be reliably diagnosed.

## Mélange Does Not Appear in Wabbajack

Make sure you are using the **latest available version of Wabbajack**.

Older versions may not contain the Dune: Awakening game support required by Mélange.

## Wabbajack Cannot Find Dune: Awakening

Confirm that:

- Dune: Awakening is installed through Steam.
- You have launched the game normally at least once.
- Steam recognizes the installation.
- You are using the latest version of Wabbajack.

## Wabbajack Installation Fails

Do not immediately delete everything.

Check the Wabbajack error and log.

Confirm that:

- You have sufficient disk space.
- Your internet connection is functioning.
- The installation and download folders are writable.
- You are signed into your NexusMods account through the Wabbajack application.
- You are not installing into a protected Windows directory.
- Antivirus or security software has not quarantined required files.

Retrying Wabbajack may resolve an interrupted or temporary download failure.

## Mod Organizer 2 Opens but the Game Does Not

Confirm that you are launching:

```text
Dune: Awakening - Singleplayer (Modded)
```

from the Mélange Mod Organizer 2 installation.

Steam should be running in the background.

If you have changed Mélange's executables, framework versions, or supplied mods, reproduce the problem using the official configuration before reporting it as a Mélange issue.

## The Game Works Through Steam but Not Through Mélange

This is useful diagnostic information.

It indicates that the base game itself can launch and that the problem is more likely associated with the modded environment.

When requesting support, mention specifically that:

- The game launches normally through Steam.
- The game fails when launched through Mélange.
- Whether the problem also occurs with the official Mélange configuration.

Include relevant logs and screenshots.

## The Game Updated and Mélange Stopped Working

Check current Mélange compatibility information before reinstalling anything.

A game update may temporarily require updates to UE4SS, WPS components, individual mods, or other parts of the framework.

## I Added a Mod and Something Broke

Disable the newly added mod and test again.

If the problem disappears, you have already isolated an important part of the issue.

If necessary, return to the official Mélange profile and reproduce the problem there.

---

# Getting Help

Mélange support, development discussion, and general Dune: Awakening modding discussion are hosted through the **Smörgåsbord Discord community**.

A permanent invitation link will be added before the first public Mélange release.

When requesting help, provide:

- Your **Dune: Awakening game version**
- Your **Mélange version**
- Your **Wabbajack version**, when relevant
- What you were attempting to do
- What happened
- What you expected to happen
- Whether the problem occurs with the official Mélange configuration
- Any mods or components you added, removed, updated, or modified
- Relevant screenshots
- Relevant logs or error messages

Please provide more information than:

> *"It doesn't work."*

The more precisely the problem can be reproduced, the easier it is to investigate.

---

## Installation Complete

If Dune: Awakening launches successfully using:

```text
Dune: Awakening - Singleplayer (Modded)
```

from Mélange's Mod Organizer 2 installation, your basic setup is complete.

From here you can play using the supplied configuration, explore the individual components in Mod Organizer 2, or begin building **Your Mélange**.

**Experiment. Learn. Mod Arrakis.**

---

**[Return to the Mélange README](README.md)**