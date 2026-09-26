# Mélange by FNS

> **A modular Wabbajack mod list and modding framework for Dune: Awakening**

## ⚠️ Temper Your Expectations

**Dune: Awakening modding is still in its infancy.**

Mélange currently exists more as **scaffolding for a future modding ecosystem** than as a traditional overhaul modlist.

There simply aren't enough mature mods yet to build the kind of large, comprehensive overhaul that established modding communities can support. That is expected to change over time.

I subscribe to the **"if you build it, they will come"** school of thought.

Mélange exists in part to help build that foundation: a working Mod Organizer 2 and Wabbajack ecosystem, organized mod installation, documentation, tooling, and a place for future Dune: Awakening mods to grow.

One of the project's goals is also to encourage mod authors and users to make **Nexus Mods** a central home for Dune: Awakening modding, helping create a discoverable and sustainable community around the game.

**Mélange is the foundation. What gets built on it depends on where the Dune: Awakening modding community goes from here.**

---

## Table of Contents

- [Definition](#definition)
- [Vision](#vision)
- [What is Mélange?](#what-is-mélange)
- [Requirements](#requirements)
- [Installation](#installation)
- [Updating Mélange](#updating-mélange)
- [Included Mods & Frameworks](#included-mods--frameworks)
- [Documentation](#documentation)
- [Support & Community](#support--community)
- [For Mod Authors](#for-mod-authors)
- [Credits & Acknowledgements](#credits--acknowledgements)
- [The Road Ahead](#the-road-ahead)
- [Support the Project](#-support-the-project)

---

## Definition

**Mélange**  
/mā-ˈläⁿzh/  
*noun*

> A mixture; a medley.

> The spice of Arrakis: the most valuable substance in the known universe.

> A special blend of Dune: Awakening mods, tools, frameworks, and experiments distilled by FinFNS.

---

## Vision

Mélange has two closely related goals:

**Build a great modular Dune: Awakening mod list.**

And, just as importantly:

**Help build the modding ecosystem that will make that mod list possible.**

Dune: Awakening modding is young. The tools, techniques, documentation, and catalog of available mods are still developing.

Rather than waiting for that ecosystem to appear on its own, Mélange aims to help provide some of the infrastructure around it.

That means building and documenting a practical workflow around:

- Mod Organizer 2
- Wabbajack
- Nexus Mods
- UE4SS
- Community-developed modding tools and frameworks
- Reproducible mod installation
- Modular configuration
- Testing and experimentation
- Documentation for both mod users and mod authors

As the Dune: Awakening modding community grows, Mélange should grow with it.

### Long-Term Goal

The eventual goal is a **large, modular overhaul of Dune: Awakening** built from a curated collection of compatible mods.

Like Borscht and Smörgåsbord, Mélange is intended to give players a solid default experience while still allowing them to decide what belongs in their own game.

It should be possible to use Mélange as a ready-to-play mod list.

It should also be possible to use it as a foundation for experimentation.

### Core Strength

**Modularity.**

Mélange isn't intended to dictate one "correct" way to play Dune: Awakening.

As the available mod catalog expands, individual components should remain organized and understandable through Mod Organizer 2 wherever practical.

Enable something.

Disable something.

Experiment.

Build the Arrakis you want.

**Mélange provides the spice. You decide how much to add.**

---

## What is Mélange?

Mélange is a **Wabbajack-powered Mod Organizer 2 mod list for Dune: Awakening**.

At its current stage, it is best understood as both a mod list and a **modding framework**.

Mélange provides a standardized environment for installing, organizing, testing, and eventually distributing Dune: Awakening mods through Mod Organizer 2.

The project currently brings together several pieces of the emerging Dune: Awakening modding ecosystem, including:

- **Mod Organizer 2** for mod management, conflict visibility, profiles, and modular configuration.
- **Wabbajack** for reproducible installation and distribution of the complete environment.
- **UE4SS** for runtime mod support.
- **WPS Dune Framework** support for mods built around the WPS ecosystem.
- **ReShade** support for graphics customization and post-processing.
- Dune-specific tooling and integration needed to make these systems work together cleanly.

Where practical, Mélange keeps modifications isolated inside Mod Organizer 2 rather than requiring users to manually scatter files throughout their Dune: Awakening installation.

### What Mélange Is Today

Early Mélange releases focus heavily on:

**Infrastructure, compatibility, organization, documentation, and proving that a robust modding workflow for Dune: Awakening can work.**

The modlist itself will expand alongside the community and the available catalog of compatible mods.

### What Mélange Can Become

As Dune: Awakening modding matures, Mélange can gradually evolve from scaffolding into the larger modular overhaul it is intended to become.

New gameplay systems, quality-of-life improvements, interface changes, visual enhancements, balance changes, and other modifications can be incorporated as they become available and prove compatible.

The framework comes first.

The overhaul gets built on top of it.

---

## Requirements

Mélange has very few requirements. If your PC can run the base game, it can run this mod list.

### Dune: Awakening — Steam

You must own and install **Dune: Awakening through Steam**.

Mélange is built specifically around the Steam release of Dune: Awakening. Other versions of the game are not supported.

### Windows 10 or Windows 11

Mélange requires a **64-bit installation of Windows 10 or Windows 11**.

There are no additional hardware requirements beyond those required to run Dune: Awakening itself.

**If you can run the base game on your PC, you can run Mélange.**

### Required Windows Components

The following Windows components are required:

| Requirement | Notes |
| --- | --- |
| **[.NET Framework 4.8](https://learn.microsoft.com/en-us/dotnet/framework/install/)** | Required Windows component. Install or enable it if it is not already present on your system. |
| **[Microsoft Visual C++ v14 Redistributable (x64)](https://aka.ms/vc14/vc_redist.x64.exe)** | The 64-bit Microsoft Visual C++ runtime is required. Install or repair it using Microsoft's official installer if needed. |

### Wabbajack

You must use the **latest available version of Wabbajack** to install Mélange.

Older versions of Wabbajack may not contain the Dune: Awakening game support required by this mod list.

### Do Not Install Mod Organizer 2 Separately

**Do not download or install your own copy of Mod Organizer 2 for Mélange.**

Mod Organizer 2 is already included as part of the Mélange installation created by Wabbajack.

Using a separate MO2 installation is unnecessary and may result in an incorrectly configured installation.

Want to understand why Mélange is built around Mod Organizer 2? See **[Why Mélange Uses Mod Organizer 2](Why_Melange_Uses_MO2.md)**.

### Single-Player Modding

Mélange is intended for **single-player modded gameplay**.

Mélange provides its own configured method for launching the game in its modded environment. Follow the Mélange installation and launch instructions rather than manually modifying the game's launch configuration.

---

## Installation

Mélange is installed using **Wabbajack**.

### Before You Begin

Before installing Mélange:

1. Install **Dune: Awakening through Steam**.
2. Launch Dune: Awakening normally through Steam at least once.
3. Make sure the game reaches the main menu successfully, then close it.
4. Download and use the **latest version of Wabbajack**.

> [!IMPORTANT]
> **Do not install Mod Organizer 2 separately.**
>
> Mélange includes its own portable, preconfigured Mod Organizer 2 installation. Wabbajack will install everything required for the Mélange modding environment.

### Installing Mélange

Download Mélange through Wabbajack and follow the installation prompts.

Choose an installation location outside of protected Windows folders such as `Program Files`.

Installing everything on an SSD is preferred to a traditional HDD.

A simple location such as:

`C:\Modlists\Melange`

or

`D:\Modlists\Melange`

is recommended.

Your Mélange installation does **not** need to be on the same drive as Dune: Awakening.

Once Wabbajack has completed successfully, launch **ModOrganizer.exe** from your Mélange installation folder.

### Launching Dune: Awakening

Launch the modded game **from inside Mélange's Mod Organizer 2 installation** using:

**Dune: Awakening - Singleplayer (Modded)**

When playing with Mélange, launch the game using **Dune: Awakening - Singleplayer (Modded)** from inside Mod Organizer 2 rather than using Steam's normal **Play** button.

Steam should still be running in the background. Mélange's launch entry starts the game through the configured modded environment required for its components to function correctly.

### Detailed Installation Guide

For complete step-by-step instructions, see the **[Mélange Installation Guide](InstallationGuide.md)**.

The guide covers installation, recommended folder locations, Steam update settings, launching Mélange through Mod Organizer 2, and basic installation verification.

---

## Updating Mélange

Mélange will evolve alongside Dune: Awakening and its developing modding community. Updates may add new mods, update existing components, change configuration, or adjust the framework in response to game updates.

For guidance on adding mods, creating personal profiles, organizing custom content, and maintaining the distinction between **Mélange** and **Your Mélange**, see **[Customizing Mélange](CUSTOMIZING_MELANGE.md)**.

### Before Updating

**Read the release notes before installing an update.**

Some Mélange updates may include special instructions, require a clean installation, or contain changes that affect user-added mods and customizations.

Unless the release notes specifically state otherwise, updates will be installed through **Wabbajack**.

### Updating with Wabbajack

Mélange updates will be distributed through **Wabbajack**.

Always use the **latest available version of Wabbajack** and read the release notes for the Mélange version you are installing before beginning an update.

For complete update instructions, see **[How to Update Mélange](How_to_Update_Melange.md)**.

### Your Own Mods and Customizations

Mélange is intended to be modular, and you are free to experiment with additional mods.

However, **anything you add or change outside the official Mélange configuration is your responsibility to maintain.**

A Mélange update may change mods, priorities, separators, configuration files, executables, or other parts of the MO2 environment.

Before making extensive personal changes, consider creating your own **Mod Organizer 2 profile** and keeping your additions clearly separated and identifiable from the mods supplied by Mélange.

Separate profiles make it easier to preserve the official Mélange configuration for testing and troubleshooting while maintaining your own customized setup.

Mélange uses the `[NoDelete]` naming convention to help protect user-added mods and personal MO2 profiles from Wabbajack's normal cleanup during updates.

For details on protecting your customizations, see **[How to Update Mélange](How_to_Update_Melange.md)**.

### When a Clean Installation Is Required

Occasionally, an update may require a completely fresh Mélange installation.

If that is necessary, it will be clearly stated in the release notes.

**Do not assume that deleting and reinstalling Mélange is required for every update.**

### After a Dune: Awakening Update

Game updates may temporarily break mods, UE4SS functionality, WPS components, or other parts of the Mélange framework.

If Dune: Awakening has just received an update, check the current Mélange release information before assuming that your installation is broken.

Early in the game's modding lifecycle, some disruption after game updates should be expected.

---

## Included Mods & Frameworks

Mélange is currently focused primarily on establishing a reliable modding foundation for Dune: Awakening.

As the game's modding community grows, this section will expand with it.

### Core Framework

The current Mélange environment includes:

| Component | Purpose |
| --- | --- |
| **Mod Organizer 2** | Provides the portable mod-management environment used by Mélange. |
| **FNS Dune: Awakening MO2 Plugin** | Provides native Dune: Awakening integration and Dune-specific mod installation handling for Mod Organizer 2. |
| **UE4SS Runtime** | Provides runtime support required by Lua and other UE4SS-based mods. |
| **WPS Dune Framework** | Provides framework support for compatible WPS Dune mods. |
| **Mélange ReShade Framework** | Provides an optional foundation for ReShade presets and graphics customization. |

Additional supporting components may be included as required by individual mods.

### Optional Graphics Components

Mélange may also provide optional graphics components through its ReShade framework.

These are kept modular so users can choose whether they want to use them rather than having visual changes forced upon the entire mod list.

### Gameplay Mods

The gameplay portion of Mélange is intentionally small at this stage.

Dune: Awakening modding is still developing, and Mélange will not include mods simply to make the list appear larger.

Mods will be added as useful, compatible, and maintainable options become available.

### Mod Authors

Mélange does not exist to replace individual mod pages or separate mod projects.

Whenever practical, mods should remain independently hosted and maintained by their original authors, with **Nexus Mods** serving as the preferred home for the broader Dune: Awakening modding community.

Mélange's role is to bring compatible projects together into a cohesive, reproducible modding environment.

### Complete Mod List

A complete list of the mods, frameworks, utilities, and optional components included in each Mélange release will be maintained separately as the project grows.

---

## Documentation

More detailed information about installing, customizing, updating, troubleshooting, and developing for Mélange is available in the project guides:

- **[Installation Guide](InstallationGuide.md)** — Installing Mélange and launching it for the first time.
- **[Customizing Mélange](CUSTOMIZING_MELANGE.md)** — Adding your own mods, profiles, and other customizations.
- **[How to Update Mélange](How_to_Update_Melange.md)** — Updating through Wabbajack while protecting personal additions.
- **[Troubleshooting Guide](TROUBLESHOOTING.md)** — Diagnosing installation, launch, framework, and mod problems.
- **[Why Mélange Uses Mod Organizer 2](Why_Melange_Uses_MO2.md)** — The reasoning behind Mélange's MO2, Wabbajack, and Nexus Mods workflow.
- **[Mod Author Guide](Mod_Author_Guide.md)** — Guidance for authors building and packaging Dune: Awakening mods.

---

## Support & Community

Mélange support, development discussion, and general Dune: Awakening modding discussion are hosted in the **Smörgåsbord Discord community**.

Dedicated Mélange channels will provide areas for:

- Announcements and release information
- Installation and technical support
- General Mélange discussion
- Dune: Awakening modding discussion
- Mod development and experimentation
- Testing upcoming Mélange changes

A permanent Discord invitation will be added here before the first public release.

### Before Asking for Help

Before reporting a problem, please determine whether it also occurs with the official Mélange configuration.

When asking for help, provide:

- Your **Dune: Awakening game version**
- Your **Mélange version**
- A description of what happened
- What you expected to happen
- Whether the problem occurs using the supplied Mélange profile
- Whether you have added, removed, updated, enabled, disabled, or modified any mods
- Any relevant screenshots
- Any relevant logs or error messages

*"It doesn't work"* remains an unfortunately ineffective diagnostic tool.

### Modified Installations

Experimentation is encouraged.

However, there is an important distinction between:

> **Mélange**

and

> **Your Mélange**

The official Mélange configuration is the environment primarily tested and supported by the project.

If you add mods, remove components, update individual mods independently, change framework versions, or otherwise customize the installation, support becomes **best-effort**.

If you encounter a problem with a customized installation, you may be asked to reproduce it using the official Mélange configuration before it can be investigated as a Mélange issue.

### GitHub Issues

GitHub Issues may eventually be used for confirmed Mélange bugs, documentation problems, and development tracking.

Please use the Discord for general installation help and troubleshooting rather than opening a GitHub issue for every support question.

### Troubleshooting Documentation

If you encounter installation, launch, framework, mod, or update problems, start with the **[Mélange Troubleshooting Guide](TROUBLESHOOTING.md)**.

The guide is designed to help isolate which part of the Mélange environment is failing before making unnecessary changes or reinstalling components.

---

## For Mod Authors

For practical guidance on WPS Dune tooling, packaging, dependencies, testing, and publishing mods for the developing Dune: Awakening ecosystem, see the **[Mélange Mod Author Guide](Mod_Author_Guide.md)**.

### Nexus Mods

Whenever practical, mod authors are encouraged to publish their work on **Nexus Mods**.

A centralized and searchable home for Dune: Awakening mods makes it easier for:

- Players to discover mods
- Authors to distribute and update their work
- Other modders to find dependencies and complementary projects
- Mod lists such as Mélange to build reproducible installations
- The community to preserve documentation, version history, and compatibility information

This does not mean every Dune: Awakening project must exist exclusively on Nexus Mods.

The goal is simply to help establish Nexus as a reliable central hub for the game's modding community.

### Mod Organizer 2 Friendly Packaging

Where possible, mods should be packaged so they can be installed and managed cleanly through **Mod Organizer 2**.

Mélange aims to keep modifications isolated from the base game installation whenever practical.

Well-structured archives make mods easier to:

- Install
- Remove
- Update
- Troubleshoot
- Test independently
- Include in Wabbajack mod lists

As Dune: Awakening modding techniques develop, Mélange will document recommended packaging structures for common mod types.

### WPS Dune Mods

Mélange supports mods built around the **WPS Dune Framework** and can integrate compatible WPS packages into its Mod Organizer 2 environment.

Mod authors do not need to design their projects specifically for Mélange.

Where possible, Mélange's tooling should adapt properly packaged mods to the environment rather than requiring authors to maintain a special "Mélange version."

### Dependencies and Documentation

Mod authors are encouraged to clearly document:

- Required frameworks and dependencies
- Installation requirements
- Known incompatibilities
- Supported game versions
- Configuration options
- Update instructions
- Whether an existing save is required or affected

Clear metadata and documentation make mods significantly easier to support individually and as part of larger mod lists.

### Want to Experiment?

Absolutely.

Mélange itself exists because Dune: Awakening modding still has a great deal of unexplored territory.

Experiments, prototypes, diagnostic tools, reverse-engineering discoveries, and seemingly small quality-of-life mods can all help move the ecosystem forward.

The Smörgåsbord Discord will include space for Dune: Awakening mod development, technical discussion, testing, and collaboration.

**If you're building something for Dune: Awakening, you're exactly the kind of person Mélange hopes to encourage.**

---

## Credits & Acknowledgements

Mélange would not exist without the developers, mod authors, tool creators, reverse engineers, testers, and community members building the infrastructure around Dune: Awakening modding.

### Core Projects & Tools

Special thanks to the developers and contributors behind:

- **Wabbajack** — for making reproducible mod list installation and distribution possible.
- **Mod Organizer 2** — for providing the foundation of Mélange's modular mod-management environment.
- **UE4SS** — for providing the runtime modding framework that makes many forms of Unreal Engine modding possible.
- **WPS Dune Framework** — for helping establish an early framework and ecosystem for Dune: Awakening mods.
- **ReShade** — for providing the graphics injection and post-processing framework used by Mélange's optional visual components.
- **Nexus Mods** — for providing hosting, discovery, versioning, and community infrastructure for mod authors and users.

### Dune: Awakening Modding Community

Dune: Awakening modding is still being figured out.

Every tool, experiment, technical discovery, tutorial, framework, mod, bug report, and shared piece of knowledge helps make the next project easier to build.

Mélange benefits directly from that collective work.

Thank you to everyone experimenting with the game and sharing what they learn.

### Mod Authors

Individual mod authors retain credit and ownership of their respective work.

Mélange is a curated installation and integration project. Inclusion of a mod in Mélange does not imply ownership, authorship, or endorsement by that mod's creator unless explicitly stated otherwise.

Where applicable, individual mods and their authors will be credited in the complete Mélange mod list and associated documentation.

### Wabbajack Community

Additional thanks to the **Wabbajack developers and community** for reviewing and accepting Dune: Awakening support into Wabbajack, and for maintaining the infrastructure that makes projects like Mélange possible.

### Funcom & Dune

**Dune: Awakening** is developed and published by **Funcom**.

**Dune** and its associated universe were created by **Frank Herbert** and are the property of their respective rights holders.

Mélange is an unofficial community modding project and is not affiliated with or endorsed by Funcom or the Dune rights holders.

### FinFNS / Fluffernuttersandwich

Mélange is created and maintained by **FinFNS (Fluffernuttersandwich)** as part of the broader Smörgåsbord modding community.

And to everyone who tests Mélange, breaks Mélange, reports why Mélange broke, or builds something new for it:

**Thank you.**

---

## The Road Ahead

Mélange is starting small.

Dune: Awakening modding is still young, the available mod catalog is limited, and many of the tools and techniques needed for more ambitious projects are still being discovered.

That's exactly why Mélange exists now.

The goal isn't simply to wait for a mature modding ecosystem and then build a mod list from it.

The goal is to help build that ecosystem.

As new tools are developed, new techniques are discovered, and new mods appear, Mélange will grow alongside them.

What begins as infrastructure and scaffolding can eventually become the large, modular Dune: Awakening overhaul Mélange is intended to be.

Until then:

**Experiment. Break things. Learn something. Share what you discover.**

The desert doesn't become a garden overnight. It begins with people willing to plant something.

Don't worry, we'll leave a little desert for the Maker.

---

## Support the Project

Mélange is and will remain free.

If you enjoy the project and would like to support the time that goes into developing, testing, documenting, and maintaining it, you can leave something in the tip cup:

**[Support FinFNS on Ko-fi](https://ko-fi.com/finfns)**

Tips are always appreciated, but never expected.

Using, testing, reporting bugs, helping other users, creating mods, and contributing knowledge to the Dune: Awakening modding community are all equally valuable ways to support the project.

---
