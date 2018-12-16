=================================
Augmented2 Ruleset for Freeciv v2.6
=================================


OBJECTIVES:
-----------

- Better balanced and more sophisticated technology tree.

- Clearly distinctive tiers of military unit classes: 
  defensive infantry, assault infantry, fast assault units, reconnaissance, 
  direct fire artillery, plunging fire artillery, peacekeepers, turrets etc.

- Distinctive tiers of ships classes: river/coastal merchants, river/coastal warships, ocean merchants, ocean warships. 

- Ships and armoured train have decreased attack alone, but can be equipped with turret guns (destroyer and patrol boat also torpedos). 
- Submarines can carry torpedos (nuclear submarine also missiles). 
- Bombers, strike aircrafts/advanced fighters can carry bombs (and torpedos). 

- Enginners can carry other unit.

- New buildings and wonders, adopted to the new technology tree. 
  Some industrial improvements give additional bonus from certain tiles.
  City radius depend on city size and improvements.

- New governments and altered governments properties.

- Upkeep cost depend on unit type and tier.

- Smooth changes in upkeep system between different government systems.

- No additional income from caravan arrival and decreased income from traderoutes.

INFO:
-----

- Ruleset base is civ2/civ3, but with profound changes.

- Help texts have been updated (mainly Buildings and Wonders), so the
  info showed ingame already takes into account the changed rules. Note
  that some graphical tables from the Manual will not match (mainly
  Terrains and Governments), so better use the tables in this ReadMe as
  reference.

The following is a full list of changes compared to civ2/civ3 ruleset...


CORE CHANGES:
-------------

- Every unit pays some kind of Upkeep cost, for example 1 food, 1 gold in case of medieval infantry, 
  or 1 shield, 1 food, 1 gold in case of gunpowder era infantry. 
  There is no abrupt change of upkeep system after revolution, each goverment pays all 3 upkeep prices, 
  however free upkeep threshold for shield and gold depend on government. Food upkeep is scalable with city size as usual.

- Units lose one Veteran level when auto-upgraded by Leonardo Workshop or DARPA wonders.

- Unlimited movement on rails delayed to maglev (available with
  Superconductors). Movement bonus on Railroads apply only for Land and Small Land units. 
  There is no movement bonus for Rivers, and Triremes are going non diagonal.

- Some key techs require no holes in its tech roots. To acquire a tech you must know its
  prerequisites, and you cannot lose a tech that another depends on.

- Enabled risk of Plague at cities with population greater than 4. Chances
  reduced by the buildings Aqueduct, Sewer System, Lazaretto/Hospital
  and the wonders: Pasteur Institute and Cure for Cancer.

FOODBOX:
--------

not changed yet

TERRAIN:
--------

- Jungles receive +1 Shield (2/1/0) with Railroad on its tile and Railway Station in city. 
  Swamps can be irrigated for +1 Food (to 2/0/0), next irrigation convert them to grassland. 
  Tundras can be mined for +1 Shield (instead of irrigated)
  and receive +1 Trade when roaded (up to 1/1/1).

- Deserts with a river receive 1 extra Food from irrigation (total 2),
  unless they have an Oasis; this simulates a growth boost like Nile
  floods.

- Mountains give extra vision range. Cities can not be placed over
  Mountains. Regular military units can't go into unroaded mountains, except of spec-ops units.

- Mines+Railroads in mountains and deserts give extra Shield production, if Cement Plant and Railroad Station is builded in city. 
  Mines+Railroads on coal give extra trade point in above case. 

- Mines+Railroads on coal give extra Shield production, if Steel Plant and Railroad Station is builded in city. 
  Mines+Railroads on iron give extra trade point in above case. 

- Forest give extra Shield production, if Textille Mill is builded in city. 

- Mines on deserts give extra Shield production, if Manufacture is builded in city. 
- Mines on coal give extra gold production in above case, or if Coal Power and Railroad Station plant is builded in city. 

