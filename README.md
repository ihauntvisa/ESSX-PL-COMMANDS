# ESSX-PL-COMMANDS
The Minecraft Full List

Overview

The functionality moved to AntiBuild is the following:

    Block place blacklist
    Block break blacklist
    Item use blacklist
    Piston block move blacklist
    Permission system based place protection
    Permission system based break protection
    Permission system based use protection

Old system support

EssentialsAntiBuild still supports the old EssProtect blacklist system syntax, where you list types of blocks to be blocked server wide.

This system allows you to list items by id or name with the following config settings:

 blacklist:

   # Which blocks should people be prevented from placing
   placement: 10,11,46,327

   # Which items should people be prevented from using
   usage: 327

   # Which blocks should people be prevented from breaking
   break:

   # Which blocks should not be pushed by pistons
   piston:

You can exempt players from these limits by using the following permissions:

 essentials.protect.exemptplacement
 essentials.protect.exemptusage
 essentials.protect.exemptbreak

Build Alert System

Essentials still supports the old alert system, where you list item id's which will trigger staff alerts when placed/broken/interacted with.

This system allows you to list items by id or name with the following config settings:

 alert:
   on-placement: 10,11,46,327
   on-use: 327
   on-break:

People with the following permission will get notified whenever a user triggers these alerts:

 essentials.protect.alerts

You can also exempt players from triggering these alerts by giving the player:

 essentials.protect.alerts.notrigger

AntiBuild
Legacy Support

In many permissions systems, you will find support for build toggles, or have build permissions intended to be given to allow people to build. If a user has building enabled in one of these systems or has the following opt out permission, they will be exempt from the following permissions checks.
Global opt out

If you have a player who you don't want to perform build checks on. I.e. You want them to be able to build with any non blacklisted block. Give the player the following permission. This is recommended where possible as it reduces the number of checks the server needs to make every time a player places/breaks a block.

 essentials.build

Permission control

Assuming a player doesn't have 'essentials.build' permission or 'build: true' in their permissions file, they will be checked for item based permissions whenever they try to place, interact with or break a block.

The permissions follow the following syntax:

 essentials.build.place.<id>
 essentials.build.place.<id>:
 essentials.build.break.<id>
 essentials.build.break.<id>:
 essentials.build.interact.<id>
 essentials.build.interact.<id>:
 essentials.build.craft.<id>
 essentials.build.craft.<id>:
 essentials.build.pickup.<id>
 essentials.build.pickup.<id>:
 essentials.build.drop.<id>
 essentials.build.drop.<id>:


These permissions can be given directly or be given using wildcards, so for example its possible to do the following:

 permissions:
 - essentials.build.*
 - -essentials.build.place.29

Which would allow a user to place/break every type of block except for placing pistons.
Caveats
PEX

PEX not following superperms rules properly will behave slightly different in that the '<id>' perms will not work. You can still use the '<id>:' perms however. If you need to whitelist/negate all datavalues for a single block, instead use: '<id>:*'. For example:

 permissions:
 - -essentials.build.place.54:*
 - essentials.build.*

Alternatively you can use the modifyworld plugin that ships with PermissionsEx.
Interacting

When a user tries to place a block, they will also be 'interacting' with the block they try to place it on. So if a player tries to place a block of dirt on sand, they will need both the interact permission for sand, and the place permission for dirt. The 'interact' check is based on the item for which the user clicks on, not always the block below. Generally if you want a user to be able to build, it would be best to give them 'essentials.build.interact.*' or 'essentials.build.*' or the global opt out permission above.



    What links here
    Related changes
    Special pages
    Printable version
    Permanent link
    Page information

This website uses cookies to display custom content and advertising.
We therefore share information about your use of our site with Google.
See details
AntiBuild

EssentialsAntiBuild is a fairly new plugin, it is the result of pulling out the antibuild feature from EssentialsProtect and adding better support for blocking certain actions.
Contents

    1 Overview
    2 Old system support
    3 Build Alert System
    4 AntiBuild
        4.1 Legacy Support
        4.2 Global opt out
        4.3 Permission control
        4.4 Caveats
            4.4.1 PEX
            4.4.2 Interacting

Overview

The functionality moved to AntiBuild is the following:

    Block place blacklist
    Block break blacklist
    Item use blacklist
    Piston block move blacklist
    Permission system based place protection
    Permission system based break protection
    Permission system based use protection

Old system support

EssentialsAntiBuild still supports the old EssProtect blacklist system syntax, where you list types of blocks to be blocked server wide.

This system allows you to list items by id or name with the following config settings:

 blacklist:

   # Which blocks should people be prevented from placing
   placement: 10,11,46,327

   # Which items should people be prevented from using
   usage: 327

   # Which blocks should people be prevented from breaking
   break:

   # Which blocks should not be pushed by pistons
   piston:

You can exempt players from these limits by using the following permissions:

 essentials.protect.exemptplacement
 essentials.protect.exemptusage
 essentials.protect.exemptbreak

Build Alert System

Essentials still supports the old alert system, where you list item id's which will trigger staff alerts when placed/broken/interacted with.

This system allows you to list items by id or name with the following config settings:

 alert:
   on-placement: 10,11,46,327
   on-use: 327
   on-break:

People with the following permission will get notified whenever a user triggers these alerts:

 essentials.protect.alerts

You can also exempt players from triggering these alerts by giving the player:

 essentials.protect.alerts.notrigger

AntiBuild
Legacy Support

In many permissions systems, you will find support for build toggles, or have build permissions intended to be given to allow people to build. If a user has building enabled in one of these systems or has the following opt out permission, they will be exempt from the following permissions checks.
Global opt out

If you have a player who you don't want to perform build checks on. I.e. You want them to be able to build with any non blacklisted block. Give the player the following permission. This is recommended where possible as it reduces the number of checks the server needs to make every time a player places/breaks a block.

 essentials.build

Permission control

Assuming a player doesn't have 'essentials.build' permission or 'build: true' in their permissions file, they will be checked for item based permissions whenever they try to place, interact with or break a block.

The permissions follow the following syntax:

 essentials.build.place.<id>
 essentials.build.place.<id>:
 essentials.build.break.<id>
 essentials.build.break.<id>:
 essentials.build.interact.<id>
 essentials.build.interact.<id>:
 essentials.build.craft.<id>
 essentials.build.craft.<id>:
 essentials.build.pickup.<id>
 essentials.build.pickup.<id>:
 essentials.build.drop.<id>
 essentials.build.drop.<id>:


These permissions can be given directly or be given using wildcards, so for example its possible to do the following:

 permissions:
 - essentials.build.*
 - -essentials.build.place.29

Which would allow a user to place/break every type of block except for placing pistons.
Caveats
PEX

PEX not following superperms rules properly will behave slightly different in that the '<id>' perms will not work. You can still use the '<id>:' perms however. If you need to whitelist/negate all datavalues for a single block, instead use: '<id>:*'. For example:

 permissions:
 - -essentials.build.place.54:*
 - essentials.build.*

Alternatively you can use the modifyworld plugin that ships with PermissionsEx.
Interacting

When a user tries to place a block, they will also be 'interacting' with the block they try to place it on. So if a player tries to place a block of dirt on sand, they will need both the interact permission for sand, and the place permission for dirt. The 'interact' check is based on the item for which the user clicks on, not always the block below. Generally if you want a user to be able to build, it would be best to give them 'essentials.build.interact.*' or 'essentials.build.*' or the global opt out permission above. 

@visa
