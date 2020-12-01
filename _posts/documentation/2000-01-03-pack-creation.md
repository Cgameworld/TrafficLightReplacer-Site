---
layout: post
title: Pack Creation
category: documentation
---
Tutorial about how to make packs!
rewrite all of this!

# Table of Contents
{: .no_toc}

* TOC
{:toc}

# Props

## General
Before creating a traffic light pack, traffic light props are needed. For general prop asset creation information refer to this [article on cslm](https://cslmodding.info/asset/prop/) 

If you already have working traffic light props skip to [here](/documentation/pack-creation/#xml-types) ??
## Traffic Light Prop Specifics

Traffic lights props use a special shader, the Traffic Light Shader. 

Because of this it is best to use the vanilla traffic light template since it already has that configured

unlike regular props, Traffic lights require _i maps???? explain when ive made one lol


## Preparation
Before making a XML file, it is suggested to publish your traffic light props as an unlisted listing

This is because the mod refers to the Prefab name of the prop, which differs whether the prop is published or not.

# XML Types

This mod can read two different kinds of XML configuration files

## OneSize
For traffic light packs that replace vanilla traffic light props one to one. This is best for legacy/limited prop packs

## MultiSize
For packs that have traffic lights for different road sizes/ have several variations per road size. This requires more prop models than the OneSize format, but it can take full advantage of the mod's features

make table with check boxes?
# XML Template

As a starting point to make a new configuration, use these blank XML templates [here](https://github.com/Cgameworld/TrafficLightReplacer/tree/master/TrafficLightReplacer/Templates) or export them using the mod's [Pack Creator Helper](/documentation/pack-creation/#pack-creator-helper)

If you are on Windows, [Notepad++](https://notepad-plus-plus.org/downloads/) with the XMLTools plugin is recommended to edit these files, since it includes features such as text highlighting, syntax checking and pretty printing.  

Example Blank XML Template:\
<img src="/assets/images/multisize-template-example.png" alt="Example XML Template"/>

For examples of fully working xml files, look at the mod's [internal XML presets](https://github.com/Cgameworld/TrafficLightReplacer/tree/master/TrafficLightReplacer/DefaultXMLS)

Read below for the explaination of the elements

# XML Elements

### PackName
The name of the pack shown in game

### OneSize
[Type](#xml-types) of XML file, ```true``` means it is a OneSize configuration, ```false``` means it is a MultiSize configuration

### Prefab
Prefab name of the prop, use the update/copy buttons in the Pack Creator Helper to grab


### Type
Defines the type of prop to replace

For **OneSize** files, types can be set to ```Main``` , ```Mirror``` , ```Ped Signal```, ```Signal Pole```, or ```Signal Pole Mirror``` with only one prop per type.

- All the types (Main, Mirror, Ped Signal, Signal Pole) need to be assigned to a prop, otherwise the pack will not work
- In the case of Signal Pole Mirror, if left blank the mod will use the non-mirrored signal pole prop

For **MultiSize** files types can be set to ```Small```, ```Medium```, ```Large```, ```All``` , or ```Signal Pole``` .

- Types Small, Medium and Large and All can be assigned to multiple props, while Signal Pole can only be assigned to one prop
- Type All means that the prop is added to all size categories
- The XML file is required to have at least one prop assigned to types (Small, Medium and Large, Signal Pole) or (All, Signal Pole), otherwise the pack will not work

### Name
Name of the prop shown in the customization dropdown (**MultiSize only**)

### Description
Tooltip shown in the customization dropdown (**MultiSize only**)

### Transform
(**optional**)\
\
Default transform settings for the pack\

### DropdownSelectionIndex
(**optional, MultiSize only**)\
\
Default variation selected for each size in the customization menu. Use this if you want something other than the first prop for a size category selected when loading the pack\
\
**SmallRoads** - index for Small Roads dropdown\
**MediumRoads** - index for Medium Roads dropdown\
**LargeRoads** - index for Large Roads dropdown

index values start at 0\
\
Example:\
![dropdown selection index example](/assets/images/DropdownSelectionIndexExample.png)\
To have the second traffic light in this list to be selected on default, change the MediumRoads element value to ```1```

### ForceDefaultSideSignalPole
(**optional, MultiSize only**)\
Forces the signal pole light to be always at the opposite side of the road when the default side is enabled, instead of only when the optional setting in the global option menu settings is enabled (only used in special cases) 

# Pack Creator Helper

In the mod, there's a toolbox window that helps with making an XML file for the mod called the Pack Creator Helper. To show it, go into the [general mod settings](/documentation/settings/), and enable "Show Pack Creator Helper"

![helper](/assets/images/modsettings-pack.png)

Once enabled you should see a window that looks like this:

![pack window](../../assets/images/pack-creator-helper.png)

## Generate Template Pack XMLS

This button exports two XML files, one for each configuration [type](/documentation/pack-creation/#xml-types)

## Update
This copies the selected prop's name into the name box. Use the [Find It! 2](https://steamcommunity.com/sharedfiles/filedetails/?id=2133885971) mod to search and to select a prop

## Copy

Copies the prop name to the clipboard

## Folder

Opens the TLRLocal folder, place XML files you want to test here

## Load TLRLocal Folder

Toggles whether to load XML files in the TLRLocal folder to the Pack dropdown

## Refresh Packs

Refreshes the main Pack Dropdown

# Loading a Traffic Pack

First press the folder icon and place an XML config in there

To load traffic lights into the mod check "Load TLR Local Folder" in the Pack Creator Helper. Then click "Refresh Packs"




# Limitations


Revise this!!
- OneSize lights can not take advantage of the mod's "Customize Lights" feature but replace the vanilla lights one to one
- MultiSize traffic lights define median lights to replace since they are hidden. In this example 

They do not support mirrored traffic lights, they are replaced with a blank prop currently?
![example-1](/assets/images/twotrafficlightexample.png)
- in the future multisize lights can support main light median replacement is planned to be added. support may be added to remedy this


For pack variations that have main lights in the median like vanilla, use the oneSize mode for now, since that supports its unlike multisize, might add in the future?

Mention that this mod doesn't even work for LHD!!

# Unsorted

To load a custom prop pack, place a TLRConfig.xml file in the workshop asset folder when publishing. 

For testing, place a xml with any name in the TLRLocal folder generated by the mod’s Pack Creator Helper Window (enable in settings). Also check the “Load TLRLocal Folder” checkbox for the mod to load XMLs in that folder.

XML templates can be exported with the Pack Creator Helper or can be found here: [xml templates](https://github.com/Cgameworld/TrafficLightReplacer/tree/master/TrafficLightReplacer/Templates)

I’ll make a more detailed tutorial later on about this

The mod reads files from

C:\Program Files (x86)\Steam\steamapps\workshop\content\255710 (any enabled/subscribed subfolder) - file in workshop folder has to named TLRLocal.xml

\AppData\Local\Colossal Order\Cities_Skylines\TLRLocal - can be named anything

Two xml types exist, onesize and multisize. Onesize (mostly for legacy packs) replaces vanilla signals one to one , while multisize is the main custom implementation that has support for traffic light variations, etc.

All the types (small, medium, large, signal pole) have to have at least one member otherwise the mod doesn’t work

[url=https://github.com/Cgameworld/TrafficLightReplacer] GitHub page [/url]