- The discovery of Refining allows to upgrade the mines placed on
  Deserts and Glaciers to Oil Wells (+2 Shields in total). Refinery gains additional gold from each Oil Well on Oil.

- Deep ocean tiles must be mined (resulting in an Oil Platform) in order to
  take advantage of the shield bonus from Offshore Platforms. Refinery in city is required.

- Pollution may appear in Ocean tiles, and Transports or Barges can clean it
  without the need of Workers/Engineers. Jungles and Forests are less
  affected by global warming.

- No minimum city output. City central tile simply gets  +1 Shield, +1 Trade.

- Irrigation possible with Agriculture Farming tech, and can be performed if River, Lake or Swamp is adjacent to tile, 
or another irrigated tile is cardinally adjacent. Electricity allow to irrigate if Sea is cardinally adjacent, 
and Recycling allow to irrigate without any restrictions.

- Transforming terrain from forest/to forest possible with Forestry tech.

- Making mines possible with Bronze Working tech.

- Tile transform is possible when Fusion tech is known (with some earlier exception for barges).

TILE      F/P/T  IRRIG(t)   MINE(t)    ROAD   MAX1   MAX2   TRANSFORM
Deep      1/0/2  NO         NO         NO     2/0/2  2/1/2  No
Ocean     1/0/2  NO         NO         NO     2/0/2  2/1/2 *Grass(36)
Lake     *2/0/2  NO         NO         NO     2/0/2  2/1/2 *Grass(36)
Swamp     1/0/0 *+1(5)     *NO         +0(4)  2/0/0  3/0/0 *Grass(24)
Glacier   0/0/0  NO         +1(10)     +0(4)  0/1/0  0/3/0 *Lake(24)
Tundra    1/0/0 *NO        *+1(5)     *+1(2)  1/1/1  1/1/1 *Plains(24)
Desert    0/1/0  +1(5)      +1(5)      +1(2)  0/2/1  0/4/1  Plains(24)
Plains    1/1/0  +1(5)      Forest(10) +1(2)  2/1/1  3/1/1 *Lake(36)
Grassland 2/0/0  +1(5)      Forest(15) +1(2)  3/0/1  4/0/1 *Lake(36)
Jungle   *1/1/0 *Swamp(10) *NO         +0(4)  1/1/0  1/1/0 *Forest(24)
Forest    1/2/0  Plain(10) *Grass(15)  +0(4)  1/2/0  1/3/0 *Hills(24)
Hills    *1/1/0  +1(10)    *+2(10)     +0(4)  1/3/0  1/4/0  Plains(24)
Mountains 0/1/0  NO        *+2(10)     +0(6)  0/3/0  0/4/0  Hills(36)

F/P/T = Food/Production/Trade; (t) = turns
MAX1 = irrigated/mined/roaded/harbour; MAX2 = farmland/railroad/oil well.
* = Changes compared to classic ruleset. Most affected are Jungles,
    Swamps and Tundras.

DEFENSE:
--------

- Halved the terrain defense bonuses, now more similar to civ3 values:

TERRAIN                  NEW      OLD
Forest/Jungle/Swamp      +25%     +50%
Hills                    +50%     +100%
Mountains                +100%    +200%

RIVER                    +25%     +50%

VETERAN
Recruit                  +25%     (=)
Veteran                  +50%     (=)
Hardened                 +75%     (=)
Elite                    +100%    (=)
Veteran Elite            +125%    (=) 

FORTIFIED                +50%     (=)
(only Land, Big Land and spec-ops Small Land units can fortify; inside cities, they are
always considered fortified)

BASE             VS LAND  VS SEA   VS AIR   VS MISSILE
Fort             +50%     +50%     +0%      +0%
Fortress         +100%    +100%    +50%     +50%
Airstrip         +0%      +0%      +50%     +50%
Airbase          +50%     +50%     +100%    +100%

