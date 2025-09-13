This document describes the files and folders within the Config folder.
To search for a specific file, use the shortcut Ctrl + F.

0. LcId and Weight
LcId consists of 'Mod ID + Abnormality ID', separated by ','.
Each LcId is separated by a line break(Enter).
After installing the mod, when you run the game, a file named allCreatureList.txt will be generated in the Config folder.
This file contains the LcId of almost all abnormalities, including mod abnormalities. You can simply find and copy the LcId of the abnormalities from this file.

Within the weight node, there should be 'LcId + Weight'.
The 'Weight' should be a float value between 0 and 1, where decreasing it lowers the appearance probability, and increasing it raises the appearance probability.
When an Abnormality is randomly selected, if it is included in the weight node, its weight is converted to a percentage chance for a lottery draw.
If chosen, the Abnormality appears; otherwise, another random Abnormality from the same risk level list is drawn once.
Hence, even if an Abnormality's weight is 0, there is still a slight chance it will appear.

1. applymod.xml
Apply or disable the mod.

	1) addIsolate
	This mod is the Additional Containment Unit mod.
	Implemented Legacy version's additonal containment units.
	Tool abnormalities aren't extracted additonally.
	Data type: Boolean, Default: true

	2) tt05
	This mod is the TT0.5 mod. You can change the value of game speed.
	Data type: Boolean, Default: true

	3) energyRefine
	This mod is the Energy Refine Work mod. Implemented Legacy version's Energy refine work.
	Data type: Boolean, Default: true

	4) isolateRandomize
	This mod is the Containment Unit Rearrangement mod.
	From the 7th day, the positions of the abnormalities are randomly rearranged at the end of the day.
	Data type: Boolean, Default: false

	5) overloadPlus
	This mod is the Qliphoth Overload Plus mod.
	All abnormalities except tool abnormalities are caught in qliphoth overload, which is higher than before.
	Data type: Boolean, Default: true

	6) aberration
	This mod is the Aberration mod.
	Data type: Boolean, Default: true

	7) centralStair
	This mod is the Central Command Team Stairs mod. You can quickly cross the Central Command Team through transparent stairs.
	Data type: Boolean, Default: false

	8) languageCompatibility
	This mod is the Language Compatibility mod, which allows you to run Energy Corp mods in language settings that have not yet been translated.
	Data type: Boolean, Default: true


2. modconfig.xml
You can change the details of the mod.

	1) addIsolate
	This is the Additional Containment Unit mod. It increases the number of abnormalities you need to manage.

		randomExtraction
		This is the Random Additional Abnormality mod. Additional abnormalities are extracted randomly without your choice.
		Data type: Boolean, Default: false

	2) tt05
	This is TT0.5 mod. You can change the value of game speed.
	The order is pause, normal speed, x1.5 speed, x2 speed from the top.

		(1) pause
		Data type: Float, Range: 0 or more, Default: 0.5
		
		(2) speedLv1
		Data type: Float, Range: 0 or more, Default: 1
		
		(3) speedLv2
		Data type: Float, Range: 0 or more, Default: 1.5
		
		(4) speedLv3
		Data type: Float, Range: 0 or more, Default: 2

	3) energyRefine
	This is Energy Refine Work mod.

		(1) maxLobPenalty
		Maximum value of LOB Point Penalty.
		Data type: Integer, Range: 0 or more, Default: 8

		(2) refineEfficiency
		Energy refine work speed. The higher the number, the faster the energy refine work will be completed.
		Data type: Float, Range: above 0, Default: 15

		(3) ignoreBossFight
		If all the energy is gathered during Core suppression, ignore the Core suppression and proceed with the Energy refine work,
		in this case the Core suppression fails.
		Data type: Boolean, Default: false

	4) overloadPlus
	This is Qliphoth Overload Plus mod. Each time you complete a work,
	the Success Rate is reduced by the number you set for each Risk level.

		(1) zayin
		Data type: Integer, Range: 0 or more, Default: 4
	  
		(2) teth
		Data type: Integer, Range: 0 or more, Default: 5
	  
		(3) he
		Data type: Integer, Range: 0 or more, Default: 6
	  
		(4) waw
		Data type: Integer, Range: 0 or more, Default: 7
	  
		(5) aleph
		Data type: Integer, Range: 0 or more, Default: 8

	5) aberration
	This is Aberration mod.

		(1) selectable
		Whether Aberration appears in the Abnormality Selection Phase.
		Data type: Boolean, Default: true

		(2) transformBlacklist
		O-05-47-1 will not transform into the Abnormality in the list.
		Data type: LcId, Default:
		100019
		100022
		100024
		Qquickness_EnergyCo, 178801
		Qquickness_EnergyCo, 178805


