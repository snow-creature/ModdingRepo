# How To Recreate DRG's Built-In Widgets

#### Before we get into it, I should mention that this is *tedious* stuff and isn't *necessary* for UI modding. The benefit of doing this is that you can actually see a facsimile of the UI you're working on in editor which helps development.

## Table of Contents
 - What you need
 - Getting Started


##   What you need:
### Necessary
 - UnrealEngine 4.27
 - FSD.pak
 - DRGPacker
 - UAssetGUI (or a similar way to read the export map of a cooked .uasset file)
### Optional
 - DRG Header Dumps (This is optional because you can technically get all the info and more from the export maps, but I prefer to use these as well)
 - [_Content.tree]() (This is a handy text file that has a tree showing all the folders in <code>Content</code> and which .uasset files they contain)

## Getting Started
The first step is to figure out what file you need to look at and what it's path is. For this guide, I'm going to walk you through recreating the Menu_Loadout widget. This is the widget for the window where you change your weapons, set skins, etc. The naming and locations for a lot of the bigger widgets like this are pretty much just as simple, and related component widgets are usually in the same folder.

If you haven't already, copy and unpack your FSD.pak, then open the content folder. The file we need can be found here: <code>Content\UI\Menu_Loadout\Menu_Loadout.uasset</code>

We're gonna open that with UAssetGui and we'll be presented with this