CITY             VS LAND  VS SEA   VS AIR   VS MISSILE
Ruins	  	      +25%
Town (Pop<=8)    +50%     +0%      +0%      +0%
City (Pop>8)     +100%    +50%     +0%      +0%

Buildings each add:
Walls            +100%    +0%      +0%      +0%
Great Wall(W)    +50%     +0%      +0%      +0%
Coastal Defense  +0%      +100%    +0%      +0%
SAM Battery      +0%      +0%      +100%    +0%
SDI Defense      +0%      +0%      +0%      +100%

- Every City of any size receives an inherent Defend_Bonus = +50%
  against all kinds of land units.

- Every City with Pop>8 receives an additional free Defend_Bonus = +25%
  against land units.

- Every City with Pop>16 receives an additional free Defend_Bonus = +25%
  against both land and sea units.

- Walls effect reduced from 200% to 100%, and cost reduced from 60
  to 30. Bonus not apply against plunging fire units. Walls upkeep 1 gold.

- Great Wall gives additional Defend_Bonus = +50% against Land units,
  and prevents population loss in any city when a defending unit loses.

Total Defense = (UNIT DEFENSE) * (100+TERRAIN)/100 * (100+RIVER)/100
 * (100+CITY+BASE)/100 * (100+FORTIFIED)/100 * (100+VETERAN)/100
(Same as classic rules).


GOVERNMENTS:
------------
					anar	trib	desp	monar	a.rep	repub	a.dem	demo	commu	funda	feder thala imper						
shield base waste			30	30	10	20	10	5	15	25	10	15	30	15	0																						
shield dist. waste		x	x	/2**	/2**	/2	/4**	/2	/4	x	/2	x	/4**	/4																						
food base waste		10	20	0	0	0	0	10	25	30	10	20	0	0																						
food dist. waste		x	x	/1	/2	/2	/4	/4	x	x	/2	x	/4	/2																						
gold base waste		30	30	20	10	20	25	10	5	30	15	5	10																							
gold dist. waste		0	0	/1*	/2*	/2	/2	/4*	/4	x	/2	x	/4	/2																						

max rate				x	60	90	80	70	60	50	40	90	40	70	60	80																						

science bonus/penalty			-25%	-50%			25%	25%	50%		-75%			-50%																						
gold bonus/penalty			-25%			25%	50%		25%	-50%		25%																								
tile production penalty	 -1 if>2 -1 if>2 -1if >2																																

empire size				x	8	10	14	14	16	20	32	28	18	24	12	16																						
empire size step			x	4	8	14	12	16	16	32	14	10	12	12	8	

martial law each			1	0	1	1	1	0	0	0	2	0	0	1	2	
martial law max			3		3	2	1				3			2	2	

celebrate					Y	Y	Y	Y	Y			Y			

veteran+					Y											Y	

has senate								Y	Y	Y				Y	Y				

revolution								Y	Y	Y	Y				Y		
incite cost multiplier		0.5	2	1	1	1	5	5	100xx	4	10	2	2	1x	x with statue of Liberty
bribing cost multiplier		0.5	1	1	2	5	100xx	1	5	1	1	2	1	4	xx 10 without slavery abolition

lux															+2	+1		

unit upkeep shield		1	1	1	1	1	1	1	1	1	1	1	1	2																						
unit upkeep food			1	1	1	1	1	1	1	1	2	1	1	1	1																						
unit upkeep gold			x	1	1	1	1	1	2	2	1	2	2	1	1																						
																																				
unhappy factor			0	0	0	1	1	1	1	2	0	1	1	1	1																						
max unit abroad free		2	2	2	3	2	1	2	2	3	2	2	2	4																						
size doubled max abroad				8	8					8	8			8																						

free upkeep shield		2	2	3	4	2	1	4	3	3	6	8	4	4																						
free upkeep food size 4		4	6	4	4	4	3	4	3	6	4	4	4	3																						
free upkeep gold			x	8	2	3	3	2	3	2	8	4	4	2	6																						
																																				
