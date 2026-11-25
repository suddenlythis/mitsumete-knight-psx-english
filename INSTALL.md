# Installing the Mitsumete Knight English translation (v1.0.1)

The download contains only the changes to the game's data track, not the game. You need your
own disc image of Mitsumete Knight (Japan), the Redump version.

## What you need

- The Redump version of **Mitsumete Knight (Japan)** (product code SLPM-86068): one `.cue` and
  two `.bin` files, as Redump catalogues it. Track 1 is the game's data and Track 2 is an
  audio track.
- The file that gets patched must be exactly:

  | File | Size | SHA-1 |
  |---|---|---|
  | `Mitsumete Knight (Japan) (Track 1).bin` | 666,909,600 bytes | `93652d280a42c73e9b382319101233d61e98a074` |

  With any other file the patch refuses to apply. Track 2 is not changed.
- xdelta3, or a front end for it such as Delta Patcher or xdelta UI. Rom Patcher JS in a web
  browser also applies `.xdelta` files.
- A PlayStation emulator. Tested in PCSX-Redux; also started in DuckStation.

## What is in the zip

| File | What it is |
|---|---|
| `MitsumeteKnight-EN-v1.0.1.xdelta` | The patch for Track 1 |
| `Mitsumete Knight (English).cue` | Optional cue sheet, only for the side-by-side alternative below. Most people do not need it |
| `README.txt` | The release notes |

## How to apply

Patch Track 1 with the `.xdelta`. Keep the file name, and open your usual `.cue`. That is all.

### With Delta Patcher

1. Original file = your `Mitsumete Knight (Japan) (Track 1).bin`
2. XDelta patch = `MitsumeteKnight-EN-v1.0.1.xdelta`
3. Tick Backup original file in the settings, then Apply patch.

### With the command line

xdelta3 writes a new file, so rename the original first:

```
ren "Mitsumete Knight (Japan) (Track 1).bin" "original.bin"
xdelta3 -d -s "original.bin" MitsumeteKnight-EN-v1.0.1.xdelta "Mitsumete Knight (Japan) (Track 1).bin"
```

### Check the result

The patched file is 666,909,600 bytes with this SHA-1 checksum:

| File | SHA-1 after patching |
|---|---|
| Track 1 `.bin` | `59fd90081b4c20d65299473bc6f3962e40a64ed0` |

## Alternative: keep the Japanese and English discs side by side

Leave your files alone, save the patched file as `Mitsumete Knight (English) (Track 1).bin`
in the same folder, and open `Mitsumete Knight (English).cue` from the zip. That cue sheet
uses your original `Mitsumete Knight (Japan) (Track 2).bin` for the audio track.

## Updating from v1.0

Patch the original Japanese Track 1 again, not the file you patched with v1.0. Saves made in the
game with v1.0 should still work. Emulator save states made with v1.0 may keep some of the old
text, so load the game normally instead.

## After patching

Start a new game. A save made with the Japanese game stores the hero's name in Japanese
letters, which the English game cannot show properly. A save state made on the Japanese game
keeps the old program and text in memory, so load the game normally instead.

Controls: Circle confirms, Cross cancels, the D-pad moves the cursor. If a choice does not
react to Circle, press Up or Down first.

## Tested on

PCSX-Redux. The opening and name entry were also seen in DuckStation. Not tested on real
hardware.
