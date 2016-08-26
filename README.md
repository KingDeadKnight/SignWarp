<img src="https://raw.githubusercontent.com/alejandroliu/pocketmine-plugins/master/Media/SignWarp-icon.png" style="width:64px;height:64px" width="64" height="64"/>

# SignWarp

* Summary: Warp between places using signs
* Dependency Plugins: n/a
* PocketMine-MP version: 1.4 (API:1.10.0), 1.5 (API:1.12.0), 1.6+php7 (API:2.0.0)
* OptionalPlugins: FastTransfer
* Categories: Teleportation
* Plugin Access: Other Plugins, Commands, Tile Entities, Manages worlds
* WebSite: https://github.com/alejandroliu/pocketmine-plugins/tree/master/SignWarp

## Overview

<!-- php: $v_forum_thread = "http://forums.pocketmine.net/threads/signwarp.7276/"; -->
<!-- template: prologue.md -->

**DO NOT POST QUESTIONS/BUG-REPORTS/REQUESTS IN THE REVIEWS**

It is difficult to carry a conversation in the reviews.  If you
have a question/bug-report/request please use the
[Thread](http://forums.pocketmine.net/threads/signwarp.7276/) for
that.  You are more likely to get a response and help that way.

_NOTE:_

This documentation was last updated for version **1.6.0**.

Please go to
[github](https://github.com/alejandroliu/pocketmine-plugins/tree/master/SignWarp)
for the most up-to-date documentation.

You can also download this plugin from this [page](https://github.com/alejandroliu/pocketmine-plugins/releases/tag/SignWarp-1.6.0).

<!-- template-end -->

A Plugin implementing simple _Sign_ based warps.

Basic Usage:

Place a Sign with the following text:

	[SWARP]
	x y z

Where `x`, `y` and `z` are numbers containing the target warp
coordinates.

Or for a warp between worlds:

	[WORLD]
	world_name
	x y z

Where `world_name` is the world to warp to, and *optionally* the
`x`, `y` and `z` warp location.

For Warp between servers use:

	[TRANSFER]
	server-address
	port

You need the **FastTransfer** plugin for this to work.

## Documentation

This plugin implements _warps_ through the placement of _signs_.  You
need to create a sign with the text:

	[SWARP]
	x y z

`x`, `y` and `z` are integers containing the target coordinates for
this warp.

To activate a _warp_ the player must touch a sign.  That will teleport
the player to the new location described by the `x`, `y`, `z`
coordinates.

The third and four lines of the sign are ignored and can be used to
describe the _warp_.

To teleport between worlds, the sign text should look like:

	[WORLD]
	world_name
	x y z
	Players:

`world_name` is the target world to teleport to.  `x`, `y`, `z` is the
target location.  If not specified it defaults to the `spawn` world.

If dynamic updates are enabled, the fourth line can contain the text
`Players:`, which will get updated dynamically with the number of
players on that world.  Otherwise the ine is  ignored and can
contain any descriptive text.

To help identify potential _warp_ targets, the command `xyz` is
provided.  Entering `/xyz` in-game will display the current
coordinates of the player.

For Warp between servers use:

	[TRANSFER]
	server-address
	port

The `port` is optional, and would default to `19132` (the default for
Minecraft PE servers).  If you do not need to specify a port, then you
can add some descriptive text instead.  The last line is ignored and
can be used for description.

You need the **FastTransfer** plugin for this to work.

### Configuration

Configuration is through the `config.yml` file.
The following sections are defined:

#### config.yml

*  settings: configurable variables
 *  dynamic updates: Signs will be udpated with the number of players in a world
 *  xyz.cmd: If true, the **xyz** command will be available
*  text: Text displayed on the different signs
 *  transfer: Fast transfer signs
 *  world: World teleport signs
 *  warp: Local world teleport signs
 *  players: Text to use when displaying player counts


### Permission Nodes

* signwarp.place.sign : Allow user to create warp
  (Defaults to Op)
* signwarp.touch.sign : Allow user to use warp
* signwarp.place.transfer.sign : Allow user to create transfer signs
  (Defaults to Op)
* signwarp.touch.transfer.sign : Allow user to use transfer signs
* signwarp.cmd.xyz : Shows current x,y,z coordinates


# Changes

* 1.6.0: Updated to API 2.0.0
* 1.5.1: bug-fix
  * Removed a nasty crash in BreakSign
* 1.5.0:
  * Signs now show max players in world.
* 1.4.0:
  * Clean-up and use library stuff
  * Removed broadcast setting: Use
	  [GrabBag](http://forums.pocketmine.net/plugins/grabbag.1060/)
		**broadcast-tp** module
  * Translations: Spanish
* 1.3.2: CallbackTask
  * Removed CallbackTask deprecation warnings
* 1.3.1: FastTransfer
  * removed onLoad... All initialization happens onEnable
  * FastTransfer support
* 1.3.0: Re-write
  * /xyz can now be disabled
  * cleaned up the code
* 1.2.2: Bug fixes
  * Fixed errors reported by [Crash Archive](http://crash.pocketmine.net/)
* 1.2.1 : Minor updates
  * Added broadcast-tp setting.
  * Small changes on the way ManyWorlds API is used.
* 1.2.0 : Configurable texts
  * Sign texts can be configured.  Useful for localization.
* 1.1.1 : Bugfix release
  * Fixed /xyz command.
* 1.1.0 : Update release
  * Will not teleport if you are holding a sign.
  * Prevents blocks to be placed when teleporting.
  * Use ManyWorlds teleport functionality when available.
  * Added dynamic sign updates.
* 1.0.0 : First release

FAQ
---

* Q: How do I create additional worlds?
* You can use a plugin like `ManyWorlds` or modify the `worlds` secion
  in your `pocketmine.yml` file.

Copyright
=========

    SignWarp
    Copyright (C) 2015 Alejandro Liu  
    All Rights Reserved.

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 2 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

128 70 128
X:-100 Y:69 Z:1072


<!-- template: startup.md -->
<!-- end-include -->
<img id="ZipPlugin-icon.png" src="https://raw.githubusercontent.com/Muirfield/ZipPluginLoader/master/media/ZipPlugin-icon.png" style="width:64px;height:64px" width="64" height="64"/>
<!-- php: $v_forum_thread = "http://forums.pocketmine.net/threads/zippluginloader.8924"; -->
<!-- php: $copyright="2016"; -->
<!-- meta: Categories = Developer Tools -->
<!-- template: header.md -->
<!-- end-include -->

<!-- template: prologue.md -->
<!-- end-include -->

**NOTE: This is unlike _DevTools_, as it is focus on only loading Zip files
instead of folders like _DevTools_.**  You still need _DevTools_ if
you actually want to do Plugin Development and to create _phar_ file
plugins.

This plugin let's you load plugins from zip files.  This is
particularly handy when trying out source plugins from
[GitHub](http://github.com) as you can click the **Download ZIP**
button, as you can then place the zip file in the plugins folder.

Essentially you put your plugin code in a zip file, and this plugin
will look for a **plugin.yml** file in there and load the plugin.

If there are multiple plugins in a zip file, all the plugins will be
loaded by default.  You can control what plugins will be loaded by
creating a control file.  For example if you have a:

	example.zip

You need to create a text file called:

	example.ctl

In this file you list (one plugin per line) the plugins that you want
to load.  Any plugins **not** in listed the control file will **not** be
loaded.

## Changes

* 1.2.1: Updated to newest API
* 1.1.3: Bug-fix
  - Fixed bug reported by (@Taha_The_Hacker)
* 1.1.2: Minor update
  * Displays a warning whenever a PHAR file is found.
* 1.1.1: Bug-fix
  - Fixed some reload related bugs.
* 1.1.0: Multiple plugins
  * Change the way error reporting is done...
  * Supports for multiple plugins in a zip file.
* 1.0.0: First release

<!-- template: license/gpl2.md -->
<!-- end-include -->