size doubled free u. shield					8			8	8		8	8																								
																																				
size doubled free u. gold					8	8			4				8																						

* Corruption by Distance is doubled until Banking is researched
  by the player
** Waste by Distance is doubled until The Corporation is researched by the player.
+ Partisans appear in conquered cities (democratic or communist) if
  Guerilla Warfare has been researched by any player.


TECHS:
------


BUILDINGS:
----------

Altered effects - 

Barrack:
Tier I: Recruits for Small Land (and Wheeled Units under Despotism), Veteran for Land units.
Tier II: Recruits for Small Land and Wheeled Units, Veteran for Land units.
Tier III: Recruits for Small Land and Wheeled Units, Veteran for Land and Big Land units.

Harbour:
Deckhand level for Sea class (cumulative with Lighthouse), 25% faster HP regen for Sea and Trireme.

Supermarket: not required for farmland bonus/creation (second irrigation after Chemical Synthesis), 
instead of, reduce distance food waste (and base food waste for Democracy or Federation).
Add 25% gold city income if Railway Station is builded.

Super Highways, Courthouse, City Walls, Airport, Mass Transit: see CITY SIZE

Colosseum: add 3 luxury points (4 with Electricity) instead of making content.

Bank, Stock Exchange: only Tax increase.

Super Highways: 25% Trade increase with Stock Exchange.


New buildings:

Manufacture:
25% city production bonus and pollution, 
bonus trade points from coal mines, bonus shields points from desert mines, 
obsoleted by Corporation

Textille Mill
50% city production and pollution, 
bonus shields points from forest, bonus trade points from silk, 
require river, 
obsoleted by Plastics

Steel Mill
100% city production bonus and 150% city pollution,
shield bonus from coal mines, trade bonus from iron mines, 
require Railway Station,
conflicting with Research Lab 

Cement Plant
50% city production bonus and 100% city pollution,
shield bonus from mountain or desert mines, trade bonus from coal mines, 
require Railway Station,
conflicting with Research Lab 

Railway Station
Necessary to gain additional bonuses from Railroad tiles. 
Default shield bonus from any railroad decreased to 25%, but railroad together with Railway Station 
yield additional output from some special resources or from mines (together with Steel Mill, Cement Plant or Coal Plant). 
Instant hp regen of train class units.
Increased city radius size.

Oil Refinery
100% tile production bonus from desert Oil Wells, trade points from Oil Wells on oil field,
required for Oil Shore Platform.

Lazaretto
plague probability 20% less

Hospital
plague probability 20% less (40% less with Pasteur Institure wonder)

CITY SIZE:
--------

Please note: recommended hexagon topology.

Initial city workable square radius 1. 
Radius of workable area will grow with:
city size 2 (rect. topo.)
City Hall
Railway Station (with Electricity) or Eiffel Tower.
Super Highways (with Combustion)
Airport (with Electricity and Combustion)

Initial city vision square radius 8.
City vision area will grow with:
city size 3 with Courthouse,
occupied city with -
City Walls
Airport (with Electricity)

WONDERS:
--------

Altered:
Great Library obsololeted by Computers,
Map Reveal shifted from Apollo to GPS
Shakespeare's Theatre obsoleted by Nanotechnology
(note: obsoleted wonders still support permanent granted worldwide bonuses).
No pollution reduction form Eiffel Tower (it is used to increase town influence and vision radius)
Women Suffrage: additional trade point/tile in Democracy, or Shield point/tile in Republic.
Internet: 

New:

Pasteur Institute
1 immediate tech and plague probability 20% less with Hospital 
(together with all water/sewage amenities and Hospital, total protection is 90%, with Cure Cancer, 100%)

Slavery Abolition
Increased min size not causing unhappiness under democracy, but penalty on rich tiles trade (gold gives 5, not 6). 
This small wonder is required for Women's Suffrage.

