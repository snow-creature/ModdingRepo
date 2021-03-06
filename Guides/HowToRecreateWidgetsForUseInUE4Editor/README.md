# How To Recreate DRG's Built-In Widgets

#### Before we get into it, I should mention that this is *tedious* stuff and isn't *necessary* for UI modding. The benefit of doing this is that you can actually see a facsimile of the UI you're working on in editor which helps development.

## Table of Contents
 - [What you need](#What-you-need)
   - [Necessary](#Necessary)
   - [Optional](#Optional)
 - [Getting Started](#Getting-Started)
   - [Determining the Parent Class](#Determining-the-Parent-Class)


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

We're gonna open that with UAssetGui and we'll be presented with this:

<img src="./Assets/FirstOpen.jpg">

Now open the ue4.27 editor and your modding project. What you want to do is the same as if you were dummying a Blueprint. For now, recreate the path <code>Content\UI\Menu_Loadout\\</code> and open the <code>Menu_Loadout</code> folder.

### Determining the Parent Class
In UAssetGUI, expand the <code>Export&nbsp;Data</code> section and find <code>Export&nbsp;26&nbsp;(Menu_Loadout_C)</code> and expand it. There should be four entries: 

<img src="./Assets/Export26.jpg">

Click on <code>UStruct&nbsp;Data</code> to see its values. We don't need to expand it since all we care about is the <code>Value&nbsp;2</code> value for the <code>Super Struct</code> property, which is <code>Window&nbsp;Widget</code>