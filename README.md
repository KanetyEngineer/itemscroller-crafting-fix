# Item Scroller – Crafting Fix (Minecraft 1.21.11)

**This is not Masa's original Item Scroller.** It is an unofficial 1.21.11 build of
[Andrews54757/itemscroller-crafting-fix](https://github.com/Andrews54757/itemscroller-crafting-fix),
rebuilt on top of the official Item Scroller 1.21.11 branch
([sakura-ryoko/itemscroller `LTS/1.21.11`](https://github.com/sakura-ryoko/itemscroller/tree/LTS/1.21.11), version 0.30.8).
Please report problems with this build here, not to masa, sakura-ryoko or Andrews54757.

## Why rebuild on the official branch?

The core ideas of the Crafting Fix fork (mass crafting through the recipe book protocol, and a
toggle so you don't have to hold the mass craft key) were later adopted by the official Item Scroller
(`massCraftUseRecipeBook`, `massCraftHold` and the `massCraftToggle` hotkey). The old fork's code base
targets Minecraft 1.21 and predates the 1.21.2 recipe book rewrite, so this build starts from the
maintained 1.21.11 code and re-applies what was still missing.

## Differences from the official Item Scroller 0.30.8

* **Honey crafting / recipe remainders** – new option `dropRecipeRemainder` (default ON). Remainders of
  the selected recipe (e.g. Glass Bottles from Honey Blocks, Buckets from Cake) are thrown out together
  with the crafting results, so AFK mass crafting doesn't get stuck on a full inventory.
  Remainders that are also an ingredient of the recipe are kept.
* `massCraftInterval` defaults to **1** tick (was 2), as in the Crafting Fix fork.
* Recipe book mass crafting (`massCraftUseRecipeBook`) is ON by default and `rateLimitClickPackets`
  and `carpetCtrlQCraftingEnabledOnServer` are OFF by default (same as upstream).

## Usage

1. Install Fabric Loader for 1.21.11 and **MaLiLib for 1.21.11 (0.27.19 or newer, below 0.28.0)**.
2. Put `itemscroller-craftfix-fabric-1.21.11-<version>.jar` in `mods`. Remove the regular Item Scroller jar
   (both use the mod id `itemscroller`).
3. Store a recipe by middle clicking the crafting output, then hold `massCraft` (Ctrl+Alt+C) or bind
   `massCraftToggle` to keep crafting without holding a key.

## 日本語

Andrews54757 氏の itemscroller-crafting-fix を Minecraft 1.21.11 向けに作り直した非公式版です。
公式 Item Scroller の 1.21.11 版（0.30.8）をベースに、Crafting Fix 独自の動作を足しています。

* レシピ本を使った一括クラフト（`massCraftUseRecipeBook`）と、キーを押し続けなくてよいトグル
  （`massCraftHold` / ホットキー `massCraftToggle`）は公式版にすでに取り込まれているので、そのまま使えます。
* 追加: `dropRecipeRemainder`（既定 ON）。ハチミツブロックを作ったときのガラス瓶など、レシピの「残り物」を
  クラフト結果と一緒に捨てます。放置一括クラフトでインベントリが詰まらなくなります。
* `massCraftInterval` の既定値を 1tick にしています（公式は 2）。
* 動かすには 1.21.11 用の MaLiLib（0.27.19 以上 0.28.0 未満）が必要です。通常の Item Scroller とは同時に入れないでください。

## License / Credits

LGPLv3 (see `LICENSE.txt`), same as the original.

* Item Scroller by [masa (maruohon)](https://github.com/maruohon/itemscroller)
* 1.21.x maintenance by [sakura-ryoko](https://github.com/sakura-ryoko/itemscroller)
* Crafting Fix by [Andrews54757](https://github.com/Andrews54757/itemscroller-crafting-fix) and contributors
* 1.21.11 Crafting Fix build by KanetyEngineer

The full git history of upstream is kept in this repository; the changes of this build are in the
commits on top of upstream `LTS/1.21.11` (`0fd8a52`).

---

[![](https://jitpack.io/v/sakura-ryoko/itemscroller.svg)](https://jitpack.io/#sakura-ryoko/itemscroller)

Item Scroller
==============
Item Scroller is a Minecraft mod that adds various convenience features for moving items
inside inventory GUIs. Examples are scrolling the mouse wheel over slots with items in them
or Shift/Ctrl + click + dragging over slots to move items from them in various ways etc.

Item scrolling is basically what the old NEI mod did and Mouse Tweaks also does.
This mod has some different drag features compared to Mouse Tweaks, and also some special
villager trading related helper features as well as crafting helper features.

For more information and downloads of the already compiled builds,
see https://www.curseforge.com/minecraft/mc-mods/item-scroller

Compiling
=========
* Clone the repository
* Open a command prompt/terminal to the repository directory
* run 'gradlew build'
* The built jar file will be in build/libs/
