# How to Update Mélange

> **A guide to safely updating Mélange while protecting your personal mods, profiles, and customizations.**

Mélange is distributed and updated through **Wabbajack**.

Updating a mod list is different from updating an ordinary application. A Mélange update may change mods, frameworks, configuration files, Mod Organizer 2 settings, executables, priorities, or other parts of the installation.

If you use Mélange exactly as distributed, updating should be relatively straightforward.

If you have created **Your Mélange** by adding mods, profiles, or other customizations, a little preparation can help keep those additions separate from files managed by the official list.

Mélange uses the `[NoDelete]` naming convention for user-added content that should be protected from Wabbajack's normal cleanup of files and folders that are not part of the official mod list.

---

## Table of Contents

- [Before You Update](#before-you-update)
- [Always Read the Release Notes](#always-read-the-release-notes)
- [Use the Latest Version of Wabbajack](#use-the-latest-version-of-wabbajack)
- [Understanding Wabbajack Updates](#understanding-wabbajack-updates)
- [Protecting Your Personal Additions with NoDelete](#protecting-your-personal-additions-with-nodelete)
- [Protecting User-Added Mods](#protecting-user-added-mods)
- [Protecting Personal MO2 Profiles](#protecting-personal-mo2-profiles)
- [What NoDelete Does Not Mean](#what-nodelete-does-not-mean)
- [Recommended Customization Layout](#recommended-customization-layout)
- [Before Running the Update](#before-running-the-update)
- [Updating Mélange Through Wabbajack](#updating-mélange-through-wabbajack)
- [After the Update](#after-the-update)
- [Checking Your Personal Mods](#checking-your-personal-mods)
- [Checking Your Personal Profiles](#checking-your-personal-profiles)
- [When an Update Changes the Official Mod List](#when-an-update-changes-the-official-mod-list)
- [When Mélange and Your Customization Conflict](#when-mélange-and-your-customization-conflict)
- [Game Updates vs. Mélange Updates](#game-updates-vs-mélange-updates)
- [When a Clean Installation Is Required](#when-a-clean-installation-is-required)
- [If the Update Fails](#if-the-update-fails)
- [If Mélange Stops Working After an Update](#if-mélange-stops-working-after-an-update)
- [Recommended Update Checklist](#recommended-update-checklist)
- [Current Status of This Guide](#current-status-of-this-guide)
- [Useful Links](#useful-links)

---

# Before You Update

Do not treat a Mélange update like clicking **Update All** in an ordinary application.

Before updating:

1. Read the Mélange release notes.
2. Close Dune: Awakening.
3. Close Mod Organizer 2.
4. Make sure you are using the latest version of Wabbajack.
5. Identify any changes you made to the official Mélange configuration.
6. Make sure personal mods and profiles that should survive Wabbajack cleanup use the `[NoDelete]` naming convention.
7. Back up anything personally important that cannot easily be recreated.

If you have heavily customized Mélange, know what you changed before running the update.

---

# Always Read the Release Notes

**Read the release notes before every Mélange update.**

Release notes may contain information about:

- Added mods
- Removed mods
- Updated mods
- Framework changes
- Game-version requirements
- Configuration changes
- Known issues
- Compatibility problems
- Required user actions
- Changes affecting custom installations
- Whether a clean installation is required

Instructions in the release notes for a particular Mélange version take precedence over the general guidance in this document.

> [!IMPORTANT]
> If the release notes say **do not update yet**, wait.
>
> If they say a **clean installation is required**, do not assume that an in-place update is safe.

---

# Use the Latest Version of Wabbajack

Always use the **latest available version of Wabbajack** when installing or updating Mélange.

Mélange depends on Wabbajack's Dune: Awakening support.

An old Wabbajack executable may not contain the functionality expected by the current Mélange release.

Do not assume that the copy of Wabbajack already sitting on your computer is current.

---

# Understanding Wabbajack Updates

A Wabbajack mod list is intended to reproduce a specific configured environment.

When Mélange changes, Wabbajack may need to:

- Add files
- Replace files
- Update mods
- Remove files no longer belonging to the list
- Change configuration
- Rebuild parts of the installation

This is what makes Wabbajack useful: the installed Mélange environment can be brought into alignment with the configuration defined by the current release.

However, this also means user-added content needs to be clearly distinguished from content managed by the official list.

That is where the `[NoDelete]` convention becomes important.

---

# Protecting Your Personal Additions with NoDelete

If you add your own mods or create personal Mod Organizer 2 profiles inside the Mélange installation, prefix their names with:

```text
[NoDelete]
```

This tells Wabbajack that the matching user-created folder should not be removed during its normal cleanup of files and folders that are not part of the official mod list.

For example:

```text
[NoDelete] My Favorite Mod
```

or:

```text
[NoDelete] My Mélange
```

> [!IMPORTANT]
> Use `[NoDelete]` **before updating**, not after your personal content has already been removed.

The convention is most useful when adopted from the beginning.

> **New to customizing Mélange?**  
> See **[Customizing Mélange](CUSTOMIZING_MELANGE.md)** before adding personal mods or creating custom profiles. It explains how to keep your additions organized before you need to worry about preserving them through an update.

---

# Protecting User-Added Mods

When you install a mod yourself through Mélange's Mod Organizer 2, give the installed mod a name beginning with:

```text
[NoDelete]
```

For example:

```text
[NoDelete] Expanded Example Mod
```

```text
[NoDelete] Personal UI Tweaks
```

```text
[NoDelete] My Gameplay Mods
```

The important part is that the **actual installed mod folder name** begins with `[NoDelete]`.

## Recommended Naming Pattern

Use:

```text
[NoDelete] Mod Name
```

For example:

```text
[NoDelete] Example Inventory Mod
```

rather than simply:

```text
Example Inventory Mod
```

This has two advantages.

First, it clearly identifies the mod as something **you added** rather than something supplied by Mélange.

Second, it protects that user-added mod folder from Wabbajack's normal cleanup behavior during an update.

## Rename Existing User-Added Mods

If you already added personal mods without the prefix, rename them in MO2 before performing a Mélange update.

For example:

```text
My Custom Mod
```

becomes:

```text
[NoDelete] My Custom Mod
```

Do this for personal mods that you want to retain across Wabbajack updates.

> [!TIP]
> Using `[NoDelete]` consistently also makes customized installations much easier to troubleshoot.
>
> At a glance, you can distinguish official Mélange content from your own additions.

---

# Protecting Personal MO2 Profiles

The same convention should be used for **personal Mod Organizer 2 profiles**.

If you create your own profile, prefix the profile name with:

```text
[NoDelete]
```

For example:

```text
[NoDelete] My Mélange
```

or:

```text
[NoDelete] Experimental
```

or:

```text
[NoDelete] Survival Setup
```

This distinguishes your personal profile from profiles managed by the official Mélange installation and protects the corresponding profile folder from Wabbajack's normal cleanup.

## Recommended Workflow

Keep the official Mélange profile available as your baseline.

Then create your personal profile as something like:

```text
[NoDelete] My Mélange
```

Use that profile for:

- User-added mods
- Personal enable/disable choices
- Experiments
- Alternative configurations
- Testing
- Other customization

This gives you both:

```text
Official Mélange
```

and:

```text
[NoDelete] My Mélange
```

The official configuration remains useful for testing whether a problem also occurs without your customizations.

> [!IMPORTANT]
> A `[NoDelete]` profile protects the personal profile folder from normal Wabbajack cleanup.
>
> It does **not** turn that profile into a complete backup of every mod, framework, configuration file, or external dependency referenced by it.

Protect personal mods separately as well.

---

# What NoDelete Does Not Mean

`[NoDelete]` is useful, but it is not magic.

It does **not** mean:

> Never touch anything related to this customization under any circumstances.

It does not automatically guarantee that a personal mod will remain compatible with a new Mélange release.

It does not guarantee that:

- A user-added mod still works
- Dependencies still exist
- Priorities are still correct
- A framework remains compatible
- A game update did not break the mod
- An official Mélange change does not conflict with it
- A personal configuration still makes sense

Think of `[NoDelete]` as **preservation**, not **compatibility**.

After an update, you still need to test your customized environment.

---

# Recommended Customization Layout

A customized Mélange installation might eventually look conceptually like this:

```text
Official Mélange Frameworks
Official Mélange Mods
Official Mélange Configuration

[ User Added Mods ]

[NoDelete] Personal Gameplay Mod
[NoDelete] Personal UI Mod
[NoDelete] Personal Graphics Mod
```

And your MO2 profiles might include:

```text
Mélange
[NoDelete] My Mélange
[NoDelete] Testing
```

This makes ownership clear.

If it begins with:

```text
[NoDelete]
```

you know it is something you intentionally preserved outside the normal official Mélange configuration.

---

### Release-Specific Instructions Take Priority

The standard process in this guide is the baseline for updating Mélange.

However, individual releases may require additional steps because of changes to frameworks, configuration, mod packaging, or the game itself. When a Mélange release includes specific update instructions, **those instructions take precedence over this general guide**.

Do not assume that every Mélange update should be handled identically.

### When Is a Clean Install Necessary?

Do **not** perform a clean installation of Mélange simply because a new version has been released.

Unless the release notes specifically say otherwise, update the existing installation using the normal Mélange update procedure.

A clean installation may occasionally be required when an update makes substantial changes to the modlist's structure, frameworks, or configuration. If that happens, the release notes will say so and provide any additional instructions.

When in doubt, follow the instructions provided with the specific Mélange release.

# Before Running the Update

Before starting Wabbajack, perform a quick review.

## 1. Close the Game

Dune: Awakening should not be running.

## 2. Close Mod Organizer 2

Close Mélange's Mod Organizer 2 before updating.

## 3. Read the Release Notes

Check for:

- Special update instructions
- Known incompatibilities
- Game-version requirements
- Clean-install requirements

## 4. Check Your Personal Mods

Make sure user-added mods you want to preserve are named:

```text
[NoDelete] Mod Name
```

## 5. Check Your Personal Profiles

Make sure personal profiles you want to preserve are named:

```text
[NoDelete] Profile Name
```

## 6. Know What You Changed

If you manually modified official Mélange files, remember that Wabbajack may restore them to the state defined by the new release.

## 7. Back Up Irreplaceable Personal Work

If you created something yourself and cannot easily recreate or redownload it, keep a separate backup.

`[NoDelete]` is not a replacement for backing up irreplaceable work.

---

# Updating Mélange Through Wabbajack

Mélange updates are performed through Wabbajack using the current Mélange release.

The normal goal is to point Wabbajack at your existing Mélange installation so it can bring that installation into alignment with the new release.

Use the **same Mélange installation location** unless the release notes specifically instruct you to perform a clean installation or use another location.

For example:

```text
D:\Modlists\Melange
```

Wabbajack can reuse files that already match the new list rather than necessarily downloading the entire installation again.

> [!WARNING]
> Do not manually delete the Mélange installation before every update.
>
> A clean installation should be performed when there is a reason to do so, not as a routine first step.

### Public Update Procedure

The exact public release-to-release Mélange update workflow will be finalized after the process has been tested against real Mélange Wabbajack releases.

Until that validation is complete, follow any update-specific instructions supplied with the current Mélange release.

This section will be expanded with the exact tested Wabbajack procedure before Mélange's public update workflow is considered finalized.

---

# After the Update

Once Wabbajack reports a successful update:

1. Close Wabbajack.
2. Open:

   ```text
   ModOrganizer.exe
   ```

   from the Mélange installation.

3. Confirm that the expected Mélange profile exists.
4. Confirm that your `[NoDelete]` personal profiles still exist.
5. Confirm that your `[NoDelete]` personal mods still exist.
6. Review the left pane for obvious changes.
7. Review the release notes again if the update changed priorities or components.
8. Test the **official Mélange configuration first**.
9. Then test your customized profile.

Do not begin by enabling every personal modification and assuming the update is broken if something fails.

Establish the official baseline first.

---

# Checking Your Personal Mods

After updating, verify your user-added mods.

For each important addition, check:

- Is the mod still present?
- Is it enabled in your personal profile?
- Are its dependencies still present?
- Has Mélange added an equivalent mod?
- Did Mélange change a framework the mod depends upon?
- Did the game's version change?
- Are there new file conflicts?
- Is the mod still compatible?

A preserved mod is not necessarily a compatible mod.

If something behaves strangely after an update, temporarily disable your personal additions and test the official configuration.

---

# Checking Your Personal Profiles

Open the MO2 profile selector and confirm your personal profiles remain available.

For example:

```text
[NoDelete] My Mélange
```

If you use several profiles, check that you know which one is currently active before launching the game.

Different profiles may have different:

- Enabled mods
- Disabled mods
- Configuration
- Priority-related state

Do not mistake switching profiles for mods disappearing from the installation.

---

# When an Update Changes the Official Mod List

A Mélange update may:

- Add a mod you previously installed yourself
- Remove an official mod
- Replace one mod with another
- Update a framework
- Change mod priority
- Introduce a compatibility patch
- Change configuration

If Mélange begins supplying a mod that you previously installed yourself, do not automatically leave both copies enabled.

For example, you may have:

```text
[NoDelete] Example Mod
```

while the new Mélange release now includes:

```text
Example Mod
```

That creates the possibility of duplicate files, duplicate scripts, conflicting versions, or unexpected priority behavior.

Compare the versions and follow the release notes.

In many cases, the sensible result will be to disable or remove your personal duplicate and use the version now managed by Mélange.

---

# When Mélange and Your Customization Conflict

If the official Mélange configuration works but your personal profile does not, begin with your customization.

Do not immediately conclude that the Mélange update is broken.

Temporarily disable recent or suspicious personal additions.

Test again.

A useful process is:

```text
Official Mélange Works
        ↓
Custom Profile Fails
        ↓
Disable Personal Mods
        ↓
Test
        ↓
Re-enable Gradually
        ↓
Identify Conflict
```

This is substantially faster than reinstalling the entire mod list.

---

# Game Updates vs. Mélange Updates

These are two different things.

## Dune: Awakening Update

A **game update** is delivered through Steam.

It may affect:

- The executable
- Engine behavior
- Runtime structures
- Assets
- Framework compatibility
- Individual mods

## Mélange Update

A **Mélange update** is distributed through Wabbajack.

It may update the modding environment to accommodate:

- New mods
- New configurations
- Framework changes
- Compatibility changes
- A new Dune: Awakening version

Do not confuse the two.

A new game version may appear **before** Mélange and its included frameworks have been confirmed compatible with it.

This is why the Installation Guide recommends setting Dune: Awakening's Steam update behavior to:

**Only update this game when I launch it**

See:

**[Mélange Installation Guide](InstallationGuide.md)**

for more information.

---

# When a Clean Installation Is Required

Most updates should not automatically be treated as clean installations.

However, there may be releases where substantial changes make a clean installation preferable or necessary.

If so, the release notes will explicitly say so.

Examples could include major changes to:

- Installation structure
- Framework architecture
- MO2 configuration
- Core tooling
- Other foundational components

> [!IMPORTANT]
> Do not perform a clean installation merely because something went wrong once.
>
> Diagnose the problem first unless the release documentation specifically requires a clean install.

If a clean installation is required, preserve your personal work separately before deleting the old environment.

Detailed migration instructions should accompany any Mélange release that requires this.

---

# If the Update Fails

A failed Wabbajack update does not necessarily mean the existing Mélange installation must be deleted.

First:

1. Read the Wabbajack error.
2. Preserve the relevant Wabbajack log.
3. Check available disk space.
4. Check the download folder.
5. Check whether a required download failed.
6. Check whether security software quarantined something.
7. Confirm you are using the latest Wabbajack.
8. Check current Mélange support information.

Retrying Wabbajack may resolve temporary download failures.

Do not begin manually replacing Mélange framework files simply because the update failed.

---

# If Mélange Stops Working After an Update

First determine whether the problem occurs in:

```text
Official Mélange
```

or only in:

```text
[NoDelete] My Mélange
```

## Official Mélange Fails

Consult the current release notes and:

**[Mélange Troubleshooting Guide](TROUBLESHOOTING.md)**

Collect logs and report the problem if necessary.

## Official Mélange Works but Your Profile Fails

Investigate your custom additions.

Check:

- `[NoDelete]` mods
- Dependencies
- Mod versions
- Conflicts
- Priorities
- Personal configuration
- Mods that Mélange now supplies itself

The update may have changed something your customization depended upon.

---

# Recommended Update Checklist

Before updating:

```text
[ ] Read the Mélange release notes
[ ] Confirm I am using the latest Wabbajack
[ ] Close Dune: Awakening
[ ] Close Mod Organizer 2
[ ] Prefix personal mod names with [NoDelete]
[ ] Prefix personal MO2 profile names with [NoDelete]
[ ] Back up irreplaceable personal work
[ ] Review any manual changes I made to Mélange
```

After updating:

```text
[ ] Confirm Wabbajack completed successfully
[ ] Open Mélange's ModOrganizer.exe
[ ] Confirm official Mélange profile exists
[ ] Confirm [NoDelete] profiles exist
[ ] Confirm [NoDelete] mods exist
[ ] Test official Mélange first
[ ] Test my custom profile second
[ ] Check for duplicate mods introduced by the update
[ ] Check important personal mods for compatibility
```

If something fails:

```text
[ ] Determine whether official Mélange also fails
[ ] Disable personal additions and retest
[ ] Check the release notes
[ ] Check whether Dune: Awakening also updated
[ ] Preserve relevant logs
[ ] Consult TROUBLESHOOTING.md
```

---

# Current Status of This Guide

Mélange is still being developed toward its initial public releases.

The project's actual **release-to-release Wabbajack update procedure will be tested before it is presented as finalized behavior**.

Until that testing is complete, this document intentionally avoids pretending that an untested update process is proven.

What is already recommended as standard Mélange practice is:

- Use the latest Wabbajack.
- Read release notes.
- Keep the official configuration available for comparison.
- Clearly identify personal customizations.
- Prefix user-added mods with `[NoDelete]`.
- Prefix personal MO2 profiles with `[NoDelete]`.
- Back up irreplaceable personal work.
- Test official Mélange before blaming an update for problems in a customized profile.
- Do not perform unnecessary clean installations.

This document will be updated as the public Mélange update process matures.

---

# Useful Links

- **[Mélange README](README.md)**
- **[Mélange Installation Guide](InstallationGuide.md)**
- **[Customizing Mélange](CUSTOMIZING_MELANGE.md)**
- **[Mélange Troubleshooting Guide](TROUBLESHOOTING.md)**

Additional release and support links will be added as Mélange approaches public release.

---

# Keep Your Mélange Yours

Mélange is designed to be updated.

It is also designed to be customized.

Those goals can coexist when the boundary between official content and personal content remains clear.

For anything you add yourself and want Wabbajack to preserve, make the distinction obvious:

```text
[NoDelete] My Mod
```

```text
[NoDelete] My Mélange
```

Then read the release notes, update carefully, test the official configuration, and bring your customizations back into the mix deliberately.

**Mélange provides the foundation. `[NoDelete]` helps you preserve what you build on top of it.**

---

**[Return to the Mélange README](README.md)**  
**[Read the Installation Guide](InstallationGuide.md)**  
**[Read Customizing Mélange](CUSTOMIZING_MELANGE.md)**  
**[Read the Troubleshooting Guide](TROUBLESHOOTING.md)**