# framework-plugins
A repository containing NWN plug-ins and utilities designed to work with SquattingMonk's nwn-core-framework.  Squatting Monk has created an awesome event management framework that is not dependent on game-external systems, such as NWNX, although using NWNX is still an option with his system.  The framework is extremely flexible and allows you to subscribe, prioritize and cancel any function to any game event, including standard game events, custom events, timer events and NWNX events (if desired).  The framework can be sourced [here](http://github.com/squattingmonk/nwn-core-framework).

An example of the framework in action can be seen in the open source [Dark Sun - Sands of Time](https://github.com/tinygiant98/darksun-sot) Persistent World NWN:EE module.  [Nasher](https://github.com/squattingmonk/nasher.nim) is required to build this module, but you can peruse the code without building the module.

## Plugin Anatomy:

The vast majority of plugins that I author contain 6-7 scripts:
* *_i_config:  contains configuration options
* *_i_const: contains constant values
* *_i_events: contains the public-facing events that are directly accessed by nwn-core-framework
* *_i_main: contains the private functionality that makes the plugin work and supports public events
* *_i_text: contains all text-based strings, held in one place to be easily translated
* *_l_plugin: contains the library and event registration functionality
* *_l_dialog: contains custom dialogs

## Plugin Descriptions:

**Persistent World Management (pw).**  This plug-in contains most of the major administrative tasks associated with running a persistent NWN module, such as registering characters, maintaining feat lists, booting players and other menial tasks associated with module management.  The vast majority of functions within this plug-in are sourced from Edward Beck's HCR2 system.

**Bleed (pw_bleed).**  This plugin contains the HCR2 bleed subsystem that allows for player's bleed out from 0 to -10 hit points, providing various messages to attract help from nearby players as well as options for healing and recovery.

**Business (pw_business).**  This plugin is designed to control the opening and closing of various businesses throughout the module.  It will provide for locking/closing, unlocking/opening of doors, warning players that an area is closed, removing players from a closed area, preventing players from logging out of a restricted area and then logging in during closed hours, dm control of whether an area is open/closed, etc.

**Corpse (pw_corpse).**  This plugin contains the HCR2 corpse subsystem that allows players to interact with the corpse of deceased characters, including moving the body and healing/resurrecting it (even while offline).

**Crowd (pw_crowd).**  This plugin allows for a simulated crowd in any area in the module.  Crowds are created through the use of initializer items that have specified variables set on them.  Crowds have multiple features, including time of day, number of crowd members, specific resrefs, specific clothing and specific dialog.  Any number of crowds can be running in any area of the module at the same time.

**Deity (pw_deity).**  This plugin contains the HCR2 Deity subsystem that allow players to specify and deity and recieve a deity-specific chance of be resurrected that increases based on multiple factors.

**DMFI (pw_dmfi).**  WIP.  This plugin contains an updated version of DMFI 1.09.

**Fugue (pw_fugue).**  This plugin contains the HCR2 Fugue subsystem that provides an area for dead players to inhabit before being resurrected or respawning.

**Hunger, Thirst, Fatigue (pw_htf).**  This plugin contains the HCR2 HTF subsystem that allow module owners to apply hunger, thirst, fatigue requirements and penalties to their players.

**Loot (pw_loot).**  This plugin contains the HCR2 Loot subsystem that creates lootable corpses of dead characters.

**Resources (pw_resources).** This plugin contains bioware-script overrides for all default creatures and placeables, forcing all non-custom creatures and placeables to inform the core framework that they are attempting to run scripts.  Its primary purpose is to ensure the framework has complete control over all events occurring in the module.

**Rest (pw_rest).**  This plugin contains the HCR2 Rest subsystem that allows for item requirements for rest and limiting spell and feat recovery.

**Ring (lotr_ring).**  A customized plugin for a LOTR module.  This plugin allows for the placement and control of The One Ring, ensuring access to it is limited, appropriate negative consequences are dealt when it's obtained and rewarding players for destroying it in the fires of Mt. Doom.

**TagBased (ds_tagbased).**  This plugin contains libraries wich allow any game object to be called via tag-based scripting.  This gets around the bioware limitation of only allowing this for items.  Events are sourced from the core-framework and scripting for tagbased scripting of other objects is very much like that for items.

**Test (test).**  This plugin contains a ridiculous number of chat commands that can be used to test various parts of a module during development.

**Torch (pw_torch).**  This plugin contains the HCR2 Torch subsystem which allows for timing torches and lanterns to ensure they are limited.  This subsystem has been modified to use util_i_time.

**Travel (ds_travel).**  A customized plugin for the Dark Sun server, this plugin allows for random encounters when travelling over large areas.  During an encounter, this plugin will create an encounter area, port the players to that area, and allow for additional players to join the encounter when they return to the encounter area.

**UnID (pw_unid).**  This plugin contains the HCR2 UnID on Drop subsystem with allows for items dropped on the ground for more than a specified amount of time to become unidentified.

**Wells (lotr_wells).**  A customized plugin for a LOTR module.  This plugin allow for benefits to be doled out to users of specific good/evil wells.  Additionally, wells can be charged or drained through the use of various liquids by like-aligned or opposite-aligned characters.

## Utility Descriptions

**Chat (util_i_chat).**  This utility allows any module to have a chat command system which allows the chat line to be used much like a command line in a terminal, with commands, long/short options and key/value pairs available for use.

**Data (util_i_data).**  This utility contains functions that replace the bioware variable handling functions to allow for additional flexibility in where variables are stored as well as provide for use of sqlite database for players/module in a single command.

**Override (util_i_override).**  The utility contains bioware override functions that have been modified to do something slightly different than the original version, such as accepting lists instead of single objects, etc.

**Quest (util_i_quest).**  This utility allows any module to have a quest management system that automates quest advancement, journal entries (both NWNX and non-NWNX), prerequisites, reward and prewards.

**Time (util_i_time).**  This utility provides for various system and game time functions and time manipulation.  All functions in this utility are based on game times and do not interface with real world/computer system times.


