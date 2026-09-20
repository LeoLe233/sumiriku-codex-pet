# Sumiriku Codex Pet

Sumiriku is an animated custom pet for the Codex desktop app: an blue-and-white cat with green eyes, goggles, a gray jacket, and a fluffy tail.

| Idle | Jumping |
| --- | --- |
| ![Sumiriku idle animation](previews/idle.gif) | ![Sumiriku jumping animation](previews/jumping.gif) |

Includes nine animation states and 16 look directions in the version 2 pet format. The spritesheet is a transparent 1536 × 2288 WebP with 192 × 208 cells.

## Import into Codex

### macOS

1. [Download this repository as a ZIP](https://github.com/LeoLe233/sumiriku-codex-pet/archive/refs/heads/main.zip) and unzip it.
2. In Finder, press **Command + Shift + G**, enter `~/.codex`, and open it. Create a folder named `pets` if it does not exist.
3. Copy the **sumiriku** folder from the downloaded repository into `pets`. Copy the folder containing `pet.json` and `spritesheet.webp`, not the whole repository. If a Sumiriku folder already exists, back it up before replacing it.
4. Open **Codex → Settings → Pets**, click **Refresh**, and select **Sumiriku**. If it does not appear, quit and reopen Codex.
5. Use `/pet` or the **Show pet** command to display it.

The final layout should be:

```text
~/.codex/pets/sumiriku/
├── pet.json
└── spritesheet.webp
```

If you set a custom `CODEX_HOME`, use its `pets` folder instead of `~/.codex/pets`.

### Terminal alternative (macOS)

Run these commands from the folder where you want to download the repository. The install step refuses to replace an existing Sumiriku folder.

```sh
git clone https://github.com/LeoLe233/sumiriku-codex-pet.git
cd sumiriku-codex-pet
pet_dir="${CODEX_HOME:-$HOME/.codex}/pets"
mkdir -p "$pet_dir"
if [ -e "$pet_dir/sumiriku" ]; then
  echo "Sumiriku already exists. Back it up before replacing it."
else
  cp -R sumiriku "$pet_dir/sumiriku"
  echo "Installed. Open Codex Settings → Pets → Refresh, then select Sumiriku."
fi
```

### Windows

Download and unzip the repository, then copy its `sumiriku` folder into `%USERPROFILE%\.codex\pets\`. Create the `pets` folder if needed. If you set `CODEX_HOME`, use that directory instead. Back up any existing Sumiriku folder first. In the desktop app, open **Settings → Pets**, refresh, and select **Sumiriku**.

The package was validated on macOS; the Windows instructions use the same local pet-folder layout and have not been tested on Windows.

## Troubleshooting

- Keep `pet.json` and `spritesheet.webp` together, directly inside the `sumiriku` folder.
- Keep `spriteVersionNumber` set to `2`; this sheet contains 11 rows.
- Use an up-to-date desktop app that supports custom v2 pets.
- If animation is static, check your operating system's Reduce Motion setting.
- This package is for local desktop installation. The web pet upload has a different size requirement.

The package layout follows the installed Codex `hatch-pet` skill. For the current pet selection and refresh controls, see [OpenAI's pet documentation](https://learn.chatgpt.com/docs/pets).

## Package

- `sumiriku/pet.json` — pet identity and spritesheet configuration.
- `sumiriku/spritesheet.webp` — the complete animated pet.
- `previews/` — animation previews for this page; not needed for installation.

This repository preserves the existing Sumiriku artwork and its latest installed jumping animation. The published atlas passed the v2 validator with no errors or warnings.

* Character Copyright Owned by LeoLe233
