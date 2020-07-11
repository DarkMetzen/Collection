The Dark Metzen Collection is an official gathering of my map projects for the Hydra NGS.

I took the time to "polish" some of these old melee maps so they would be in line with Hydra's economic demands and have prepared various force iterations of each.

After playing a lot of Hydra melee with the community, I felt the desire to increase our
repertoire of interesting battlefields to conquest.

Each map is set up for UMS and melee play, and should work.

Dark Metzen's Loot Box: An archive containing new melee maps.
Dark Metzen's Paid DLC: An archive containing my recent scenarios.
Dark Metzen's Battle Chest: An archive containing both aforementioned archives.

So you also want to convert old melee maps? Here's the process:

*First, do you have the latest copy of SCMDraft? Go to www.stormcoast-fortress.net and download the latest official release under SCMDraft

*Second, do you have the hydrabeta's editor file set up?

Make a new profile in SCMDraft. Under Game Data, add stardat.mpq, broodat.mpq, and patch_rt.mpq to the Custom Game Data area. Then, add hydra1161.mpq to the game data. Save and it should work.

1. Find a melee map you wish to convert to the Hydra NGS
2. Polish resource placement across the map:
   - Resource gathering must be efficient in mains and expansions
   - Mains should have at least 8 mineral fields and 1 gas
   - Mains with distant nats should have 9 mineral fields and 2 gas
   - Naturals should have at least 7 minerals and 1 gas
   - Thirds and beyond should have at least 6 minerals and 1 gas
3. Build on the concept
   - Move start locations, resource placements away from map edges
   - Tighten chokes and widen ramps where necessary
   - Add expansions when there are too few
