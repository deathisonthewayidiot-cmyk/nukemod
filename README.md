# Nuke (Fabric, Minecraft Java 26.3)

Adds one block: the **Nuke**. TNT's much worse cousin.

* **Arm it** with flint and steel, a fire charge, or a redstone signal.
* **10 second countdown** (the block glows red), then it detonates with a blast
  radius of **48** (vanilla TNT is 4).
* **Craft it**: 4 TNT (corners) + 4 gunpowder (edges) + 1 nether star (centre).
  Also in the creative inventory, Redstone Blocks tab.
* Respects the `tntExplodes` game rule.

Tune it in `src/main/java/com/nukemod/NukeBlock.java`: `BLAST_POWER` and `FUSE_TICKS`.
A radius of 48 is big. If a server stutters, lower it.

## Getting the jar

### Option A: no setup, let GitHub build it
1. Create a new GitHub repo and push this folder to it.
2. Open the **Actions** tab, wait for the `build` run to finish.
3. Download the **Artifacts** zip. Use `nuke-1.0.0.jar` (not the `-sources` jar).

### Option B: build locally
Requires **JDK 25** and an internet connection.

    ./gradlew build          # Windows: gradlew.bat build

The jar is written to `build/libs/nuke-1.0.0.jar`.

## Installing
1. Install Fabric Loader 0.20.1 or newer for Minecraft 26.3.
2. Put these in your `mods` folder:
   * `nuke-1.0.0.jar`
   * Fabric API `0.165.0+26.3` (or newer for 26.3)

Also works on a dedicated server, as it has no client-only code.
Players on a server also need the mod (the block needs its textures).

## Status
Written against the official Fabric 26.3 template (Loader 0.20.1, Loom 1.19,
Fabric API 0.165.0+26.3). Method signatures were cross-checked against Fabric API
and Paper sources for 26.3, but this project has **not been compiled against the
real game jars**. If `./gradlew build` reports an error, it will point at
a specific line in `NukeBlock.java` or `NukeMod.java`.