MIT
1 new tech, 4 bulbs for city, 50% for any research lab

Global Positioning System
Map revealed

LHC
2 new techs, convenient method to achieve Great Unification Theory, which is very expensive

Space lift
Required to make Spaceship Structurals

Hollywood:
Neutralizes the unhappiness caused by aggressively deployed military unit, like original Women Suffrage.
Unlike other wonders, Hollywood have expensive upkeep.

Marie Curie Mobile X-ray fleet
Faster heal of infantry units.

DARPA
Randomly upgrade unit. New Land, Small and Big Land units have Recruit rank (with Barrack, Hardened for Land and Big Land units). 
Prerequisite to Internet wonder.


BONUS EFFECTS:

25% defense for Small Land class in Ruins
Increased unit vision benefit from Satellite System


UNITS:
------

Following units groups:
* regular Land units - defensive infantry, assault infantry, fast assault units, peacemakers - can't move into mountains/glaciers (some units can attack it).
* reconnaissance Small Land units (explorers, archers, snipers etc) - can move everywhere;
* direct fire artillery - movement restricted to roads (less restriction for self-propelled units), can't occupy towns, can attack non native tiles;
* plunging fire artillery - movement restricted to roads (less restriction for self-propelled units), ignore walls, bombardment action, can't occupy towns, can attack non native tiles;
* Big Land class - movement more restricted than for regular Land class, but less compared to Wheeled Units. Can't be loaded on some units.
* Turrets - can't move by itself (can reside in cities/forts/airstrips), can be boarded on Sea units/armoured trains, can attack from and at non native tiles;
* Sea class units: can go on Ocean tiles;
* Trireme class units: can go on Coast Ocean, River and Lake tiles;
* Air class units, Helicopters, Missiles: can go everywhere;
* Bombs, Torpedos - can be loaded on Air units (and some Sea units).


upkeep -	production	sh.	fd.	gold	unh.	A	D	HP	FP	BR	MP	mov.restr.	fuel	comments
														
initial														
tribe	10	0	1	0	1	1	1	5	1		1			
														
civilian		0		0	0									
settlers	30	0	2	1	0	0	1	20	1		1			
migrants	10	0	1	1	0	0	1	10	1		1			
workers	20	0	1	1	0	0	1	10	1		1			
engineers	30	1	0	1	0	0	2	20	1		2			
														
peacemakers														
warriors	10	0	0	1	0	1	1	10	1		1	m,g		
halberdier	15	0	0	0	0	1	2	15	1		1	m,g		
riot police	20	0	1	0	0	1	3	15	2		1	m,g		
														
reconnaissance														
archers	25	1	1	0	0	2	1	5	1	3	1			IgWall, AttNoNat.
marksman	55	1	1	0	0	6	2	10	2	1	1			IgTer, AttNoNat.
sniper	60	1	1	0	0	9	4	10	2	1	1			IgTer, InVis, AttNoNat.
														
defending														
phalanx	20	0	1	0	0	1	2	15	1		1	m,g		
pikemen	30	0	1	0	0	2	3	15	1		1	m,g		Horse *2
musketeers	40	1	1	0	0	2	4	10	2		1	m,g		
riflemen	45	1	1	0	0	3	5	10	2		1	m,g		AttNoNat
infantry	50	1	1	0	0	3	6	12	2		1	m,g		AttNoNat
modern rangers	55	1	1	0	0	4	6	15	2		1	m,g		AttNoNat
														
assaulting														
legion	30	0	1	0	0	3	2	15	1		1	m,g		
arbalest	35	1	1	0	0	5	1	10	1		1	m,g		AttNoNat
swordsmen	40	0	1	0	0	4	2	15	1		1	m,g		
arquebusiers	45	1	1	0	0	4	3	10	2		1	m,g		
grenadier	55	1	1	0	0	5	4	10	2		1	m,g		
stormtrooper	60	1	1	0	0	6	4	12	2		1	m,g		
marines	65	1	1	0	0	8	4	15	2		1	m,g		Marines
super soldiers	75	2	1	0	0	9	5	15	2		1	m,g		Marines
														