3. banList.xml
* Dedicated to the Additional Containment Unit mod, disabled when the Random Additional Abnormality mod is used.
Prevents abnormalities from appearing in the Abnormality selection phase or prevents duplicates of the abnormalities you've chosen from appearing.

	1) selectableOnce
	Prevents duplicates of the abnormalities you've chosen from appearing.
	Data type: LcId, Default:
	100007	T-06-27	Malfunction when there are two or more
	100008	O-02-40	Event presence
	100009	O-03-03	Event presence
	100014	O-01-45	Event presence
	100015	T-03-46	Malfunction when there are two or more
	100020	O-02-56	Event presence
	100032	F-01-57	Interaction exists
	100033	F-02-58	Interaction exists
	100104	O-05-102	Interaction exists
	300001	T-09-77	Tool Abnormality
	300002	T-09-78	Tool Abnormality
	300003	T-09-09	Tool Abnormality
	300004	T-09-79	Tool Abnormality
	300005	T-09-80	Tool Abnormality
	300006	T-09-82	Tool Abnormality
	300007	O-09-81	Tool Abnormality
	300101	T-09-85	Tool Abnormality
	300102	T-09-86	Tool Abnormality
	300103	T-09-90	Tool Abnormality
	300104	O-09-91	Tool Abnormality
	300105	T-09-94	Tool Abnormality
	300106	O-09-95	Tool Abnormality
	300107	O-09-96	Tool Abnormality
	300108	T-09-97	Tool Abnormality
	300110	D-09-104	Tool Abnormality
	
	2) preventExtraction
	Prevents abnormalities from appearing in the Abnormality selection phase.
	Data type: LcId, Default:
	300109	O-07-103	Condition for appearance exists

4. randomExtraction
Settings exclusive to the Random Additional Abnormality mod.

	1) blacklist.xml
	It can prevent Abnormalities of certain mods from appearing randomly.

		(1) useBlacklist
		Whether to use the Mod blacklist function.
		Data type: Boolean, Default: false

		(2) blacklist
		You can write down the Mod ID of the mod you want to block here.
		If you want to block multiple mods, please separate the Mod ID into Enter.
		Data type: String

	2) dailyDifficulty.xml
	Adjust the difficulty of the Random Additional Abnormality mod.
	Zayin, Teth, He, Waw, and Aleph in order. The larger the number, the more likely it is to be extracted.

	3) reserveCreature.xml
	You can meet the desired Abnormality with the desired probability on the desired date.
	Create a 'D + Desired Date' node.
	Days without random abnormality do not appear.


	4) risklevel.xml
	You can increase or eliminate the probability of random extraction by adding or removing Abnormality IDs.
	Abnormality in nodes with low risk levels is more likely to appear at the beginning of the game, but it is less likely to appear as the game progresses.
	Abnormality in nodes with high risk levels does not appear at the beginning of the game, but it is more likely to appear as the game progresses.

		(1) Creating a risklevel.xml File
		Within the riskLevel folder, create an .xml file that includes 'risklevel' in its name for the mod to recognize it.
		Please refer to an existing risklevel.xml for the structure of the file. It should contain one preventRandomExtraction node and one weight node.

		(2) List of Abnormalities Unattainable by Random Extraction

		100000	0-00-00	Cannot be encountered during the Abnormality Selection Phase
		100007	T-06-27	Malfunction when there are two or more
		100008	O-02-40	Event presence
		100009	O-03-03	Event presence
		100014	O-01-45	Event presence
		100015	T-03-46	Malfunction when there are two or more
		100020	O-02-56	Event presence
		100032	F-01-57	Interaction exists
		100033	F-02-58	Interaction exists
		100034	B-is-as	Disrupts gameplay
		100038	O-02-63	Cannot be encountered during the Abnormality Selection Phase
		100104	O-05-102	Interaction exists

		(3) Weighted Abnormality List
	
		100001	F-01-02	Weight 0.2
		100018	T-01-54	Weight 0.2
		100022	F-01-18	Weight 0.2
		100036	O-03-60	Weight 0.2
		100011	T-05-41	Weight 0.2
		100016	F-02-49	Weight 0.2
		100017	O-01-15	Weight 0.2
		Qquickness_EnergyCo, 178802	F-01-02	Weight 0.7
		Qquickness_EnergyCo, 178803	T-01-54	Weight 0.7
		Qquickness_EnergyCo, 178805	F-01-18	Weight 0.7
		Qquickness_EnergyCo, 178804	O-03-60	Weight 0.7
		Qquickness_EnergyCo, 178806	T-05-41	Weight 0.7
		Qquickness_EnergyCo, 178807	F-02-49	Weight 0.7
		Qquickness_EnergyCo, 178808	O-01-15	Weight 0.7