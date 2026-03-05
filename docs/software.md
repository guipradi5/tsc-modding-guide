# Software

## Read Unity game files

The first good step to translate a game is getting some of the files or texts in order to translate them.

This game has all of its texts divided in various files and formats and at the same time, divided at multiple "levels". Some texts are accessible in the form of .txt files formatted as JSON files, while other texts are only obtainable in binary format within the game files.

For editing texts in binary format directly, you may need a hexadecimal editor:

- [HexEditor](https://mh-nexus.de/en/hxd/) - A powerful hex editor used to view and edit binary data at the byte level, allowing you to directly modify binary files and locate specific text patterns within game data

**To extract these files you'll need a Unity game asset extractor**. There are a number of programs that can do these, but my favorites and the ones mainly used for the spanish translation of The Silver Case were:

- [UABEA](https://github.com/nesrak1/UABEA/releases) - For exploring the game files, internal folder structure and export/import assets
- [UnityEX](https://platinmods.com/threads/unityex-assets-modding-tool.135921/) - For exporting/importing assets
- [AssetStudio](https://github.com/Perfare/AssetStudio/releases) - For quickly watching images, sounds, videos and exporting them

And with any of them you have to read the resources.assets file inside the TheSilverCase_Data folder inside the game installation folder, normally it's located in:

```
C:\Program Files (x86)\Steam\steamapps\common\The Silver Case\TheSilverCase_Data
```

The resources.assets file contains 95% of the game files that are used across the chapters.

Game files used for multiple menus like the Load screen, the main screen, new game screen, settings, screen, etc. are located inside the level1, level2, level3, level4, level5 and level6 files.

I recommend using **UnityEX** for the main bulk of exporting and reimporting assets as it's the most reliable one with the file formats.

**UABEA** I mainly used for the chapter dialogues, but in hindsight I would have sticked with UnityEX. UABEA is still GREAT for finding GameObjects, elements, filter specific assets, where texts are and to edit specific assets.

**AssetStudio** is great for exporting all images and videos from the game the first time around. It also enables you to review what has been imported already and what not as it has a great asset preview window.

Finally, for the actual game logic, it can be read directly using a program called:

- [dnSpy](https://dnspy.org/)

The game logic is located in:

```
The Silver Case\TheSilverCase_Data\Managed\Assembly-CSharp.dll
```

Just open this file with dnSpy 32 bits, and you can check the internal game code, written in C#.

There are some texts that are located inside the Assembly-CSharp.dll file and should be replaced. You can do a text search using dnSpy or export all files to a new folder and open it with VSCode to do a general search in a more comfortable way, locate the texts to translate, go back to dnSpy and replace.