paratroopers	60	1	1	0	0	6	5	15	2		1	m,g		Paratroopers
														
spec-ops														
vikings	20	0	1	0	0	1	1	5	1		1			Unique,Marines,AttNoNat
corsairs	30	1	1	0	0	2	1	10	2		1			Unique,Marines,AttNoNat
navy seals	50	1	1	0	0	8	2	12	2		1			Unique,Marines,AttNoNat,InVis
alpine troops	65	1	1	0	0	7	5	12	2		1			IgTer
														
other														
partisan	40	1	1	0	0	5	3	10	2		1			IgTer, IgZOC
fanatics	20	1	1	0	0	4	5	10	2		1	m,g		Fanatic
														
technical	50	1	0	0	0	18	4	15	2		2	only r		Fanatic, Missile
														
cavalry														
horsemen	18	0	1	0	0	2	1	10	1		2	m,g		
mounted archery	25	0	1	0	0	3	1	10	1		2	m,g		AttNoNat
chariot	30	0	1	0	0	4	1	10	1		2	m,g,j,s		
elephants	50	0	2	0	0	3	2	20	1		2	m,g		
crusaders	40	0	2	0	0	5	1	15	1		2	m,g		Fanatic
knights	45	0	2	0	0	4	2	15	1		2	m,g		
dragoons	55	1	2	0	0	5	2	12	2		2	m,g		AttNoNat
cavalry	65	1	2	0	0	7	4	12	2		2	m,g		AttNoNat
mech. Inf.	80	2	1	0	0	6	6	20	2		3	m,g		AttNoNat
														
armoured														
armoured train	120	2	0	0	0	6	8	30	2	2	10	only rr, turret+		
armor	100	3	0	0	0	10	5	30	2		2	m,g,j,s		Lights. *2, AttNoNat
reactive armor	130	3	0	0	0	11	5	30	2		3	m,g,j,s		Lights. *3, AttNoNat
autonomous war mech	180	2	0	0	0	7	3	20	3		2	m,g,j,s		AttNoNat
														
plunging fire artillery														
catapult	45	1	0	0	0	6	1	5	1	1	1	only r		IgWall, AttNoNat
cannon	60	2	0	0	0	7	1	5	2	2	1	only r		IgWall, AttNoNat
howitzer	80	2	0	0	0	9	1	10	2	2	1	only r		IgWall, AttNoNat
self-propelled howitzer	110	3	0	0	0	10	2	25	2	3	2	m,g,j,s		IgWall, AttNoNat
mobile anti aircraft gun	120	2	0	0	0	8	4	20	2	4	3	m,g,j,s		AttNoNat
														
stationary artillery														
ballista	35	1	0	0	0	7	1	5	1		1	only f		NoVeteran, AttNoNat
bombard	45	2	0	0	0	8	1	5	2		1	only f		NoVeteran, AttNoNat
turret cannon	60	3	0	0	0	11	2	10	2		1	only f		NoVeteran, AttNoNat
turret aa gun	50	2	0	0	0	7	2	10	2		2	only f		NoVeteran, AttNoNat
														
siege artillery														
battering ram	40	1	0	0	0	7	1	10	1		1	only r		CityBuster, AttNoNat
artillery	60	2	0	0	0	10	2	10	2		1	only r		CityBuster, AttNoNat
self-propelled gun	90	3	0	0	0	12	3	20	2		2	m,g,j,s		CityBuster, AttNoNat
														
