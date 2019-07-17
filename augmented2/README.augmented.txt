=================================
Augmented2 Ruleset for Freeciv v2.6
=================================


OBJECTIVES:
-----------

- Better balanced and more sophisticated technology tree, 62 new techs.
  Facultative advance paths based on Asiatic culture (Arab, Hindu, Chinese, Japonese) 
  - not required for mainstream technology path, but granting some extra units/buildings/wonders.

- Clearly distinctive tiers of military unit classes: 
  defensive infantry, assault infantry, fast assault units, reconnaissance, 
  direct fire artillery, plunging fire artillery, peacekeepers, turrets etc.

- Well defined tiers of ships classes: river/coastal merchants, river/coastal warships, ocean merchants, ocean warships. 

- Ships and armoured train have decreased attack alone, but can be equipped with turret guns (destroyer and patrol boat also torpedos). 
- Submarines can carry torpedos (nuclear submarine also missiles). 
- Bombers, strike aircrafts/advanced fighters can carry bombs (and torpedos). 

- Enginners can carry other unit.

- New buildings and wonders, adopted to the new technology tree. 
  Some industrial improvements give additional bonus from certain tiles.
  City radius depend on city size and improvements.

- Some building and especially wonders require certain level of Culture Points. These can be earned 
  each turn from some other buildings, or granted by special events.

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

- Mountains give extra vision range for small reconnaissance units. Cities can not be placed over
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

- Tile transform is possible when Combustion tech is known (with some earlier exception for steam barge).

- Terrain transformation pattern -
transfOrm:
Mountains -> Hills <-> Plains 
Grassland -> Swamp <-> Lake
Jungle -> Plains 
Forest -> Tundra -> Desert -> Plains
Glacier -> Lake
Irrigate:
Forest -> Grasslands
Jungle -> Swamp
Swamp -> Grassland
Mining:
Forest -> Plains
Grassland -> Forest
Jungle -> Forest
Plains -> Desert
Swamp -> Jungle

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
(only military units can fortify; inside cities, they are
always considered fortified)

BASE             VS LAND  VS SEA   VS AIR   VS MISSILE
Fort             +50%     +50%     +0%      +0%
Fortress         +100%    +100%    +50%     +50%
Airstrip         +0%      +0%      +50%     +50%
Airbase          +50%     +50%     +100%    +100%

CITY             VS LAND  VS SEA   VS AIR   VS MISSILE
Ruins	  	      +25% for Small Land
Town (Pop<=8)    +50%     +0%      +0%      +0%
City (Pop>8)     +100%    +50%     +0%      +0%

Buildings each add:
Walls            +100%    +0%      +0%      +0%
Palisade         +25%
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

1. 
All governments pay shield, food and gold upkeep, however upkeep free differ depending on government. 
For example Monarchy have 4 unit shield upkeep free, but only 3 units gold upkeep free, 
while First Republic only 1 unit shield  upkeep free, but 4 units gold upkeep free. 
Food upkeep depend only on city size (except of Communism, which offer more free food).

2. Neither government is immune on bribery or revolting (except of cities with Palace etc). 
However cost of such actions depend on government.

