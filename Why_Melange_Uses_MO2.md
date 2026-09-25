# Why Mélange Uses Mod Organizer 2

> **Why Mélange is building Dune: Awakening modding around Mod Organizer 2, Wabbajack, Nexus Mods, and a portable modding environment.**

Dune: Awakening modding is still young.

That gives the community an unusual opportunity.

Instead of inheriting years of established habits and trying to retrofit better tooling afterward, we can build around strong mod-management practices from the beginning.

Mélange uses **Mod Organizer 2 (MO2)** because it provides more than a convenient list of installed mods.

It gives us an architecture for keeping mods organized, configurations reproducible, experiments reversible, frameworks manageable, and the original game installation substantially cleaner.

Combined with **Wabbajack**, **Nexus Mods**, and Mélange's Dune-specific integration, MO2 provides the foundation for the kind of modding ecosystem we would like to see grow around Dune: Awakening.

---

## Table of Contents

- [Why Mod Organizer 2?](#why-mod-organizer-2)
- [Keeping the Game Directory Clean](#keeping-the-game-directory-clean)
- [Virtualized Mod Management](#virtualized-mod-management)
- [Mods Remain Separate](#mods-remain-separate)
- [Conflicts Become Visible](#conflicts-become-visible)
- [Profiles Make Experimentation Easier](#profiles-make-experimentation-easier)
- [Frameworks Belong in the Mod Manager Too](#frameworks-belong-in-the-mod-manager-too)
- [Making WPS Mods MO2-Friendly](#making-wps-mods-mo2-friendly)
- [Why Mélange Uses Wabbajack](#why-mélange-uses-wabbajack)
- [Why Nexus Mods Matters](#why-nexus-mods-matters)
- [Learning from Older Modding Ecosystems](#learning-from-older-modding-ecosystems)
- [Why Not Build Around Steam Workshop?](#why-not-build-around-steam-workshop)
- [A Better Dune Modding Pipeline](#a-better-dune-modding-pipeline)
- [What This Means for Mod Authors](#what-this-means-for-mod-authors)
- [What This Means for Players](#what-this-means-for-players)
- [Mélange Is Not Trying to Own Dune Modding](#mélange-is-not-trying-to-own-dune-modding)
- [Building the Ecosystem Early](#building-the-ecosystem-early)
- [Useful Links](#useful-links)

---

# Why Mod Organizer 2?

There are many ways to install a mod.

The simplest is usually:

```text
Download Files
      ↓
Copy Files Into Game
      ↓
Hope Everything Works
```

That can be perfectly adequate for a single simple modification.

It becomes much less attractive when the installation grows to include:

- Multiple mods
- Runtime frameworks
- Lua mods
- Graphics modifications
- Compatibility patches
- Alternative configurations
- Different mod versions
- Development tools
- Experimental mods
- User customizations

At that point, knowing **what installed which file** becomes important.

So does knowing:

- Which mod is overwriting another
- Which version is installed
- Which components are optional
- Which mods belong together
- What changed before something broke
- How to disable something without deleting it
- How to reproduce a known-good setup

That is where Mod Organizer 2 becomes valuable.

Mélange is not using MO2 merely because it is a familiar mod manager.

**Mélange uses MO2 because its design matches the kind of Dune: Awakening modding environment we want to build.**

---

# Keeping the Game Directory Clean

Traditional manual mod installation often means placing files directly into the game's directory.

Over time, that directory can become a mixture of:

```text
Original Game Files
+ Mod A
+ Mod B
+ Framework A
+ Framework B
+ Configuration Changes
+ Files From a Mod You Forgot About
+ Something You Installed Six Months Ago
```

Eventually, nobody remembers exactly where everything came from.

Removing a mod may require manually identifying its files.

Updating a mod may leave obsolete files behind.

Two mods may silently overwrite one another.

Troubleshooting can turn into archaeology.

Mélange avoids this wherever practical by keeping mod-managed content inside the Mod Organizer 2 environment.

The goal is simple:

> **The game directory should belong to the game whenever possible. The mod manager should manage the mods.**

There are technical situations where runtime modding requires interaction with the game's directory or executable environment.

Mélange handles those situations as part of its configured infrastructure rather than expecting every user to manually reproduce them.

---

# Virtualized Mod Management

MO2's virtual filesystem is one of the primary reasons Mélange uses it.

Instead of permanently combining every enabled mod into the physical Dune: Awakening installation, MO2 constructs the environment the game needs when it is launched through Mélange.

Conceptually:

```text
Steam Game Files
       +
Mélange Frameworks
       +
Enabled Mods
       +
Configuration
       ↓
Virtual Game Environment
       ↓
Dune: Awakening
```

The original files and individual mod packages remain substantially separated on disk.

That separation gives us something extremely valuable:

**reversibility.**

A mod can often be disabled without manually reconstructing the original game directory.

That makes experimentation dramatically safer and easier.

---

# Mods Remain Separate

When Mod A and Mod B are installed manually into the same directory, their files may become physically mixed together.

With MO2, they can remain distinct:

```text
mods\
├── Mod A
├── Mod B
├── Mod C
└── Mod D
```

That makes basic questions much easier to answer.

For example:

> Which files belong to this mod?

> Can I disable it?

> Can I replace it?

> Did another mod overwrite it?

> Is this an official Mélange component or something I added?

This separation is particularly important for **Your Mélange**.

User-added mods can be clearly identified using the Mélange convention:

```text
[NoDelete] Mod Name
```

That provides both organization and protection from normal Wabbajack cleanup of user-added mod folders during updates.

---

# Conflicts Become Visible

File conflicts are not inherently bad.

Sometimes one mod is intentionally supposed to overwrite another.

For example:

```text
Original Mod
      ↓
Compatibility Patch
```

The important thing is knowing that the conflict exists and understanding which file should win.

Manual installation can hide that relationship because the later file simply replaces the earlier one.

MO2 makes those relationships much easier to inspect.

This allows Mélange and its users to reason about conflicts instead of simply accumulating overwritten files in the game directory.

---

# Profiles Make Experimentation Easier

MO2 profiles allow different configurations to coexist within the same Mélange installation.

For example:

```text
Mélange
```

can remain the official baseline while:

```text
[NoDelete] My Mélange
```

contains your personal configuration.

You might also maintain:

```text
[NoDelete] Testing
```

or:

```text
[NoDelete] Graphics Experiment
```

or:

```text
[NoDelete] Mod Development
```

This is useful for players.

It is even more useful for troubleshooting and mod development.

If something breaks in your customized setup, you can ask:

> Does this also happen with official Mélange?

That one test can eliminate a huge number of possible causes.

As with user-added mods, Mélange recommends prefixing personal profiles with:

```text
[NoDelete]
```

so they remain clearly identifiable as user-created content and are protected from normal Wabbajack cleanup.

---

# Frameworks Belong in the Mod Manager Too

Dune: Awakening modding is not limited to simple replacement files.

Modern Unreal Engine modding can involve runtime frameworks and supporting infrastructure such as:

- UE4SS
- WPS components
- Lua mods
- Runtime modifications
- ReShade
- Graphics add-ons
- Configuration files
- Supporting tools
- QoL Plugins

These components can become difficult to manage when every framework has its own manual installation procedure.

Mélange's approach is:

> **If we can manage it cleanly through MO2, we should.**

This means framework components can be:

- Identified
- Versioned
- Enabled or disabled where appropriate
- Updated deliberately
- Distributed consistently
- Reproduced through Wabbajack

Users should not need to memorize the internal installation architecture of every framework simply to use a mod list.

That complexity belongs in the tooling.

---

# Making WPS Mods MO2-Friendly

The existing Dune: Awakening modding ecosystem includes mods packaged around the **WPS Dune** environment.

Mélange does not want mod authors to create an entirely separate:

```text
Mélange Edition
```

of every WPS mod.

Instead, Mélange's Dune-specific MO2 integration is designed to recognize supported package structures and adapt them to the environment expected by the runtime.

Conceptually:

```text
WPS Mod Archive
       ↓
Mélange / MO2 Installation
       ↓
Dune-Specific Package Handling
       ↓
Expected Runtime Structure
       ↓
UE4SS / WPS Environment
```

That distinction is important.

**The mod author should package the mod correctly.**

**The mod manager should handle the mod-management problem.**

We would rather improve Mélange's tooling than ask every Dune: Awakening mod author to maintain special packages specifically for us.

---

# Why Mélange Uses Wabbajack

MO2 provides the mod-management environment.

**Wabbajack makes that environment reproducible.**

A manually written installation guide might say:

```text
Install Framework A
Install Framework B
Download Mod C
Use Version 1.4
Change This Setting
Move This File
Rename That Folder
Install Patch D
Make Sure E Loads After F
```

Every manual step is an opportunity for two users to end up with different installations.

Wabbajack allows Mélange to describe a known configuration and automate much of its reconstruction.

That gives us a pipeline like:

```text
Mélange Definition
       ↓
Wabbajack
       ↓
Portable MO2 Environment
       ↓
Known Mod Versions
       ↓
Known Configuration
```

That reproducibility is enormously valuable for:

- Installation
- Updates
- Troubleshooting
- Testing
- Support
- Development

When someone reports a problem with the official Mélange configuration, we have a much better idea of what they are actually running.

---

# Why Nexus Mods Matters

Mélange would like to see **Nexus Mods become a central home for Dune: Awakening mods**.

That is not because every mod must exist in one place.

It is because a young modding community benefits from having a recognizable, searchable hub where players can discover mods and authors can publish them.

A healthy central catalog makes it easier to find:

- Mods
- Authors
- Requirements
- Dependencies
- Version information
- Changelogs
- Installation instructions
- Compatibility information
- Bug reports
- Updates
- Related mods

It also works naturally with the kind of mod-management and automated installation ecosystem Mélange is building.

The goal is not merely:

> **Make Mélange easier to install.**

The larger goal is:

> **Help Dune: Awakening develop a sustainable PC modding ecosystem.**

Mélange benefits if Dune modding grows.

Mod authors benefit if players can find their work.

Players benefit if mods are easier to discover and manage.

The entire ecosystem becomes stronger when those interests align.

---

# Learning from Older Modding Ecosystems

Dune: Awakening is not Funcom's first moddable survival game.

Older modding communities give us useful examples of both what works and what becomes difficult at scale.

**Conan Exiles** developed a substantial modding community, with Steam Workshop becoming a major distribution mechanism.

Steam Workshop offers real advantages.

It is:

- Convenient
- Integrated into Steam
- Easy for players to discover
- Easy to subscribe to
- Familiar to many users

For casual modding, that convenience can be excellent.

But convenience at installation time is not the only consideration.

As a modding ecosystem becomes larger and more complicated, users also begin to care about:

- Precise version control
- Controlling when mods update
- Preserving known-good configurations
- Managing conflicts
- Keeping multiple configurations
- Reproducing an exact mod setup
- Troubleshooting individual components
- Automated mod-list installation
- Separating mods from the base game
- Maintaining large curated lists

Those are areas where a dedicated mod manager provides significant advantages.

Mélange would rather build around those capabilities **before** the Dune: Awakening ecosystem becomes large enough that changing established habits is difficult.

---

# Why Not Build Around Steam Workshop?

Steam Workshop solves a different problem than Mod Organizer 2.

Workshop is primarily designed around:

```text
Find Mod
   ↓
Subscribe
   ↓
Steam Downloads It
```

That is wonderfully simple.

But Mélange needs more than subscription management.

We want:

```text
Discover Mod
      ↓
Choose Version
      ↓
Install Through Mod Manager
      ↓
Keep Mod Isolated
      ↓
Inspect Conflicts
      ↓
Control Configuration
      ↓
Preserve Known-Good Setup
      ↓
Reproduce It Through Wabbajack
```

Those goals favor a dedicated mod-management ecosystem.

Another important consideration is **automatic updating**.

Automatic updates are convenient until a known-good modded configuration depends upon a particular combination of:

```text
Game Version
+
Framework Version
+
Mod Version
+
Configuration
```

If one piece changes automatically, the entire configuration can change without the user intentionally changing it.

Mélange's philosophy is that users should have as much practical control over their modded environment as possible.

> **Updates should be deliberate when compatibility matters.**

This is the same reason we recommend controlling when Dune: Awakening itself updates.

---

# A Better Dune Modding Pipeline

The ecosystem Mélange would like to encourage looks roughly like this:

```text
                    MOD AUTHOR
                        │
                        ▼
                   Nexus Mods
                        │
              ┌─────────┴─────────┐
              │                   │
              ▼                   ▼
        Individual User       Mélange
              │                   │
              ▼                   ▼
      Mod Organizer 2         Wabbajack
              │                   │
              └─────────┬─────────┘
                        ▼
                Mod Organizer 2
                        │
                        ▼
               Dune: Awakening
```

The important part is that Mélange does **not** need to become the exclusive distribution point for mods.

The original mod page remains the author's home.

Mélange can reference and integrate those mods while Wabbajack and MO2 handle reproducible installation.

That means a mod can serve:

- Standalone users
- Mélange users
- Other future mod lists
- Mod developers
- Advanced users building their own configurations

without requiring separate releases for each group.

---

# What This Means for Mod Authors

Mélange does not want to dictate how authors create their mods.

We do want to encourage a few practices that benefit everyone.

Where practical:

- Publish mods through a discoverable community hub such as Nexus Mods.
- Package mods cleanly.
- Document dependencies.
- Document compatible game versions.
- Maintain useful version numbers.
- Include changelogs.
- Avoid unnecessary manual overwrites.
- Make updates understandable.
- Keep archives friendly to mod-management tools.

If a mod uses WPS or UE4SS, package it correctly for that ecosystem.

Let Mélange handle the MO2 integration where possible.

You should not need to maintain:

```text
Normal Version
```

and:

```text
Mélange Version
```

unless there is a genuine technical reason.

---

# What This Means for Players

For players, this approach means slightly more structure in exchange for substantially more control.

Instead of treating modding as:

```text
Copy Files Until Game Changes
```

Mélange encourages:

```text
Install
Enable
Test
Disable
Compare
Update Deliberately
```

That makes it easier to experiment without losing track of the environment.

It also makes asking for support much easier.

There is an enormous difference between:

> I installed a bunch of files into the game directory over the last six months.

and:

> The problem occurs with official Mélange 1.x using this profile and disappears when I disable this mod.

The second problem can actually be investigated.

---

# Mélange Is Not Trying to Own Dune Modding

Mélange is a mod list and modding framework.

It is **not** intended to become a gatekeeper for Dune: Awakening mods.

Authors should be free to publish independently.

Players should be free to install mods without Mélange.

Other people should be free to build different mod lists and different tools.

Mélange's goal is to provide infrastructure that makes all of that easier.

We would like to encourage an ecosystem where:

```text
Authors publish mods
        ↓
Players can find them
        ↓
Mod managers can install them
        ↓
Mod lists can reference them
        ↓
Authors retain their own distribution
        ↓
Everyone benefits as the catalog grows
```

A healthy modding community should be larger than any individual mod list.

---

# Building the Ecosystem Early

There is another reason Mélange is being built now rather than waiting for thousands of mods to exist.

**Habits form early.**

Once a community has spent years distributing mods through scattered archives, Discord attachments, manual installation instructions, Workshop subscriptions, and incompatible packaging conventions, creating a unified management workflow becomes much harder.

Dune: Awakening is early enough that we can encourage better habits while the ecosystem is still forming.

That means encouraging:

**Nexus Mods for discovery and distribution.**

**Mod Organizer 2 for management and isolation.**

**Wabbajack for reproducible mod lists.**

**Mélange for Dune-specific integration, documentation, and a curated environment.**

**WPS and UE4SS for the runtime capabilities that make many advanced mods possible.**

These pieces do not need to compete with one another.

They solve different parts of the same problem.

---

# Why This Matters

Today, Dune: Awakening has a relatively small mod catalog.

That will hopefully not remain true.

If the community grows, today's infrastructure decisions become tomorrow's foundation.

We can either wait until there are hundreds of mods and then try to solve:

- Distribution
- Organization
- Version control
- Conflicts
- Dependencies
- Updates
- Framework management
- Reproducibility
- Troubleshooting

or we can begin building those systems now.

Mélange chooses the second option.

The immediate result may look like a lot of infrastructure supporting a relatively small number of mods.

That's intentional.

**We're building the shelves before the library is full.**

---

# Useful Links

- **[Mélange README](README.md)**
- **[Mélange Installation Guide](InstallationGuide.md)**
- **[Customizing Mélange](CUSTOMIZING_MELANGE.md)**
- **[How to Update Mélange](How_to_Update_Melange.md)**
- **[Mélange Troubleshooting Guide](TROUBLESHOOTING.md)**

Additional mod-author and development documentation will be added as the Dune: Awakening modding ecosystem develops.

---

# The Foundation

Mélange uses Mod Organizer 2 because we want Dune: Awakening modding to remain manageable as it grows.

We use Wabbajack because reproducibility matters.

We encourage Nexus Mods because discoverability and sustainable distribution matter.

We integrate existing Dune frameworks because authors should not have to reinvent their work for our mod list.

And we keep building the infrastructure because waiting until the ecosystem is already fragmented makes the problem much harder to solve.

Dune: Awakening modding is still young.

That's not a limitation.

It's an opportunity.

**Mélange provides the spice. The community decides what Arrakis becomes.**

---

**[Return to the Mélange README](README.md)**  
**[Read the Installation Guide](InstallationGuide.md)**  
**[Read Customizing Mélange](CUSTOMIZING_MELANGE.md)**  
**[Read How to Update Mélange](How_to_Update_Melange.md)**  
**[Read the Troubleshooting Guide](TROUBLESHOOTING.md)**