Place respawn Markers in the editor, name them respawn_east, respawn_west and/or respawn_guerrila depending on which sides you want to have respawning.
The players will respawn here but will not be able to control their units until there are enough of them. Make sure these markers are at least 100 m apart.
Place them somewhere safe, we don't want them to be interfered with, consider framing them with hescos or similar.

Place objects in the editor, name them zsn_respawn_east, zsn_respawn_west and/or zsn_respawn_guerrila.
This is the place the players will be moved to when they are given control back. Make sure they are objects,
I no longer support markers since they cannot be moved during gameplay on dedicated servers. (I recommend the invisible Helipad, but any object is supported, including vehicles)

[west, 4, -1, true, false, west] remoteExec ["zsn_waverespawn", 2];

Is the line used to call the script, it contains six params;

- Side: the side to use wave respawn, default is West.

- Wave Size: The number of players to include in each wave, default is 9

- Wave count: The max number of waves to respawn, default is -1 (infinite)

- Custom Loadout: New wave gets custom loadouts defined in description.ext, they can also respawn with a vehicle. 
If false thay will respawn with the gear they had at mission start. Default is false

- PvP: whether or not this is a PvP mission, this determines what kind of end trigger will be used when one side runs out of "lives". Default is false

- Respawn side: which side the new wave will belong to, if you want to respawn players to a different side, default is whatever you set in the first param

This line can be executed anywhere in the mission at any point, it can be used to change the respawn conditions during gameplay

There is also support for setting params size and count in the mission lobby, (only for east and west in the example but you get the idea) the params are set in description.ext

To initialize the script for multiple sides, just execute the command line multiple times, this example mission executes it three times for three sides.
