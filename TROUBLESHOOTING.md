# Mélange Troubleshooting Guide

> **Troubleshooting and diagnostic guide for Mélange — a modular Wabbajack mod list and modding framework for Dune: Awakening.**

This guide covers common Mélange installation, launch, framework, mod, and update problems.

If Mélange was working previously and suddenly stopped, resist the temptation to immediately reinstall everything.

Most problems are much easier to diagnose when you change **one thing at a time**.

---

## Table of Contents

- [Start Here](#start-here)
- [The Golden Rule of Troubleshooting](#the-golden-rule-of-troubleshooting)
- [Do Not Shotgun Troubleshoot](#do-not-shotgun-troubleshoot)
- [Determine Which Layer Is Failing](#determine-which-layer-is-failing)
- [Check for a Recent Dune: Awakening Update](#check-for-a-recent-dune-awakening-update)
- [Base Game Problems](#base-game-problems)
- [Wabbajack Installation Problems](#wabbajack-installation-problems)
- [Mod Organizer 2 Problems](#mod-organizer-2-problems)
- [Game Launch Problems](#game-launch-problems)
- [UE4SS Problems](#ue4ss-problems)
- [WPS Mod Problems](#wps-mod-problems)
- [ReShade and Graphics Problems](#reshade-and-graphics-problems)
- [Individual Mod Problems](#individual-mod-problems)
- [Problems After Adding Your Own Mods](#problems-after-adding-your-own-mods)
- [Problems After Updating Mélange](#problems-after-updating-mélange)
- [Problems After a Game Update](#problems-after-a-game-update)
- [Antivirus and Security Software](#antivirus-and-security-software)
- [What Not to Delete](#what-not-to-delete)
- [Logs and Diagnostic Information](#logs-and-diagnostic-information)
- [How to Report a Problem](#how-to-report-a-problem)
- [When Asking for Help](#when-asking-for-help)
- [Useful Links](#useful-links)

---

# Start Here

Before changing anything, answer these questions:

1. **Does Dune: Awakening launch normally through Steam?**
2. **Does the problem occur only when launching through Mélange?**
3. **Did Dune: Awakening recently update?**
4. **Did Mélange recently update?**
5. **Did you add, remove, update, enable, disable, or modify anything?**
6. **Did the problem begin immediately after one of those changes?**
7. **Does the problem occur using the official Mélange configuration?**

The answers to those questions usually determine where troubleshooting should begin.

---

# The Golden Rule of Troubleshooting

**Change one thing at a time.**

Then test.

If you change five things and the problem disappears, you do not know which change fixed it.

If you change five things and the problem becomes worse, you do not know which change caused the new problem.

A good diagnostic process looks like this:

```text
Observe Problem
      ↓
Identify Likely Layer
      ↓
Make One Change
      ↓
Test
      ↓
Record Result
      ↓
Continue
```

This may feel slower.

In practice, it is usually much faster.

---

# Do Not Shotgun Troubleshoot

When something stops working, avoid immediately doing things such as:

- Reinstalling Dune: Awakening
- Reinstalling Mélange
- Reinstalling Mod Organizer 2
- Downloading a different UE4SS version
- Replacing framework files manually
- Deleting random configuration files
- Changing launch arguments
- Moving files directly into the game directory
- Updating every mod individually
- Disabling half the mod list at random
- Following unrelated instructions written for another game
- Following old troubleshooting instructions without checking whether they still apply

These actions can destroy useful diagnostic information or introduce additional problems.

> [!IMPORTANT]
> Mélange supplies a configured modding environment.
>
> Do not manually replace Mélange's framework components simply because a newer version exists somewhere on the Internet.

Newer does not automatically mean compatible.

---

# Determine Which Layer Is Failing

Mélange contains several layers.

Understanding which layer is failing dramatically reduces the troubleshooting area.

A simplified Mélange launch stack looks like:

```text
Steam / Dune: Awakening
        ↓
Mélange Mod Organizer 2
        ↓
Configured Modded Launch Environment
        ↓
Framework Components
        ↓
Individual Mods
        ↓
Dune: Awakening
```

A problem with one layer does not necessarily mean the entire Mélange installation is broken.

## Layer 1 — Base Game

Can Dune: Awakening launch normally through Steam?

If not, begin with the base game.

## Layer 2 — Mod Organizer 2

Does Mélange's Mod Organizer 2 open normally?

If not, begin with the MO2 environment.

## Layer 3 — Modded Game Launch

Does:

```text
Dune: Awakening - Singleplayer (Modded)
```

start the game?

If not, investigate the configured launch environment.

## Layer 4 — Frameworks

Does the game launch, but framework-dependent mods fail?

The problem may involve UE4SS, WPS integration, ReShade, or another framework component.

## Layer 5 — Individual Mods

Does almost everything work except one feature?

The problem is more likely isolated to an individual mod or dependency.

---

# Check for a Recent Dune: Awakening Update

Before doing anything destructive, check whether Dune: Awakening recently updated.

Game updates can change:

- Executables
- Engine behavior
- Internal game structures
- Assets
- Runtime behavior
- Functions used by mods
- Data expected by modding frameworks

That can temporarily break otherwise healthy mods.

If Mélange worked yesterday, Dune: Awakening updated today, and Mélange no longer works today, **the game update is important diagnostic information**.

Check the current Mélange release information and support channels before reinstalling anything.

> [!NOTE]
> This is why Mélange recommends setting Dune: Awakening in Steam to:
>
> **Only update this game when I launch it**
>
> See the [Mélange Installation Guide](InstallationGuide.md) for details.

---

# Base Game Problems

## Dune: Awakening Does Not Launch Through Steam

If the unmodded game cannot launch normally, do not begin by troubleshooting Mélange.

First establish that the base game works.

Close Mélange and Mod Organizer 2, then test Dune: Awakening normally through Steam.

If the game still fails, investigate the base installation first.

Possible areas to check include:

- Steam installation integrity
- Pending Steam updates
- Windows updates
- GPU drivers
- Required Windows components
- Antivirus or security interference
- General Dune: Awakening problems

Mélange cannot reliably fix a broken base game installation.

## Verify the Game Through Steam

If you suspect damaged or missing base game files, Steam provides a file verification function.

In Steam:

1. Open **Library**.
2. Right-click **Dune: Awakening**.
3. Select **Properties**.
4. Select **Installed Files**.
5. Select **Verify integrity of game files**.

> [!WARNING]
> Verification restores Steam-managed game files to the state expected by Steam.
>
> If you have manually placed modding files directly inside the Dune: Awakening installation directory, verification may affect those files or expose an already-mixed installation.
>
> Mélange is designed to avoid unnecessary manual modification of the game directory wherever practical.

After verification finishes, launch Dune: Awakening normally once before returning to Mélange.

---

# Wabbajack Installation Problems

## Mélange Does Not Appear in Wabbajack

Make sure you are using the **latest available version of Wabbajack**.

Older versions may not contain the Dune: Awakening support required by Mélange.

Do not assume that an old Wabbajack executable is current simply because it still launches.

## Wabbajack Cannot Find Dune: Awakening

Confirm that:

- Dune: Awakening is installed through **Steam**.
- Steam recognizes the game as installed.
- You have launched the game normally at least once.
- The game reaches the main menu normally.
- You are using the latest Wabbajack version.

If you recently moved the game between Steam libraries, launch it normally through Steam before trying Wabbajack again.

## Wabbajack Download Failure

A failed download does not automatically mean the entire installation must be deleted.

Possible causes include:

- Temporary network failure
- Host outage
- File removed or updated by its author
- Nexus Mods availability
- Interrupted connection
- Authentication problems
- Antivirus interference

Retry the installation first.

Wabbajack can often reuse files that were downloaded successfully.

## Wabbajack Installation Failure

Confirm that:

- There is sufficient free disk space.
- The Mélange installation folder is writable.
- The download folder is writable.
- Mélange is not being installed inside `Program Files`.
- Mélange is not being installed inside the Dune: Awakening directory.
- Mélange is not being installed inside the Steam `steamapps` directory.
- Security software has not quarantined required files.
- The latest Wabbajack version is being used.

Recommended installation examples:

```text
C:\Modlists\Melange
```

or:

```text
D:\Modlists\Melange
```

If the installation continues to fail, preserve the Wabbajack log before asking for help.

---

# Mod Organizer 2 Problems

## Mod Organizer 2 Does Not Open

Make sure you are launching the copy included with Mélange:

```text
<Melange Installation>\ModOrganizer.exe
```

Do not substitute another MO2 installation.

Mélange uses a portable, preconfigured Mod Organizer 2 environment.

## MO2 Asks You to Create a New Instance

Stop.

Mélange should already contain its configured portable environment.

Do not create a new global or portable instance unless Mélange documentation specifically instructs you to do so.

If MO2 suddenly behaves as though it has never been configured, something may be wrong with the installation or the wrong `ModOrganizer.exe` may have been launched.

## Mods Appear to Be Missing

Before reinstalling anything, confirm that:

- You opened the correct Mélange installation.
- You are using the expected MO2 profile.
- The mods have not simply been disabled.
- Separators are not collapsed.
- You did not accidentally open another MO2 instance.

## Mods Are Suddenly Disabled

Check which MO2 profile is active.

Different profiles can have different enabled/disabled states.

Switching profiles can therefore make the mod list appear different without any files actually being removed.

---

# Game Launch Problems

## Use the Correct Launcher

The primary Mélange game launcher is:

```text
Dune: Awakening - Singleplayer (Modded)
```

Select it in Mod Organizer 2 and click:

**Run**

Steam should be running in the background.

Do not use Steam's normal **Play** button when you intend to launch a Mélange session.

## Steam Is Not Running

Start Steam and sign in before launching Dune: Awakening through Mélange.

Then retry:

```text
Dune: Awakening - Singleplayer (Modded)
```

## The Game Works Through Steam but Not Through Mélange

This is extremely useful diagnostic information.

It indicates that:

- The base game can launch.
- Steam can launch the game.
- The problem is more likely associated with the modded environment.

When asking for help, explicitly state:

> **The game launches normally through Steam but fails through Mélange.**

That immediately narrows the investigation.

## The Game Starts and Immediately Closes

Before changing anything, determine whether:

- Dune: Awakening recently updated.
- Mélange recently updated.
- You changed a framework component.
- You installed another mod.
- You manually placed files into the game directory.
- Security software quarantined anything.

Check available logs before attempting a reinstall.

## The Game Hangs During Startup

Give the game a reasonable amount of time before force-closing it, particularly after:

- A game update
- A Mélange update
- Shader-related changes
- Graphics changes
- First launch after installation
- GPU Driver Update/Reinstallation

If the hang persists consistently, collect logs and determine whether the base game still launches normally through Steam.

---

# UE4SS Problems

Mélange uses **UE4SS** to support runtime modifications used by compatible mods.

UE4SS can be sensitive to game updates and engine changes.

## Game Launches but UE4SS Mods Do Not Work

First determine whether:

- All UE4SS mods stopped working
- Only one UE4SS mod stopped working

If **all** UE4SS-dependent mods fail simultaneously, suspect the framework or game compatibility before assuming that every individual mod broke at once.

If only **one** mod fails, investigate that mod and its dependencies first.

## Do Not Install a Different UE4SS Version Manually

Mélange supplies the UE4SS version expected by that Mélange release.

Do not replace it simply because another version is newer.

A newer UE4SS build may:

- Behave differently
- Change compatibility
- Require different configuration
- Break a working Mélange setup

Framework updates should be handled through Mélange unless documentation specifically instructs otherwise.

## UE4SS After a Game Update

If Dune: Awakening updated immediately before UE4SS functionality stopped working, check Mélange compatibility information.

Do not assume your UE4SS installation suddenly corrupted itself.

---

# WPS Mod Problems

Mélange supports compatible mods built around the **WPS Dune ecosystem**.

Mélange's integration is designed so that compatible WPS mods can participate in the MO2-managed environment without requiring users to manually reproduce the normal WPS installation workflow.

## A WPS Mod Does Not Work

Determine whether:

- Other WPS/UE4SS mods still work
- The mod is enabled in MO2
- The mod has required dependencies
- The mod supports the current game version
- The mod supports the current framework version
- The problem began after a game update

If other WPS mods work normally, the issue may be isolated to the individual mod.

If every WPS/UE4SS mod stops functioning simultaneously, investigate the framework layer.

## Do Not Manually Install a Second Copy

Avoid manually installing another copy of a Mélange-managed WPS mod directly into the game or UE4SS directories.

Doing so can create duplicate files and make it unclear which copy of the mod is actually being loaded.

One of the primary purposes of Mélange is to keep these components organized through Mod Organizer 2.

---

# ReShade and Graphics Problems

Mélange may include optional **ReShade-based graphics components**.

Graphics modifications introduce a different category of troubleshooting than gameplay mods.

## Game Works Until Graphics Components Are Enabled

Disable the optional graphics component and test again.

If the game begins working normally, you have isolated the problem to the graphics layer.

Possible causes may include:

- ReShade compatibility
- Add-on compatibility
- GPU driver changes
- Game updates
- Conflicting graphics injectors
- Third-party overlays
- User configuration changes

## ReShade Does Not Appear

Confirm that the appropriate Mélange graphics components are enabled.

Do not immediately run the standard ReShade installer over the Mélange environment.

Mélange's graphics framework may require a particular configuration or version.

## Another Graphics Injector Is Installed

Multiple graphics injectors, overlays, or DLL-based modifications can conflict.

If you added another graphics tool after installing Mélange, disable that addition and test again.

---

# Individual Mod Problems

## One Mod Does Not Work

If everything else appears functional, investigate the individual mod before troubleshooting the entire framework.

Check:

- Is the mod enabled?
- Are its dependencies enabled?
- Does it support the current game version?
- Does it require configuration?
- Does it conflict with another mod?
- Did the mod recently update?
- Did the game recently update?

## Disable and Retest

If a particular mod appears to cause a problem:

1. Disable that mod.
2. Launch the game.
3. Attempt to reproduce the problem.

If the problem disappears, you have isolated an important variable.

That does not automatically prove that the mod itself is defective.

The problem could involve:

- A conflict
- A dependency
- Load order
- Configuration
- Game-version compatibility
- Framework compatibility

But you now know where to investigate.

---

# Problems After Adding Your Own Mods

Mélange encourages experimentation.

However, once you change the official configuration, there is an important distinction between:

> **Mélange**

and:

> **Your Mélange**

## Return to the Official Configuration

If you encounter a problem after adding your own mods, attempt to reproduce the issue using the official Mélange configuration.

If the problem disappears, the issue is likely associated with your customization.

If the problem remains, it may be appropriate to investigate as a Mélange problem.

## Add Mods Gradually

Avoid installing twenty new mods and testing only after all twenty are enabled.

A better process is:

```text
Add Mod
   ↓
Launch
   ↓
Test
   ↓
Works?
   ↓
Add Next Mod
```

This makes identifying conflicts dramatically easier.

## Keep Your Mods Organized

Keep user-added mods clearly identifiable inside MO2.

A dedicated separator such as:

```text
[ User Added Mods ]
```

can make troubleshooting much easier.

---

# Problems After Updating Mélange

If a problem begins immediately after a Mélange update:

1. Read the release notes.
2. Check for special update instructions.
3. Confirm the update completed successfully.
4. Check whether your own modifications were affected.
5. Test using the official Mélange configuration.
6. Check the current support channels for known issues.

Do not immediately replace individual framework components with versions from previous Mélange releases unless specifically instructed.

---

# Problems After a Game Update

A Dune: Awakening update can temporarily break mods even when Mélange itself has not changed.

Symptoms may include:

- Game failing to launch through the modded environment
- UE4SS failing
- WPS mods failing
- Individual mods no longer functioning
- Crashes during startup
- Unexpected behavior in previously working mods

If the problem began immediately after a game update, **that timing matters**.

Check Mélange's current compatibility status before modifying the installation.

> [!IMPORTANT]
> A modded game breaking immediately after the base game updates does not necessarily mean your mod list has become corrupted.

Frameworks and mods may simply need to be updated for the new game version.

---

# Antivirus and Security Software

Modding frameworks sometimes behave in ways that security software considers unusual.

This can include:

- Runtime injection
- DLL loading
- Executable interaction
- Script execution
- File staging
- Temporary file operations

These behaviors may cause antivirus software to flag or quarantine legitimate modding components.

## If a File Was Quarantined

Do not blindly restore every quarantined file.

First determine:

- Which file was quarantined
- Which Mélange component supplied it
- Whether the file came from the expected source

If you are unsure, ask for help before creating broad antivirus exclusions.

> [!WARNING]
> Do not disable your antivirus entirely simply to make a mod list work.

Use narrow exclusions only when they are actually necessary and you understand what is being excluded.

Example: Make an Exclusion for the MO2 instance/application in your Anti-malware software.

---

# What Not to Delete

When troubleshooting, do not randomly delete:

- Mélange framework files
- MO2 configuration files
- Profiles
- Mods
- Download archives
- UE4SS files
- ReShade files
- WPS components
- Logs
- Game files
- Steam manifests

Logs and configuration files often contain exactly the information needed to diagnose the problem.

If a support instruction requires deleting or regenerating something, follow that specific instruction rather than performing broad cleanup.

---

# Logs and Diagnostic Information

Logs are much more useful than:

> *"It crashed."*

Different Mélange components may generate different logs.

Depending on the problem, useful diagnostic information may include:

- Wabbajack installation logs
- Mod Organizer 2 logs
- UE4SS logs
- Mod-specific logs
- ReShade logs
- Crash information
- Screenshots of error messages

## Preserve the First Failure

If something fails unexpectedly, consider copying the relevant log somewhere safe **before repeatedly relaunching or changing things**.

Some logs may be overwritten or changed on subsequent launches.

## Do Not Paste Thousands of Lines Without Context

When asking for help, provide the log file itself when possible and explain:

- What you were doing
- What happened
- Approximately when the failure occurred
- What changed immediately before the problem began

Context makes logs significantly more useful.

---

# How to Report a Problem

A useful problem report explains how another person can reproduce the issue.

A good report might look like:

```text
Dune: Awakening Version:
Mélange Version:
Wabbajack Version:

Problem:
The game closes during startup when launched through Mélange.

Expected:
The game should reach the main menu.

Base Game Test:
The game launches normally through Steam.

Official Mélange Profile:
The problem still occurs.

Recent Changes:
Dune: Awakening updated before the problem began.

Custom Mods:
None.

Error Message:
[Describe or attach screenshot]

Relevant Logs:
[Attach files]
```

That provides substantially more useful information than:

```text
game broke pls help
```

---

# When Asking for Help

Before requesting support, gather:

- Your **Dune: Awakening version**
- Your **Mélange version**
- Your **Wabbajack version**, if relevant
- Whether the base game launches through Steam
- Whether the game launches through Mélange
- Whether the problem occurs using the official Mélange configuration
- What changed before the problem began
- Any user-added mods
- Relevant screenshots
- Relevant logs
- Exact error messages

Also mention whether you have manually modified:

- The Dune: Awakening game directory
- Mélange's UE4SS installation
- WPS components
- ReShade components
- MO2 executables
- Launch arguments
- Framework versions

That information matters.

## Support Expectations

The official Mélange configuration is the primary supported environment.

Customized installations are welcome, and the community may still be able to help, but troubleshooting **Your Mélange** is necessarily best-effort.

You may be asked to reproduce a problem using the official Mélange configuration.

This is not intended to discourage customization.

It is how we determine whether the problem belongs to:

```text
Mélange
```

or:

```text
Your Mélange
```

---

# Useful Links

- **[Mélange README](README.md)**
- **[Mélange Installation Guide](InstallationGuide.md)**

Additional support and community links will be added as Mélange approaches its first public release.

---

# Still Stuck?

If you've reached this point and the problem remains:

**Stop changing things.**

Gather your logs, screenshots, version information, and the results of the tests you've already performed.

Then ask for help through the Mélange support channels.

Tell us what you already tried.

Tell us what changed.

Tell us what works.

Tell us what doesn't.

And most importantly:

**Tell us whether the base game works and whether the problem occurs with the official Mélange configuration.**

Those two pieces of information can eliminate enormous portions of the troubleshooting tree immediately.

---

**[Return to the Mélange README](README.md)**  
**[Read the Mélange Installation Guide](InstallationGuide.md)**