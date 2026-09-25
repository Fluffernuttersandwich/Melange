# Mélange Mod Author Guide

> **Guidance for Dune: Awakening mod authors who want their work to integrate cleanly with the growing WPS, Nexus Mods, Mod Organizer 2, and Mélange ecosystem.**

Mélange wants more Dune: Awakening mods.

More importantly, we want mod authors to be able to build those mods without creating special versions specifically for Mélange.

For most authors interested in runtime Dune: Awakening modding, the best place to start is the existing **WPS Dune ecosystem**:

- **WPS Dune Launcher**
- **WPS Dune Framework**
- **WPS Dune Modder Kit**

Build your mod correctly for that ecosystem, document it well, and let Mélange handle the Mod Organizer 2 side wherever possible.

---

## Table of Contents

- [Start Here](#start-here)
- [WPS Dune Launcher](#wps-dune-launcher)
- [WPS Dune Framework](#wps-dune-framework)
- [WPS Dune Modder Kit](#wps-dune-modder-kit)
- [Choosing an Approach](#choosing-an-approach)
- [Package Your Mod Cleanly](#package-your-mod-cleanly)
- [Use Dependencies Instead of Bundling Them](#use-dependencies-instead-of-bundling-them)
- [Use mod.json](#use-modjson)
- [Version and Document Your Mod](#version-and-document-your-mod)
- [Test What You Release](#test-what-you-release)
- [Publish on Nexus Mods](#publish-on-nexus-mods)
- [Mélange Compatibility](#mélange-compatibility)
- [Getting Involved](#getting-involved)

---

# Start Here

If you want to create Dune: Awakening mods, start by familiarizing yourself with the WPS tooling.

### WPS Dune Launcher

**[WPS Dune Launcher on Nexus Mods](https://www.nexusmods.com/duneawakening/mods/18)**

The WPS Dune Launcher provides the player-facing runtime environment for compatible mods, including the required UE4SS runtime.

### WPS Dune Framework

**[WPS Dune Framework on Nexus Mods](https://www.nexusmods.com/duneawakening/mods/21)**

The Framework provides shared services and a documented Lua API for compatible mods.

Its goal is simple:

**Common functionality should not need to be independently reinvented by every mod author.**

---

# WPS Dune Launcher

The WPS Dune Launcher provides the standard runtime environment for WPS-compatible mods.

For authors, this gives you a known target rather than requiring every player to assemble their own UE4SS installation.

Compatible mods can declare requirements and load-order information so the launcher can help players construct a valid environment.

Mélange takes a different route on the player-facing side by managing these components through Mod Organizer 2, but it intentionally preserves compatibility with the WPS ecosystem.

**You should not need to build a separate Mélange version of your mod.**

---

# WPS Dune Framework

The WPS Dune Framework is the main shared API available to Lua mod authors.

Its documented capabilities include areas such as:

- UI and appearance
- Animation and physics
- Environment, camera, and audio
- Player and game-state snapshots
- Settings and saved preferences
- Mod-to-mod communication
- Managed changes and restoration
- Lifecycle helpers
- Diagnostics

Framework adoption is optional. Not every mod needs it.

If the Framework already provides a supported operation you need, however, using that API can reduce duplicated reverse engineering and give multiple mods a common way to interact with the game.

Keep the Framework as a **separate dependency** rather than copying it into your mod.

---

# WPS Dune Modder Kit

The optional **WPS Dune Modder Kit** is available from the WPS Dune Framework's Nexus page.

If you are beginning Dune: Awakening mod development, this is the recommended starting point.

The kit currently includes starter projects covering:

- Independent Lua
- Settings
- Lifecycle
- Tables
- Merchants
- Backpack functionality
- UI
- Materials
- Animation
- Physics
- Environment
- Mod communication
- Hybrid mods
- Native UE4SS mods
- Content staging

It also provides an author workbench, API lookup, packaging tools, offline Lua testing, Visual Studio Code support, native UE4SS helpers, Unreal content tooling, and author documentation.

> [!TIP]
> Start with the smallest starter that demonstrates the capability you actually need.
>
> A working small mod is a better foundation than a complicated project containing systems you do not yet use.

---

# Choosing an Approach

Not every mod needs the same architecture.

A simple mod may only require:

```text
Lua
```

Another may use:

```text
Lua
+
WPS Dune Framework
```

More advanced projects may eventually require:

```text
Lua
+
Native UE4SS
```

or a hybrid approach.

Choose the least complicated architecture that accomplishes the goal.

Do not add dependencies merely because they exist.

Likewise, do not spend days rebuilding functionality already exposed through a documented Framework API unless you have a technical reason to do so.

---

# Package Your Mod Cleanly

Good packaging benefits everyone.

A mod should ideally be installable without requiring the user to manually scatter individual files across several directories.

Use the WPS package structure appropriate for your project and test the final archive you intend to release.

Avoid:

```text
MyMod.zip
└── RandomFolder
    └── AnotherFolder
        └── ActualMod
```

The archive should have a predictable structure that the intended tooling can understand.

Mélange's Dune-specific MO2 integration is designed to adapt supported WPS packages to the Mélange environment.

**Let the tooling perform the adaptation.**

Do not create unusual archive structures solely for Mélange.

---

# Use Dependencies Instead of Bundling Them

If your mod requires the WPS Dune Framework, declare it as a dependency.

Do not include another copy of the Framework inside your mod.

The same general principle applies to shared infrastructure:

```text
Your Mod
    ↓
Declares Dependency
    ↓
Shared Framework
```

rather than:

```text
Your Mod
├── Your Files
├── Another Framework Copy
├── Another Runtime Copy
└── Who Knows Which Version Wins
```

One shared dependency is much easier for players, mod managers, and other authors to maintain.

---

# Use mod.json

WPS supports `mod.json` metadata for compatible packages.

Use it.

Good metadata gives tooling information about your mod rather than forcing users to manage relationships manually.

Document things such as:

- Mod identity
- Version
- Package type
- Dependencies
- Load-order requirements
- Conflicts
- Build compatibility

Keep this information accurate when releasing updates.

Metadata that says the wrong thing can be worse than metadata that says nothing.

---

# Version and Document Your Mod

Use meaningful version numbers.

For example:

```text
1.0.0
1.1.0
1.1.1
```

When releasing an update, include a short changelog.

Tell users when an update:

- Adds features
- Fixes bugs
- Changes requirements
- Changes configuration
- Requires a newer Framework
- Requires a newer game build
- Breaks compatibility with an older version

Also document what your mod actually requires.

Do not make users discover dependencies through crashes.

---

# Test What You Release

Static checks and successful packaging are useful.

They are not substitutes for running the mod in Dune: Awakening.

Before making gameplay claims about a release, test the release archive in-game.

At minimum, verify:

```text
Package
   ↓
Install
   ↓
Launch
   ↓
Feature Works
   ↓
Restart
   ↓
Feature Still Works
```

Test updates as updates when possible, not only as fresh installations.

If your mod changes persistent state or saved settings, test those paths too.

> [!IMPORTANT]
> A script compiling successfully proves that it compiled.
>
> It does not prove that the mod works in the game.

---

# Publish on Nexus Mods

Mélange strongly encourages Dune: Awakening mod authors to publish their work on **Nexus Mods**.

A central, discoverable catalog benefits the entire community.

A useful Nexus page should make it easy to find:

- What the mod does
- Current version
- Requirements
- Installation instructions
- Game compatibility
- Framework requirements
- Changelog
- Known limitations
- Author
- Support information

Whenever possible, keep the original mod on its own Nexus page rather than distributing it exclusively as part of Mélange.

That allows standalone users, Mélange users, and future mod lists to use the same release.

---

# Mélange Compatibility

You do **not** need permission from Mélange to make a compatible mod.

You also should not need a special:

```text
Mélange Edition
```

If your mod is properly packaged for the supported Dune modding ecosystem, Mélange should do the integration work wherever practical.

If Mélange cannot correctly handle a reasonable WPS-compatible package, that may be something **we should improve in Mélange's tooling** rather than something every author should work around.

We would much rather fix our MO2 integration once than ask twenty mod authors to package their work twenty different ways.

## When Mélange-Specific Work May Be Appropriate

There may still be legitimate reasons for:

- Compatibility patches
- Optional configurations
- Conflict resolution
- Special load-order requirements

Those should solve an actual compatibility problem rather than exist merely because Mélange uses MO2.

---

# Getting Involved

Dune: Awakening modding is still young.

That means experimentation, reverse engineering, documentation, failed prototypes, and shared discoveries are all valuable.

If you discover something useful, document it.

If you create a reusable technique, share it.

If the WPS Framework already solves your problem, use it.

If Mélange's MO2 integration mishandles a reasonable mod package, tell us.

And if you build something interesting:

**Put it on Nexus Mods so people can find it.**

The ecosystem only grows if people contribute to it.

---

# Resources

- **[WPS Dune Launcher](https://www.nexusmods.com/duneawakening/mods/18)**
- **[WPS Dune Framework & Modder Kit](https://www.nexusmods.com/duneawakening/mods/21)**
- **[Why Mélange Uses Mod Organizer 2](Why_Melange_Uses_MO2.md)**
- **[Customizing Mélange](CUSTOMIZING_MELANGE.md)**
- **[Mélange README](README.md)**

---

# Build Something

Mélange can provide infrastructure.

WPS can provide tools and shared APIs.

Nexus Mods can provide a home for your work.

But none of those things create the mods.

**That's where you come in.**

Experiment. Document what you learn. Package it cleanly. Test it. Publish it.

Let's see what Dune: Awakening modding can become.

---

**[Return to the Mélange README](README.md)**