3. There is no extra gold per tile in Democracy or Republic 
(unless Women's Suffrage wonder exists, wich gives such effect for Democracy, or extra shield for Republic).
But some governments have bonuses or penalties while producing gold, science or luxury.
For example science and gold is suppressed under Tribalism, while improved under Republic.

4. Additional unhappines is generated proportional to enemy nationality percentage in your city.
It can throw out Tribal, Democracy or Republic gov.

Gov. table reference:
				anar. tri.	desp. mon. f.rep. rep.	d.dem. dem.	com.	fund.	fed.	thal.	fasc.					

shield base waste		50	30	10	20	10	5	20	25	10	15	25	20	0					
shield dist.waste		x	x	/2**	/2**	/2	/4**	/2	/4	x	/2	x	x	/4					
food base waste		30	0	0	0	0	0	10	20s	30	0	15s	0	10s					
food dist. waste		x	x	/1	/2	/2	/2	/4	x	x	/2	/4	/4	/2					
gold base waste		x	30*	20	10	20	25	10	5	30	15	5	10	20					
gold dist. waste		x	0	/1*	/2*	/2	/2	/4*	/4	x	/2	x	/4**	/2					
max rate			x	60	90	80	70	60	50	40	90	40	70	60	80					
																			
* Corruption by Distance is doubled until Banking is researched  by the player																			
** Waste by Distance is doubled until The Corporation is researched by the player																			

sci.bonus/penalty		n	-25%	-50%	n	n	25%	25%	50%	n	-50%	n	n	-25%
gold bonus/penalt		n	-25%	n	n	25%	50%	n	25%	-50%	n	25%	n	n
lux bonus/penalty		-50%	n	n	-25%	n	n	n	25%	-75%	n	n	25%	-75%
tile prod.penalty	 -1 if >2 -1 if >2 -1 if >2							   -1 if >2 shield land	

empire size			x	8	10	14	16	16	20	32	28	14	24	12	16
empire size step		x	4	8	14	14	16	16	32	14	10	24	12	8

martial law each		1	0	1	1	1	0	0	0	2	0	0	1	2
martial law max		3		3	2	1				3			2	2
% enemy unhappy		100	100	100	100	100	50	60	33	70	100	80	33	150

celebrate					Y	Y	Y	Y	Y			Y	Y	

veteran+				Y											Y

has senate							Y	Y	Y	Y 			Y	Y	

revolution				Y			Y	Y	Y					
incite multiplier		0.5	2	1	1	1	2	2	2/10**	1	10	3	1	x/2*	* with statue of Liberty				
bribing multipl.		0.5	1	1	2	2	2/10**	1	5	1	5	3	1	4	** 10 without slavery abolition				

lux												+2	+1						

unit upkeep shield	1	1	1	1	1	1	1	1	1	1	1	1	2					
unit upkeep food		1	1	1	1	1	1	1	1	2	1	1	1	1					
unit upkeep gold		x	x	1	1	1	1	2	2	1	2	2	1	1					

unhappy factor		0	0	0	1	1	1	1	2	1	1	1	3	1					
max unit abroad		2	2	2	3	2	1	0	0	3	2	1	2	4					

free upkeep shield	2	2	3	4	1	0/1	3	3	3	6	2	4	4					
					
free upkeep gold		x	x	2	3	4	3	1	0/1	8	4	2	1	6					

* Corruption by Distance is doubled until Banking is researched
  by the player
** Waste by Distance is doubled until The Corporation is researched by the player.
+ Partisans appear in conquered cities (democratic or communist) if
  Guerilla Warfare has been researched by any player.


TECHS:
------
Improved tech tree.
New techs:

* absolutism 
* agricultural_farming 
* alchemy 
* animal_husbandry 
* antimatter_propulsion 
* artificial_intelligence 
* astronomy 
* biology 
* biotechnology 
* buddhism 
* bushido 
* carpentry 
* chemical_synthesis 
* christianity 
* cinematography
* concrete 
* confucianism 
* craft_guilds 
* creative_art 
* desert_code 
* direct_democracy 
* drama
* egalitarianism 
* electromagnetism 
* exploration 
* federation 
* fire_making 
* first_republic 
* forestry 
* fundamentalism 
* glass_working 
* great_unification_theory 
* hinduism 
* imperialism 
* islam 
* jet_propulsion 
* leather tanning
* legalism 
* machinery 
* mass_entertainment
* modern_theatre
* modern_warfare 
* nanotechnology 
* offshore_exploration 
* paper_making 
* pastoralism 
* printing_press 
* quantum_theory 
* radar 
* radioactivity 
* saddle_stirrup 
* satellite_system 
* screw_propeller 
* shinto 
* shogunate 
* sikhism 
* simple_machines 
* slave_trade 
* socialism 
* stone_knapping 
* super_soldiers 
* taoism 
* thalassocracy 
* theory_of_relativity 
* turbine 
* vedism 
* zaibatsu 


BUILDINGS:
----------

Altered effects - 

Barrack:
Infantry Barracks -
Tier I: Recruits for Small Land, Veteran for Infantry units.
Tier II: Recruits for Small Land, Veteran for Infantry units (trade bonus if Saltpeter tile is workable in city)
Stable Barracks: Recruits for Light Cavalry, Veteran for Heavy Cavalry.
Workshop Barrack: Veteran for Wheeled Units, Big Land, Mech. Inf.

Harbour:
Deckhand level for Sea class (cumulative with Lighthouse), 25% faster HP regen for Sea and Trireme.

Supermarket: not required for farmland bonus/creation (second irrigation after Chemical Synthesis), 
instead of, reduce distance food waste (and base food waste for Democracy or Federation).
Add 25% gold city income if Railway Station is builded.

Super Highways, Courthouse, City Walls, Airport, Mass Transit: see CITY SIZE

Colosseum: Small Wonder, increase luxury by 50% and make 1 military unhappy citizen content.
Amphitheatre: add 3 luxury points (only 2 with Cinematography) 
Theater add 2 luxury points (4 with Cinematography)

Bank, Stock Exchange: only Tax increase.
Marketplace: overall Trade increase.

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
Increased city radius size with Eiffel Tower or Mass Transit.

Oil Refinery
100% tile production bonus from desert Oil Wells, trade points from Oil Wells on oil field,
required for Oil Shore Platform.

Lazaretto
plague probability 20% less

Hospital
plague probability 20% less (40% less with Pasteur Institure wonder)

Monk Monastery: add 4 science points to the city (and 1 unhappy citizen content, if player posses Buddha Statue).
Shrine Torii: cheap temple improvment (extra 1 unhappy citizen content).
Church: makes 2 unhappy citizens content (3 with J.S. Bach's Cathedral), required for Cathedral.
Mosque: makes 2 unhappy citizens content, additionally neutralizes unhappiness caused by one military unit (Kaaba required).

Note: Sacral building improvments, belonging to different faiths, doesn't mix 
(temple/church/mosque can't exists in same city)

CITY SIZE:
--------

Please note: recommended hexagon topology.

Initial city workable square radius 1. 
Radius of workable area will grow with:
city size 2 (rect. topo.)
City Hall
Railway Station with
Eiffel Tower or Mass Transit

Initial city vision square radius 8.
City vision area will grow with:
city size 3 with Courthouse,
occupied city with City Walls
city with Watchtower
Airport or Eiffel Tower (with Electricity)

WONDERS:
--------

Altered:
Great Library obsololeted by Computers,
Map Reveal shifted from Apollo to GPS
Shakespeare's Theatre obsoleted by Television.
No pollution reduction form Eiffel Tower (it is used to increase town influence and vision radius)
Women Suffrage: additional trade point/tile in Democracy, or Shield point/tile in Republic. For unhapiness see: Hollywood.
Internet: do not reveal map (use GPS instead).
Great Wall: add defense also to fortress.

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
Unlike other wonders, Hollywood has expensive upkeep.

Marie Curie Mobile X-ray fleet
Faster heal of infantry units.

DARPA
Randomly upgrade unit. Small Land military units have Recruit rank (with Barrack, veteran). 
Prerequisite to Internet wonder.

Additional faith wonders:

Leshan Buddha Statue
Add +1 food for each river tile within city radius, neutralises 1 unhappy citizen for each city in the World with Monk Monastery.

Kaaba: Add extra gold from each road tile within city radius. Each Mosque neutralizes unhappiness caused by one military unit.

Angkor Wat: Act as second Palace (but can't be build if Player already have Ecclesiastical Palace or opposite), 
add 4 Luxury point to the city where is located.

Golden Temple: 
Make one more happy citizen for each Temple, Church or Mosque.

Western Wall: 50% defense for city (cumulative with City Walls, not cumulative with Great Wall),
gold bonus as for Colossus (extra trade from each tile generating trade).

Note: different faith wonders (above and Cathedrals or Crusade) doesn't mix 
(can't exists in same country, except of Golden Palace and Western Wall, which are ecumenic).

GREAT/SMALL WONDERS SUMMARY:
---------------------------


BONUS EFFECTS:

25% defense for Small Land class in Ruins
Increased unit vision benefit from Satellite System


UNITS:
------

Caravans and migrants are unique units. Freights and Slaves are not unique. 

Following military unit groups:
* Infantry units - defensive or assault infantry - can't move into mountains (some units can attack it).
* fast assault units: LightCavalry - can't move into mountains/glaciers (some units can attack it), Heavy Cavalry - cant go also into Swamps.
* reconnaissance Small Land units (explorers, archers, snipers, peacemakers etc) - can move everywhere;
* direct fire artillery - movement restricted to roads and flat tiles (less restriction for self-propelled units), can't occupy towns, can attack non native tiles;
* plunging fire artillery - movement restricted to roads and flat tiles (less restriction for self-propelled units), ignore walls, bombardment action, can't occupy towns, can attack non native tiles;
* Big Land class - movement more restricted than for regular Land class, but less compared to Wheeled Units. Can't be loaded on some units.
* Turrets - can't move by itself (can reside in cities/forts/airstrips), can be boarded on Sea units/armoured trains, can attack from and at non native tiles;
* Sea class units: can go on Ocean tiles;
* Trireme class units: can go on Coast Ocean, River and Lake tiles;
* Air class units, Helicopters, Missiles: can go everywhere;
* Bombs, Torpedos - can be loaded on Air units (and some Sea units).
* Diplomatic actions and espionage: Messenger, Diplomat, Spy (and unique Corsair, Ninja, Navy Seals)

Units reference table:

upkeep -	prod.	sh.	fd.	gold	unh.	A	D	HP	FP	BR	MP  m.restr. fuel/pop cap.  comments
															
initial															
tribe		15	0	1	0	0	1	1	5	1		1		1P		
															
civilian															
settlers	24	1	2	1	0	0	1	20	1		1		2P		
migrants	12	1	1	0	0	0	1	10	1		1		1P		unique
workers		15	1	1	1	0	0	1	10	1			1			capturable
engineers	30	2	0	1	0	0	2	20	1		2				
slaves		15	0	1	0	0	0	1	5	1			1		1P	capturable	capturable
															
peacemakers															
militia 	6	0	1	1	1	1	1	10	1		1				
halberdier	10	1	1	1	1	2	2	12	1		1				
riot police	15	2	1	1	1	2	3	15	2		1				
															
reconnaissance															
hunters		10	1	1	1	1	2	1	5	1	1	1			AttNoNat.
archers		15	2	1	1	1	2	1	6	1	3	1			IgWall, AttNoNat.
marksman	25	2	1	2	1	6	2	10	2	1	1			IgTer, AttNoNat.
sniper		35	2	1	3	1	9	4	10	2	1	1			IgTer, InVis, AttNoNat.
															
defending															
phalanx		10	1	1	1	1	1	2	12	1		1	m,g			
pikemen		15	1	1	1	1	2	3	15	1		1	m,g			Horse *2
musketeers	20	2	1	1	1	2	4	10	2		1	m,g			
riflemen	30	2	1	1	1	3	5	12	2		1	m,g			AttNoNat
infantry	40	2	1	2	1	3	6	12	3		1	m,g			AttNoNat
modern rangers	50	2	1	2	1	4	6	15	3		1	m,g			AttNoNat
															
assaulting															
skirmishers 	10	1	1	1	1	2	1	10	1		1	m,g			
legion		18	1	1	1	1	3	2	14	1		1	m,g			
arbalest	20	2	1	1	1	5	1	10	1		1	m,g			AttNoNat
swordsmen	25	1	1	1	1	4	2	15	1		1	m,g			
samurai		30	1	1	1	1	5	4	15	1		1	m,g			
arquebusiers	30	2	1	1	1	4	2	10	2		1	m,g			
grenadier	40	2	1	1	1	6	3	10	2		1	m,g			
stormtrooper	50	2	1	2	1	6	4	12	3		1	m,g			
marines		60	2	1	2	1	8	4	15	3		1	m,g			Marines
super soldiers	70	3	1	2	1	9	5	15	3		1	m,g			Marines
															
paratroopers	55	2	1	2	1	6	5	12	3		1	m,g			Paratroopers
															
spec-ops															
vikings		15	0	1	1	1	1	1	5	1		1			Unique,Marines,AttNoNat
corsairs	20	1	1	2	1	2	1	10	2		1			Unique,Marines,AttNoNat
navy seals	40	2	1	3	1	8	2	12	3		1		Unique,Marines,AttNoNat,InVis
ninja		60	1	1	3	1	5	2	12	1		1	Unique,Marines,AttNoNat,InVis,Spy,IgTer
alpine troops	55	2	1	2	1	7	5	12	2		1				IgTer
															
other															
partisan	15	1	0	0	1	5	3	10	3		1		1P		IgTer, IgZOC
fanatics	20	1	1	0	1	4	5	10	3		1	m,g	1U		Fanatic
janissary	30	2	1	1	1	4	4	12	2		1	m,g			AttNoNat
technical	45	2	0	2	1	18	4	15	3		2	only r		1	Fanatic, Missile
															
															
light cavalry															
															
mounted archery	18	1	2	1	1	3	1	10	1		2	m,g			AttNoNat
dromedari	25	1	2	1	1	4	2	10	1		2	m,g			
lancers		35	2	2	1	1	4	3	10	2		2	m,g			AttNoNat
bicycle inf.	40	2	1	2	1	5	3	10	2		2	m,g			AttNoNat
ATV troops	50	3	1	2	1	7	4	10	3		3	m,g			AttNoNat
															
															
heavy cavalry															
horsemen	12	1	2	1	1	2	1	12	1		2	m,g			BadWallAttacker
chariot		20	1	2	1	1	4	1	10	1		2	only r			BadWallAttacker
elephants	35	1	3	1	1	3	2	20	1		2	m,g,s			BadWallAttacker
crusaders	25	1	2	2	1	5	1	16	1		2	m,g			Fanatic, BadWallAtt.
knights		30	1	2	1	1	4	2	16	1		2	m,g			BadWallAttacker
mounted samurai	35	1	2	1	1	5	3	15	1		1	m,g			BadWallAttacker
cuirassier	40	2	2	1	1	4	3	14	2		2	m,g			BadWallAttacker
dragoons	50	2	2	2	1	6	4	12	2		2	m,g			BadWallAttacker
mounted. Inf.	60	2	2	3	1	6	5	12	3		3	m,g		AttNoNat, BadWallAtt
mech. Inf.	75	3	1	3	1	6	6	20	3		3	m,g		AttNoNat, BadWallAtt
															
armoured															
armoured train	90	3	0	2	1	6	8	30	3	2	10	only rr, turret+		3	BadWallAtt
armor		80	4	0	3	1	10	5	30	3		2	m,g,s			Lights. *2, AttNoNat, BadWallAtt
reactive armor	100	4	0	4	1	11	5	30	3		3	m,g,s			Lights. *3, AttNoNat, BadWallAtt
aut. war mech	130	3	0	4	0	7	3	20	3		2	m,g,s			AttNoNat, BadWallAtt
															
plunging fire artillery															
catapult	40	2	0	2	1	6	1	5	1	1	1	only r			IgWall, AttNoNat
cannon		50	3	0	2	1	7	1	5	2	2	1	only r			IgWall, AttNoNat
howitzer	65	3	0	3	1	9	1	10	3	2	1	only r			IgWall, AttNoNat
s-pr. howitzer	90	4	0	4	1	10	2	25	3	3	2	m,g,s			IgWall, AttNoNat
mob. a-a gun	80	3	0	3	1	8	4	20	3	4	3	m,g,s			AttNoNat
															
stationary artillery															
ballista	20	2	0	1	0	7	1	5	1		1	only f		NoVeteran, AttNoNat
bombard		30	3	0	1	0	8	1	5	2		1	only f		NoVeteran, AttNoNat
turret cannon	50	4	0	2	0	11	2	15	4		1	only f		NoVeteran, AttNoNat
turret aa gun	40	3	0	2	0	7	6	10	3		2	only f		NoVeteran, AttNoNat
															
siege artillery															
battering ram	30	1	1	2	1	7	1	12	1		1	only r		CityBuster, AttNoNat
artillery	45	3	0	2	1	10	2	10	2		1	only r		CityBuster, AttNoNat
Anti-tank gun	60	3	0	3	1	10	3	12	3		2	only r		CityBuster, AttNoNat
s-prop. gun	75	4	0	3	1	12	4	25	3		2	m,g,s	CityBuster, AttNoNat
															
planes															
airplane	30	2	0	2	1	4	4	10	2		8		1		
zeppelin	50	2	1	2	1	5	2	10	2	1	4		4		
fighter		40	3	0	2	1	5	5	15	3		8		2		
bomber		90	3	1	2	2	6	2	20	3	2	6	bomb+	4	2	
helicopter	75	3	0	3	1	5	3	30	3	2	6				
strike aircraft	60	3	0	2	1	4	3	15	3		7	bomb/t+	2	1	
jet fighter	70	3	0	2	1	6	6	20	3		12		2		
strike jet	90	4	0	2	1	7	4	25	3		10	bomb/t+	2	1	
stealth fighter	110	4	0	3	1	8	8	25	3		14	bomb/t+	2	1	
stealth bomber	200	4	1	3	2	9	5	40	3	4	10	bomb+	4	3	
a.matt. fighter	170	4	0	4	1	9	9	20	3		16	bomb/t+	3	1	
a.matt. bomber	280	4	1	4	2	10	6	30	3	6	12	bomb+	6	2	
															
river/coast boats															
canoe		15	0	1	1	0	0	1	5	1		2			1	unique
raft		10	1	0	0	0	0	1	5	1		2			1	
trireme		20	1	2	1	1	1	1	15	1		3			2	
aak		25	1	2	1	0	0	2	20	1		3			3	
steam_barge	40	2	1	1	0	0	2	25	1		3			4	
diesel_barge	50	2	1	2	0	0	3	25	1		4			5	
															
river/coast warships		0	0		0										
galley	30	1	2	2	1	2	3	20	1		3	turret+		1	
monitor	50	2	1	2	1	2	5	20	2		4	turret+		1	
patrol boat	60	3	1	2	1	3	5	20	3		6	turret/t+		1	
															
sea boats															
longboat	20	0	1	1	0	0	1	10	1		2			1	Unique
cog	30	1	2	1	0	0	3	10	1		3			2	
Junk	25	1	2	1	1	2	2	10	1		3			2	
galleon	40	1	2	1	0	0	3	20	1		4			3	
paddle steamer	50	2	1	2	0	0	4	25	1		4			6	
transport	65	3	1	2	0	0	5	40	1		5			8	
															
sea warships															
caravel		40	1	2	1	1	2	4	15	1		3			1	turret+
frigate		50	1	2	2	1	3	4	20	1		4			1	turret+, AttNoNat
flagship fr.	70	1	2	3	1	5	8	20	1		5			2	Unique, turret+, AttNoNat
ironclad	60	2	1	2	1	4	5	20	2		4			1	turret+, AttNoNat
destroyer	65	2	1	3	1	4	6	25	3		6			1	turret/t+, AttNoNat
cruiser		85	3	1	4	1	5	10	30	3		5			2	turret+, AttNoNat
battleship	100	4	2	4	2	6	11	40	4		4			3	turret+, AttNoNat
aegis cruiser	120	4	1	4	2	6	12	40	4		5			3	turret/c+, AttNoNat
railgun destr.	80	2	1	4	1	4	7	30	4		6			2	turret/t+, AttNoNat
															
other ships															
submarine	90	3	1	3	1	4	5	20	2		5			4	torpedo+
nucl.submarine	120	4	1	4	1	5	6	25	3		6			8	torpedo/m+
carrier		110	3	1	4	1	0	9	40	2		5			8	
															
missiles															
cruise missile	40	2	0	2	1	18	0	10	4		16		1		
Abomb		150	2	0	3	3	99	0	10	3		2		1		
nuclear		180	3	0	3	3	99	0	10	4		16		1		
torpedo		20	2	0	1	0	10	0	5	3		2		1		
GBU		15	1	0	1	0	8	0	5	3		1		1		
															
espionage															
messenger	15	0	1	1	0	0	0	10	1		1				no incite
diplomat	20	0	1	2	0	0	0	10	1		2				
spy		30	1	1	3	0	0	0	10	1		3				
															
land transport															
caravan		30	0	1	1	0	0	1	10	1		1				Unique
freight		50	1	0	1	0	0	1	20	1		2				
train		60	1	0	2	0										
															
exploration															
explorer	15	0	1	1	0	0	1	5	1		1				IgTer
leader		0	0	0	0	0	2	20	1		2				
balloon		15	1	0	1	0										
AWACS		120	3	0	3	0	0	1	30	3		16		3		
drone		70	2	0	1	0	4	2	10	3		12				


Author: Wahazar