planes														
airplane	40	1	0	0	0	4	4	10	1		8		1	
zeppelin	70	2	0	0	0	5	2	10	1	1	4		4	
fighter	60	2	0	0	0	5	5	15	2		8		2	
bomber	110	3	0	0	0	6	2	20	2	2	6	bomb+	4	
helicopter	90	2	0	0	0	5	3	30	2	2	6			
strike aircraft	80	2	0	0	0	4	3	15	2		7	bomb/t+	2	
jet fighter	90	2	0	0	0	6	6	20	2		12		2	
strike jet	100	3	0	0	0	7	4	25	2		10	bomb/t+	2	
stealth fighter	130	3	0	0	0	8	8	25	2		14	bomb/t+	2	
stealth bomber	200	4	0	0	0	9	5	40	2	4	10	bomb+	4	
antimatter fighter	240	3	0	0	0	9	9	20	2		16	bomb/t+	3	
antimatter bomber	360	4	0	0	0	10	6	30	2	6	12	bomb+	6	
														
river/coast boats														
raft	10	0	0	0	0	0	1	5	1		2			
trireme	30	0	2	0	0	1	1	15	1		3			
aak	35	0	2	0	0	0	2	15	1		3			
steam_barge	50	1	1	0	0	0	2	20	1		3			
diesel_barge	55	1	1	0	0	0	3	20	1		4			
														
river/coast warships														
galley	45	0	2	0	0	2	3	20	1		3	turret+		
monitor	60	1	1	0	0	2	5	20	2		4	turret+		
patrol boat	75	2	1	0	0	3	5	20	2		6	turret/t+		
														
sea boats														
longboat	30	0	1	0	0	0	1	10	1		2			Unique
cog	40	0	2	0	0	0	3	10	1		3			
galleon	50	0	2	0	0	0	3	20	1		4			
paddle steamer	65	1	1	0	0	0	4	20	1					
transport	80	2	1	0	0	0	5	40	1		5			
														
sea warships														
caravel	50	0	2	0	0	2	4	15	1		3			turret+
frigate	60	0	2	0	0	3	4	20	1		4			turret+, AttNoNat
flagship frigate	80	0	2	0	0	5	8	20	1		5			Unique, turret+, AttNoNat
ironclad	70	1	1	0	0	4	5	20	2		4			turret+, AttNoNat
destroyer	90	1	1	0	0	4	6	25	2		6			turret/t+, AttNoNat
cruiser	120	2	1	0	0	5	10	30	2		5			turret+, AttNoNat
battleship	160	3	2	0	0	6	11	40	2		4			turret+, AttNoNat
aegis cruiser	180	4	1	0	0	7	12	40	2		5			turret/c+, AttNoNat
railgun destroyer	130	1	1	0	0	4	7	30	3		6			turret/t+, AttNoNat
														
other ships														
submarine	140	2	1	0	0	4	5	20	2		5			torpedo+
nuclear_submarine	190	3	1	0	0	5	6	25	2		6			torpedo/m+
carrier	150	2	1	0	0	0	9	40	1		5			
														
missiles														
cruise missile	50	1	0	0	0	18	0	10	3		16		1	
Abomb	160	1	0	0	0	99	0	10	2		2		1	
nuclear	190	2	0	0	0	99	0	10	3		16		1	
torpedo	25	1	0	0	0	10	0	5	2		2		1	
GBU	20	0	0	0	0	8	0	5	2		1		1	
														
espionage														
messenger	20	0	1	0	0	0	0	10	1		1			no incite
diplomat	30	0	1	1	0	0	0	10	1		2			
spy	40	0	1	2	0	0	0	10	1		3			
														
land transport														
caravan	50	0	1	2	0	0	1	10	1		1			
freight	50	1	0	0	0	0	1	20	1		2			
train		1	0	0	0									
														
exploration														
explorer	20	0	0	0	0	0	1	5	1		1			IgTer
leader		0	0	0	0	0	2	20	1		2			
balloon		0	0	0	0									
AWACS	140	2	0	0	0	0	1	30	2		16		3	
drone	80	1	0	0	0	4	2	10	2		12			
