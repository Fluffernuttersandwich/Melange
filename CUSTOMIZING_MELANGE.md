# Customizing Mélange

> **A guide to customizing, extending, and experimenting with your Mélange installation.**

Mélange is designed to be modular.

The supplied configuration provides a tested starting point, but it is not intended to dictate the only way to play Dune: Awakening.

Enable something.

Disable something.

Add something.

Experiment.

**Build the Arrakis you want.**

There is, however, an important distinction between:

> **Mélange**

and:

> **Your Mélange**

Once you begin changing the official configuration, those changes become your responsibility to understand and maintain.

This guide explains how to experiment without unnecessarily destroying the known-good configuration you started with.

---

## Table of Contents

- [Before You Customize](#before-you-customize)
- [Mélange vs. Your Mélange](#mélange-vs-your-mélange)
- [Understanding Mod Organizer 2](#understanding-mod-organizer-2)
- [Create a Custom Profile](#create-a-custom-profile)
- [Keep Your Mods Organized](#keep-your-mods-organized)
- [Installing Additional Mods](#installing-additional-mods)
- [Adding WPS Dune Mods](#adding-wps-dune-mods)
- [Adding UE4SS Mods](#adding-ue4ss-mods)
- [Graphics and ReShade Customization](#graphics-and-reshade-customization)
- [Enabling and Disabling Mods](#enabling-and-disabling-mods)
- [Mod Priority and File Conflicts](#mod-priority-and-file-conflicts)
- [Updating Individual Mods](#updating-individual-mods)
- [Removing Mods](#removing-mods)
- [Testing Your Changes](#testing-your-changes)
- [When Something Breaks](#when-something-breaks)
- [Preparing for Mélange Updates](#preparing-for-mélange-updates)
- [Sharing Your Configuration](#sharing-your-configuration)
- [For Mod Authors and Experimenters](#for-mod-authors-and-experimenters)
- [Useful Links](#useful-links)

---

# Before You Customize

Before modifying Mélange, make sure the official installation works.

You should be able to:

1. Open Mélange's **Mod Organizer 2**.
2. Launch:

   ```text
   Dune: Awakening - Singleplayer (Modded)
   ```

3. Reach the Dune: Awakening main menu.
4. Confirm that the supplied Mélange environment functions normally.

Do this **before** adding your own mods.

If you begin customizing an installation that has never been tested in its original state, troubleshooting becomes much harder because you have no known-good baseline for comparison.

> [!IMPORTANT]
> Establish that **Mélange works before building Your Mélange**.

---

# Mélange vs. Your Mélange

Throughout the documentation, these terms have specific meanings.

## Mélange

**Mélange** refers to the official configuration distributed through the project.

This is the environment primarily tested by the Mélange project.

## Your Mélange

**Your Mélange** is the configuration you create after changing the official installation.

Examples include:

- Adding mods
- Removing mods
- Updating individual mods independently
- Changing framework versions
- Changing configurations
- Changing priorities
- Changing launch options
- Replacing graphics components
- Editing supplied files
- Adding experimental tools

Customization is encouraged.

However, once the official configuration has been changed, support necessarily becomes more complicated.

When troubleshooting, you may be asked to reproduce a problem using the official Mélange configuration.

That is how we determine whether a problem belongs to:

```text
Mélange
```

or:

```text
Your Mélange
```

---

# Understanding Mod Organizer 2

Mélange uses **Mod Organizer 2** as the center of its modding environment.

One of MO2's greatest strengths is that mods can remain separated from one another rather than being permanently merged into the base game installation.

This makes experimentation significantly easier.

A simplified view looks like:

```text
Dune: Awakening
       ↑
Mod Organizer 2
       ↑
 ┌─────────────┐
 │ Frameworks  │
 │ Gameplay    │
 │ Interface   │
 │ Graphics    │
 │ Your Mods   │
 └─────────────┘
```

When the game is launched through Mélange, MO2 presents the enabled files to the game through its virtualized environment.

This allows you to:

- Enable mods
- Disable mods
- Change priorities
- Inspect conflicts
- Create profiles
- Keep mods separated
- Test changes without permanently merging everything together

> [!WARNING]
> MO2 makes experimentation easier.
>
> It does **not** make every combination of mods automatically compatible.

---

# Create a Custom Profile

Before making extensive changes, consider creating your own Mod Organizer 2 profile.

This gives you a separate configuration for experimenting while preserving an easy way to return to the official Mélange setup.

## Creating a Profile

In Mod Organizer 2:

1. Open the **Profile** selector.
2. Open the profile management window.
3. Copy or clone the supplied Mélange profile.
4. Give your new profile a descriptive name.

For example:

```text
Mélange - Custom
```

or:

```text
My Mélange
```

Use your custom profile when experimenting.

Keep the official profile available as a known-good reference.

## Why Profiles Matter

Profiles can preserve different combinations of enabled and disabled mods and other profile-specific settings.

This makes it much easier to answer:

> Does this problem also happen in the official Mélange configuration?

If the answer is **no**, your customization has already narrowed the investigation.

> [!NOTE]
> A separate MO2 profile is **not a complete backup of your added mod files**.
>
> Profiles help separate configurations. They should not be treated as protection against every change that a future Mélange update might make.

---

# Keep Your Mods Organized

As the mod list grows, organization becomes increasingly important.

Do not scatter your additions randomly throughout the official Mélange structure.

A simple approach is to create a separator such as:

```text
[ User Added Mods ]
```

or:

```text
[ My Mélange ]
```

and place your additions there when appropriate.

You may eventually choose to create more specific separators:

```text
[ User Added - Gameplay ]
[ User Added - UI ]
[ User Added - Graphics ]
[ User Added - Experimental ]
```

The exact organization is up to you.

The important part is being able to quickly identify:

- What Mélange supplied
- What you added
- What you modified
- What is experimental

That distinction becomes extremely valuable during troubleshooting and updates.

---

# Installing Additional Mods

Whenever practical, install additional mods **through Mod Organizer 2** rather than manually copying files into Dune: Awakening.

The exact installation process depends on how the mod is packaged.

A typical MO2-friendly archive can be installed using MO2's normal archive installation function.

After installation:

1. Give the mod a clear name.
2. Place it in an appropriate location in the left pane.
3. Enable it.
4. Check for file conflicts.
5. Read the mod author's documentation.
6. Confirm required dependencies are installed.
7. Launch the game.
8. Test the mod before installing several more.

> [!IMPORTANT]
> Read the mod author's instructions.
>
> Mélange can provide infrastructure, but it cannot make an incorrectly installed or incompatible mod work automatically.

---

# Adding WPS Dune Mods

Mélange supports compatible mods from the **WPS Dune ecosystem**.

Mélange's MO2 integration is designed to handle supported WPS mod packages inside the Mélange environment wherever practical.

This means users should generally prefer installing supported packages through Mélange's Mod Organizer 2 environment rather than manually duplicating those files elsewhere.

## General Workflow

For a compatible WPS mod:

1. Download the mod from its official source.
2. Read the author's requirements and compatibility information.
3. Install the archive through Mélange's Mod Organizer 2.
4. Confirm that the mod appears correctly in MO2.
5. Enable the mod.
6. Launch:

   ```text
   Dune: Awakening - Singleplayer (Modded)
   ```

7. Test the mod.

Mélange's Dune-specific MO2 integration may normalize supported packages into the structure required by the modded runtime environment.

The exact behavior can depend on the package type and the current Mélange release.

> [!WARNING]
> Do not install a second manual copy of the same mod into the game's directories simply because the mod was originally designed for another installation workflow.
>
> Duplicate copies can make it difficult to determine which version is actually loading.

## Dependencies Still Matter

If a WPS mod requires:

- Another mod
- A particular framework version
- A specific game version
- Configuration
- A particular load order

those requirements still apply.

Mélange integration does not eliminate mod dependencies.

---

# Adding UE4SS Mods

Mélange provides its own configured **UE4SS runtime environment**.

Compatible UE4SS-based mods should be managed through Mélange wherever practical.

## Do Not Install Another UE4SS Runtime

If a mod page says:

> Install UE4SS first

remember that Mélange already supplies its configured UE4SS runtime.

Do **not** automatically install another copy of UE4SS over the Mélange environment.

Doing so may replace:

- Runtime files
- Configuration
- Compatibility settings
- Framework versions
- Other files expected by Mélange

If a mod requires a UE4SS version different from the one supplied by Mélange, treat that as a **compatibility question**, not an instruction to immediately overwrite the framework.

## Lua Mods

Some UE4SS mods use Lua.

Where supported by Mélange's installation handling, these mods can be kept isolated inside MO2 while being presented to UE4SS in the structure it expects.

Install them through Mélange when possible rather than manually scattering files through the game's directories.

---

# Graphics and ReShade Customization

Mélange may include optional graphics components built around **ReShade**.

These are intended to remain modular.

You may choose to:

- Enable visual components
- Disable visual components
- Change presets
- Adjust shader settings
- Experiment with your own ReShade configuration

## Establish a Baseline First

Before changing graphics components:

1. Confirm the game launches normally through Mélange.
2. Confirm the existing graphics configuration works.
3. Make one significant graphics change at a time.
4. Test after each change.

Graphics injectors can interact with:

- GPU drivers
- Upscaling technologies
- Frame generation
- Overlays
- Other injectors
- Game updates

Troubleshoot graphics changes separately from gameplay mods whenever possible.

## Do Not Run Installers Blindly

Do not automatically run another ReShade installer over Mélange simply because a preset tells you to install ReShade.

Mélange may already provide the required runtime.

Determine what the preset actually requires before replacing framework files.

---

# Enabling and Disabling Mods

One of the primary advantages of Mélange's MO2 environment is the ability to enable and disable components individually.

In the MO2 left pane:

- **Checked** mods are enabled.
- **Unchecked** mods are disabled.

This makes experimentation easy.

However, do not assume every component is optional.

Some mods may depend on:

- Frameworks
- Libraries
- Other mods
- Configuration files
- Compatibility patches

Disabling a dependency may cause several other mods to stop functioning.

## Framework Components

Treat framework components more cautiously than ordinary gameplay mods.

If you do not know what a framework component does, do not disable it merely because you do not recognize the name.

---

# Mod Priority and File Conflicts

When multiple mods provide the same virtual file path, the higher-priority file may overwrite the lower-priority version in the environment presented to the game.

This is one of the reasons MO2 is useful: those relationships can be inspected rather than silently merged into the game directory. Use the Data tab!

## A Conflict Is Not Automatically a Problem

A file conflict simply means multiple mods provide the same file.

Sometimes this is intentional.

For example:

```text
Base Mod
   ↓
Compatibility Patch
```

The patch may intentionally overwrite files from the base mod.

Do not attempt to eliminate every conflict simply because MO2 displays one.

The important question is:

> **Which version is supposed to win?**

## Do Not Randomly Rearrange the Official List

Mélange's supplied organization is part of the configuration.

If you are experimenting with priority in the Data tab:

1. Make one change.
2. Record what you changed.
3. Test.
4. Revert if necessary.

---

# Updating Individual Mods

Be cautious when independently updating mods supplied by Mélange.

A newer version of a mod is not automatically appropriate for the current Mélange release.

An update may:

- Require a newer framework
- Require a newer game version
- Change configuration
- Introduce new dependencies
- Remove compatibility
- Conflict with another included mod
- Require a new patch

## Mélange-Supplied Mods

Unless you have a specific reason to do otherwise, allow Mélange updates to manage the versions of mods included with the official list.

If you independently update one of them, that becomes part of **Your Mélange**.

## User-Added Mods

Mods you added yourself are your responsibility to maintain.

Before updating one:

1. Read its changelog.
2. Read its update instructions.
3. Check dependencies.
4. Check game-version compatibility.
5. Determine whether configuration changed.
6. Keep the previous version available until the new version is tested.

---

# Removing Mods

Removing a mod can be more complicated than disabling it.

Some mods may affect:

- Save data
- Configuration
- Runtime state
- Dependencies
- Other mods

Before permanently removing a mod, read the author's documentation.

## Disable Before Deleting

When troubleshooting, prefer:

```text
Disable
   ↓
Test
   ↓
Confirm
   ↓
Remove if appropriate
```

rather than immediately deleting the mod.

Keeping the files temporarily makes reverting the test easier.

## Save-Game Considerations

Do not assume every mod can be safely removed from an existing save.

If a mod author provides uninstall instructions, follow them.

If no information exists, proceed cautiously and keep backups of important saves where appropriate.

---

# Testing Your Changes

Good customization is mostly good testing.

The best habit you can develop is:

> **Change one thing at a time.**

For example:

```text
Install Mod A
     ↓
Launch Game
     ↓
Test Mod A
     ↓
Everything Works
     ↓
Install Mod B
```

Avoid:

```text
Install 17 Mods
     ↓
Launch Game
     ↓
Crash
     ↓
Wonder Which of 17 Mods Caused It
```

## Test the Feature You Changed

Do not merely confirm that the main menu appears.

If you installed an inventory mod, test inventory behavior.

If you installed a graphics modification, inspect the graphics behavior.

If you installed a UI mod, open the affected interface.

If you installed a gameplay mod, test the relevant gameplay system.

A successful launch proves only that the game launched.

---

# When Something Breaks

First ask:

> **What changed immediately before the problem began?**

That is often the most useful troubleshooting question.

If you just installed a mod:

1. Disable it.
2. Test again.

If you just updated a mod:

1. Restore the previous version if practical.
2. Test again.

If you changed priority:

1. Restore the previous order.
2. Test again.

If you changed configuration:

1. Restore the previous configuration.
2. Test again.

If the problem disappears, you have isolated an important variable.

## Return to Official Mélange

If necessary, switch back to the official Mélange Profile and test.

If the official configuration works but your custom configuration does not, the problem is probably associated with your changes.

If the official configuration also fails, consult:

**[Mélange Troubleshooting Guide](TROUBLESHOOTING.md)**

---

# Preparing for Mélange Updates

A future Mélange update may change:

- Included mods
- Mod versions
- Framework versions
- Separators
- Priorities
- Configuration
- Executables
- Compatibility settings

Before updating, know what you changed.

This is another reason to keep user additions clearly separated.

## Recommended Habits

Keep track of:

- Mods you added
- Mods you removed
- Mélange mods you independently updated
- Configuration files you changed
- Priority changes
- Framework changes
- Graphics changes

You do not need to maintain a novel-length changelog.

Even a simple list can be extremely helpful.

For example:

```text
My Mélange Changes

Added:
- Example Inventory Mod
- Example UI Mod

Changed:
- Example Graphics Preset

Updated Manually:
- Example Mod 1.2 → 1.3

Disabled:
- Example Gameplay Mod
```

## Do Not Assume Profiles Are Backups

MO2 profiles help preserve configuration choices.

They do not necessarily preserve every user-added file against every possible update operation.

Specific backup and preservation recommendations will be documented once Mélange's public Wabbajack update process has been fully tested.

Always read Mélange release notes before updating.

---

# Sharing Your Configuration

You are welcome to discuss and share your Mélange customizations with other users.

When doing so, clearly distinguish your configuration from the official Mélange release.

For example:

> **My Mélange setup uses...**

rather than:

> **Mélange includes...**

when describing components you added yourself.

This avoids confusion when other users attempt to reproduce your setup.

## Do Not Redistribute Other Authors' Work Without Permission

A working personal configuration does not automatically grant permission to repackage another author's files.

If you want to publish a mod, patch, preset, collection, or other package based on someone else's work, respect the original author's permissions and distribution terms.

Whenever practical, direct users to the original mod page.

If you tweak someone else's mod and want to share that, it's best to do so as an add-on patch mod.

---

# For Mod Authors and Experimenters

Mélange is intended to be useful not only as a mod list, but also as a practical environment for experimentation.

If you are developing or testing a Dune: Awakening mod, consider keeping your development build clearly separated from the official Mélange components.

For example:

```text
[ Development / Testing ]
```

This makes it easier to:

- Enable your development build
- Disable it
- Compare against the official configuration
- Test dependencies
- Identify conflicts
- Replace builds during development

## MO2-Friendly Packaging

Where practical, package mods so they can be installed and removed cleanly through Mod Organizer 2.

Good packaging makes a mod easier to:

- Install
- Update
- Remove
- Test
- Troubleshoot
- Include in reproducible mod lists

Mélange's Dune-specific MO2 integration may provide additional handling for supported package types as the ecosystem develops.

## You Do Not Need a Special Mélange Version

Mod authors should not need to maintain a separate:

```text
Mélange Edition
```

of every mod.

Where practical, Mélange should adapt properly packaged mods to its environment rather than requiring authors to create special releases specifically for the mod list.

That keeps the wider Dune: Awakening modding ecosystem healthier and reduces duplicated work.

---

# Useful Links

- **[Mélange README](README.md)**
- **[Mélange Installation Guide](InstallationGuide.md)**
- **[Mélange Troubleshooting Guide](TROUBLESHOOTING.md)**

Additional modding documentation and community links will be added as the project develops.

---

# Make It Yours

Mélange is intended to provide a strong foundation.

What you build on that foundation is up to you.

Use the supplied configuration.

Strip it down.

Build it up.

Experiment with something nobody has tried yet.

Just remember what you changed, test one thing at a time, and keep a known-good configuration available when the desert decides to fight back.

**Mélange provides the spice. You decide how much to add.**

---

**[Return to the Mélange README](README.md)**  
**[Read the Installation Guide](InstallationGuide.md)**  
**[Read the Troubleshooting Guide](TROUBLESHOOTING.md)**