4. Set the Map Description
   - Make sure all player races are set to User Select
   - Update player colors to use the Hydra Palette (http://pr0nogo.wikidot.com/rs-player-colors)
     - Lazy Check: 
       P1 31 (Vermillion)
       P2 26 (Ultramarine)
       P3 102 (Midnight Green)
       P4 97 (Japanese Violet)
       P5 32 (Magma)
       P6 98 (Dark Spring Green)
       P7 18 (Alice Blue)
       P8 76 (Sunglow)
   - Separate players into forces as necessary
   - Remove any unused players from active forces
   - Name the map (I use the format [Original Title + Force Iteration], e.g. 1v1, 2v2)
5. Checklist
   - Did you remember to:
     - Name the map
     - Name the forces
     - Distribute the players
     - Tick or untick randomize start location
     - Set player race to user select
     - Add or delete start locations
     - Move resources away from the map's edge
     - Polish resource placement, add gas in minonly thirds
6. Triggers
   - Open your map.
   - Open trigedit (Trigger Editor, 3rd option under Triggers in SCMDraft)
   - Press Ctrl + A
   - Paste one of the following based on your force iteration:
   
   
~~~ 1v1 ~~~ ~~~ 1v1 ~~~ ~~~ 1v1 ~~~ ~~~ 1v1 ~~~ ~~~ 1v1 ~~~ ~~~ 1v1 ~~~
~~~ FFA ~~~ ~~~ FFA ~~~ ~~~ FFA ~~~ ~~~ FFA ~~~ ~~~ FFA ~~~ ~~~ FFA ~~~
~~~ 1v1 ~~~ ~~~ 1v1 ~~~ ~~~ 1v1 ~~~ ~~~ 1v1 ~~~ ~~~ 1v1 ~~~ ~~~ 1v1 ~~~


Trigger("All players"){
Conditions:
	Always();

Actions:
	Set Resources("Current Player", Set To, 100, ore);
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Current Player", "Factories", At most, 0);

Actions:
	Defeat();
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Non Allied Victory Players", "Factories", At most, 0);

Actions:
	Victory();
}

//-----------------------------------------------------------------//





~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~
~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~
~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~ ~~~ 2v2 ~~~





Trigger("All players"){
Conditions:
	Always();

Actions:
	Set Resources("Current Player", Set To, 100, ore);
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Current Player", "Factories", At most, 0);

Actions:
	Defeat();
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Non Allied Victory Players", "Factories", At most, 0);

Actions:
	Victory();
}

//-----------------------------------------------------------------//

Trigger("Player 1", "Player 2"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi0");
	Run AI Script("+Vi1");
	Set Alliance Status("Player 1", Allied Victory);
	Set Alliance Status("Player 2", Allied Victory);
	Set Alliance Status("Player 3", Enemy);
	Set Alliance Status("Player 4", Enemy);
}

//-----------------------------------------------------------------//

Trigger("Player 3", "Player 4"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi2");
	Run AI Script("+Vi3");
	Set Alliance Status("Player 1", Enemy);
	Set Alliance Status("Player 2", Enemy);
	Set Alliance Status("Player 3", Allied Victory);
	Set Alliance Status("Player 4", Allied Victory);
}

//-----------------------------------------------------------------//





~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~
~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~
~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~ ~~~ 2v2v2 ~~~





Trigger("All players"){
Conditions:
	Always();

Actions:
	Set Resources("Current Player", Set To, 100, ore);
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Current Player", "Factories", At most, 0);

Actions:
	Defeat();
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Non Allied Victory Players", "Factories", At most, 0);

Actions:
	Victory();
}

//-----------------------------------------------------------------//

Trigger("Player 1", "Player 2"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi0");
	Run AI Script("+Vi1");
	Set Alliance Status("Player 1", Allied Victory);
	Set Alliance Status("Player 2", Allied Victory);
	Set Alliance Status("Player 3", Enemy);
	Set Alliance Status("Player 4", Enemy);
	Set Alliance Status("Player 5", Enemy);
	Set Alliance Status("Player 6", Enemy);
}

//-----------------------------------------------------------------//

Trigger("Player 3", "Player 4"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi2");
	Run AI Script("+Vi3");
	Set Alliance Status("Player 3", Allied Victory);
	Set Alliance Status("Player 4", Allied Victory);
	Set Alliance Status("Player 1", Enemy);
	Set Alliance Status("Player 2", Enemy);
	Set Alliance Status("Player 5", Enemy);
	Set Alliance Status("Player 6", Enemy);
}

//-----------------------------------------------------------------//

Trigger("Player 5", "Player 6"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi4");
	Run AI Script("+Vi5");
	Set Alliance Status("Player 5", Allied Victory);
	Set Alliance Status("Player 6", Allied Victory);
	Set Alliance Status("Player 1", Enemy);
	Set Alliance Status("Player 2", Enemy);
	Set Alliance Status("Player 3", Enemy);
	Set Alliance Status("Player 4", Enemy);
}

//-----------------------------------------------------------------//





~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~
~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~
~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~ ~~~ 2v2v2v2 ~~~





Trigger("All players"){
Conditions:
	Always();

Actions:
	Set Resources("Current Player", Set To, 100, ore);
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Current Player", "Factories", At most, 0);

Actions:
	Defeat();
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Non Allied Victory Players", "Factories", At most, 0);

Actions:
	Victory();
}

//-----------------------------------------------------------------//

Trigger("Player 1", "Player 2"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi0");
	Run AI Script("+Vi1");
	Set Alliance Status("Player 1", Allied Victory);
	Set Alliance Status("Player 2", Allied Victory);
	Set Alliance Status("Player 3", Enemy);
	Set Alliance Status("Player 4", Enemy);
	Set Alliance Status("Player 5", Enemy);
	Set Alliance Status("Player 6", Enemy);
	Set Alliance Status("Player 7", Enemy);
	Set Alliance Status("Player 8", Enemy);
}

//-----------------------------------------------------------------//

Trigger("Player 3", "Player 4"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi2");
	Run AI Script("+Vi3");
	Set Alliance Status("Player 3", Allied Victory);
	Set Alliance Status("Player 4", Allied Victory);
	Set Alliance Status("Player 1", Enemy);
	Set Alliance Status("Player 2", Enemy);
	Set Alliance Status("Player 5", Enemy);
	Set Alliance Status("Player 6", Enemy);
	Set Alliance Status("Player 7", Enemy);
	Set Alliance Status("Player 8", Enemy);
}

//-----------------------------------------------------------------//

Trigger("Player 5", "Player 6"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi4");
	Run AI Script("+Vi5");
	Set Alliance Status("Player 5", Allied Victory);
	Set Alliance Status("Player 6", Allied Victory);
	Set Alliance Status("Player 1", Enemy);
	Set Alliance Status("Player 2", Enemy);
	Set Alliance Status("Player 3", Enemy);
	Set Alliance Status("Player 4", Enemy);
	Set Alliance Status("Player 7", Enemy);
	Set Alliance Status("Player 8", Enemy);
}

//-----------------------------------------------------------------//

Trigger("Player 7", "Player 8"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi6");
	Run AI Script("+Vi7");
	Set Alliance Status("Player 7", Allied Victory);
	Set Alliance Status("Player 8", Allied Victory);
	Set Alliance Status("Player 1", Enemy);
	Set Alliance Status("Player 2", Enemy);
	Set Alliance Status("Player 3", Enemy);
	Set Alliance Status("Player 4", Enemy);
	Set Alliance Status("Player 5", Enemy);
	Set Alliance Status("Player 6", Enemy);
}

//-----------------------------------------------------------------//





~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~
~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~
~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~ ~~~ 3v3 ~~~





Trigger("All players"){
Conditions:
	Always();

Actions:
	Set Resources("Current Player", Set To, 100, ore);
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Current Player", "Factories", At most, 0);

Actions:
	Defeat();
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Non Allied Victory Players", "Factories", At most, 0);

Actions:
	Victory();
}

//-----------------------------------------------------------------//

Trigger("Player 1", "Player 2", "Player 3"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi0");
	Run AI Script("+Vi1");
	Run AI Script("+Vi2");
	Set Alliance Status("Player 1", Allied Victory);
	Set Alliance Status("Player 2", Allied Victory);
	Set Alliance Status("Player 3", Allied Victory);
	Set Alliance Status("Player 4", Enemy);
	Set Alliance Status("Player 5", Enemy);
	Set Alliance Status("Player 6", Enemy);
}

//-----------------------------------------------------------------//

Trigger("Player 4", "Player 5", "Player 6"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi3");
	Run AI Script("+Vi4");
	Run AI Script("+Vi5");
	Set Alliance Status("Player 4", Allied Victory);
	Set Alliance Status("Player 5", Allied Victory);
	Set Alliance Status("Player 6", Allied Victory);
	Set Alliance Status("Player 1", Enemy);
	Set Alliance Status("Player 2", Enemy);
	Set Alliance Status("Player 3", Enemy);
}

//-----------------------------------------------------------------//





~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~
~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~
~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~ ~~~ 4v4 ~~~





Trigger("All players"){
Conditions:
	Always();

Actions:
	Set Resources("Current Player", Set To, 100, ore);
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Current Player", "Factories", At most, 0);

Actions:
	Defeat();
}

//-----------------------------------------------------------------//

Trigger("All players"){
Conditions:
	Command("Non Allied Victory Players", "Factories", At most, 0);

Actions:
	Victory();
}

//-----------------------------------------------------------------//

Trigger("Player 1", "Player 2", "Player 3", "Player 4"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi0");
	Run AI Script("+Vi1");
	Run AI Script("+Vi2");
	Run AI Script("+Vi3");
	Set Alliance Status("Player 1", Allied Victory);
	Set Alliance Status("Player 2", Allied Victory);
	Set Alliance Status("Player 3", Allied Victory);
	Set Alliance Status("Player 4", Allied Victory);
	Set Alliance Status("Player 5", Enemy);
	Set Alliance Status("Player 6", Enemy);
	Set Alliance Status("Player 7", Enemy);
	Set Alliance Status("Player 8", Enemy);
}

//-----------------------------------------------------------------//

Trigger("Player 5", "Player 6", "Player 7", "Player 8"){
Conditions:
	Always();

Actions:
	Run AI Script("+Vi4");
	Run AI Script("+Vi5");
	Run AI Script("+Vi6");
	Run AI Script("+Vi7");
	Set Alliance Status("Player 5", Allied Victory);
	Set Alliance Status("Player 6", Allied Victory);
	Set Alliance Status("Player 7", Allied Victory);
	Set Alliance Status("Player 8", Allied Victory);
	Set Alliance Status("Player 1", Enemy);
	Set Alliance Status("Player 2", Enemy);
	Set Alliance Status("Player 3", Enemy);
	Set Alliance Status("Player 4", Enemy);
}

//-----------------------------------------------------------------//

6. Triggers (Cont.)
    - After pasting the correct script, click the black check mark icon.
    - Save the map. You're done!
