### Fork of [MinecraftHeads](https://github.com/TheLuca98/MinecraftHeads) by [TheLuca98](https://github.com/TheLuca98)

# MinecraftHeads

This repository is effectively a mirror for the data made available by the [Minecraft-Heads.com public API](https://minecraft-heads.com/scripts/api.php). The data is provided here as a single JSON file and is updated weekly by a script that runs on GitHub Actions.

## Purpose

To allow developers to fetch the entire dataset with a single HTTP call and without putting an unnecessary burden on the Minecraft-Heads.com servers.

## Downloads

The file is available via CDN, courtesy of [raw.githack.com](https://raw.githack.com/):

```
https://raw.githack.com/Random-MC/MinecraftHeads/master/heads.json
```

Or you can click here: **[direct download link](https://raw.githack.com/Random-MC/MinecraftHeads/master/heads.json)**

## Usage

The database is a standard JSON file. Each row in the file is a head.
Example of a head object:
```json
{
    "name": "@ Icon",
    "uuid": "e978ac35-5f37-4f57-833c-5d6983afa18d",
    "category": "alphabet",
    "value": "eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvZGFkNDQ4OTkxMjAxNmYwZjkyOTVmMWY...",
    "hash": "dad4489912016f0f9295f1f3a780f641c8a72eda11032643f7dbd619c101073a",
    "tags": [
        "Punctuation Mark",
        "Icons (Ironblock)"
    ]
}
```


The value of the `hash` column is a portion of the skin URL: `https://textures.minecraft.net/texture/<HASH>`.

The skin URL is used to generate the `textures` property (to include in the user profile), which is essentially the following JSON object, but base64-encoded:

```json
{ "textures": { "SKIN": { "url": "https://textures.minecraft.net/texture/<HASH>" } } }
```

Additional resources on this topic:

- [Example of a user profile](https://sessionserver.mojang.com/session/minecraft/profile/853c80ef3c3749fdaa49938b674adae6)
- [Mojang API on wiki.vg](https://wiki.vg/Mojang_API#UUID_to_Profile_and_Skin.2FCape)
- [minotar/skin-spec on GitHub](https://github.com/minotar/skin-spec)