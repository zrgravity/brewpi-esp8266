.. include:: ../global.rst

Connecting Temperature Sensors
==================================

The first decision you should make when planning a build is how you will connect your DS18b20 temperature sensors to the
rest of your hardware. This decision will influence both how you connect the rest of your build together as well as how
your build is enclosed.


Breakout Board
--------------

The easiest way of connecting temperature sensors to a build is through the use of a breakout board. The wires from your
DS18b20 temperature sensors are soldered directly onto the breakout board and the breakout board is connected to the
rest of your build via either an RJ-11 or RJ-45 cable.

Advantages:
* Easy to assemble/solder
* Breakout board can be placed away from the rest of your build, closer to your fermenters

Disadvantages:
* Difficult to replace temperature sensors if necessary
* Requires separate enclosure for breakout board


Breakout Board Choices
**********************

There are two breakout board PCBs currently available: RJ-45 and RJ-11. The boards are functionally identical, except
for the jack. The RJ-45 board connects to the matching base PCB via a regular, straight 8-wire ethernet cable. The RJ-11
board connects to the matching base PCB via a regular, crossover 4-wire telephone cable. The temperature sensor breakout
boards also support attaching an optional door sensor if desired.

Note - If you use a breakout board it is highly recommended that you use a base PCB with a matching jack.

RJ-45 Breakout Board
++++++++++++++++++++

PCB Order Link:
Eagle Files:

Bill of Materials:
* PCB
* 1-3x DS18b20 Temperature Sensors



RJ-11 Breakout Board
++++++++++++++++++++

PCB Order Link:
Eagle Files:


Assembly
********

Assembly for both the RJ-11 and RJ-45 breakout boards is identical. Simply solder the power, ground, and data cables
from the DS18b20 temperature sensors to the corresponding holes on the breakout board, and attach the snap-in.

If you want to attach a door
sensor, you can either solder on an optional


Directly Wired
--------------

The most straightforward method of connecting temperature sensors to your build is by directly wiring the temperature
sensors to the ESP8266. This method eliminates the need for a base PCB at the expense of increased wiring/build
complexity.

All three wires of the DS18b20

When you first access a new installation of Fermentrack you will be asked to set up a user account. This account will
enable you to configure devices, configure the Fermentrack application, and view brew logs.

Setting up the user account is extremely straightforward:

1. From the root Fermentrack page, click "Continue to guided installation"
2. On the next page, entering the following:
    - **Username** - The username used to log into Fermentrack
    - **Password** - The password for the user account
    - **Email Address** - Currently unused, but may potentially be used later
3. Click "Create new user account"
4. Done!

You're now ready to move on to configuring the site settings.

Site Settings
----------------

After configuring a user account, the next step is to configure Fermentrack. The following are the available
configuration options:

* **Brewery Name** - The name displayed in the upper left of each Fermentrack page
* **Date time format display** - The date format used on the dashboard of each device
* **Require login for dashboard** - *Currently Unused* - Should users be required to be logged in to *view* the dashboard/logs. Login will still be required to change temperature settings, configuration options, etc.
* **Temperature format** - The preferred (default) temperature format. Used when setting fermentation temperature profiles. Can be overridden per device.
* **Preferred timezone** - The preferred timezone you would like graphs displayed in. *Note* - All data is stored in UTC (GMT) - you are only selecting how the data will be *displayed*. Feel free to change this at any time with no issues.
* **Git Update Type** - Which releases you will be prompted to upgrade to. Can be set to "tagged versions" (which will generally be tested and stable), "all commits" which will include all new code releases, and "None".

All of these can be updated at any time by clicking on the "gear" icon in the upper right of any Fermentrack page.


Notes for Advanced Users
--------------------------------

User Accounts
~~~~~~~~~~~~~~~~~~~~~

Currently, Fermentrack has limited access control implemented, and is not yet designed for multiple user installations.
This feature is planned for a later release - once it becomes available, different levels of access will be able to be
specified on a per-user basis.

In the mean time if you need multiple user accounts they can be configured using the Django admin interface (accessible
via the "gear" icon). Each account will need "superuser" access to be able to use the full functionality of Fermentrack.
Again - please keep in mind - multiple user access is not officially supported. When access control functionality is
implemented, any users created previously through this method will retain full access/control of Fermentrack.


Advanced Site Settings
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

There are a handful of additional site settings which are intended for advanced users and developers only. These
settings can only be accessed via the Django admin. These settings include:

* **Allow Git Branch Switching** - Allows switching to a different git branch from within Fermentrack
* **User Has Completed Configuration** - Determines if the user has completed the initial configuration workflow, or should be prompted to set Fermentrack up on next login.

Additionally, graph colors can be configured via the Django admin. The graph color options include:

* **Graph Beer Set Color** - The color of the "Beer Setting" line
* **Graph Beer Temp Color** - The color of the "Beer Temperature" line
* **Graph Fridge Set Color** - The color of the "Fridge Setting" line
* **Graph Fridge Temp Color** - The color of the "Fridge Temp" line
* **Graph Room Temp Color** - The color of the "Room Temp" line
* **Graph Gravity Color** - The color of the "Specific Gravity" line


