# raz
Regions, Areas and Zones for Minetest

## Inspired by 
+ areas - ShadowNinja
+ pvp_areas - pvp_areas

# The Idea
a mod to do them all
- mark regions and show them in a hud
- protect areas, invite guests 
- create zones for PvP {Player vs. Player}
- prevent damage for player in cities {Mobdamage vs. Player - MvP}
- give areas an effect like 

|effect| description | |
|-----|-----|-----|
|hot| heal over time
|bot | restore breath over time
holy | both: heal an breath over time 
dot| damage over time
choke | reduve breath over time
evil | both: damage and choke over time

## Versions
- v 0.1 - start of the projekt
- v 0.2	- placing regions, zones an areas by hand and these commands: region_mark pos1, region_mark pos2, region_mark set **region_name**
- v 0.3 - adding the effects. Protection is working. protection_violation makes damage
- v 0.4 - export and import regions to/from file, convert and import areas from ShadowNinja areas mod!
- v 0.5	- guest-status works, commands region_set *params* 
- v 0.6 - more commands fot modifying the attributs

roadmap
	- PvP, MvP attribute
	- PvP - module 
	- items from mod marker
	- more commands
	- clear code

## Privilegs:
+ "region_admin" ==> modify all regions, import, export regions, convert areas.dat, ...
+ "region_effect" ==> Can set and remove effects for own regions.
+ "region_mvp" ==> Can enable/disable MvP for own regions.
+ "region_pvp" ==> Can enable/disable PvP for own regions.
+ "region_set" ==> Can invite/ban guests or change owner of own regions.
+ "region_mark" ==> Can set, remove and rename own regions and protect and open them.

## commands

|command|parameters|what does the command do|who can use is
|------|------|-------|-------| 
region *help* | **command** | Get some infos about the use of the *command* | privileg: interact
region *status* | no params | Get some more infos about the region at your position. | privileg: interact
region *pos1* | no params |	Set one corner for the region |  privileg: region_mark
region *pos2* | no params |	Set the second corner for the region |  privileg: region_mark
region *set*  | **region_name**| Marks an region with the name **region_name** | privileg: region_mark
region *remove* | **ID** | Remove an OWN-region with the **ID** | privileg: region_mark
region *protect* | **ID**| Protect the region with the ID (only OWN regions) | privileg: region_mark
region *open* | **ID** | Opens the region with the **ID** for all players to 'dig' (only OWN regions).| privileg: region_mark
region *invite* **ID** **name** | Invites player **name** as guest in your OWN-Region with the **ID** - The guest player can 'dig' and 'build' like in an own protected region.| privileg: region_set
region *ban* | **ID** **name** | Bans the player **name** from the guestlist of your region with the **ID**.| privileg: region_set
region *change_owner* | **id** **new owner** | Changes the owner from your region (**ID**) to **new owner**.| privileg: region_set
region *pvp* | **ID** **+/-** | Make your zone to become an arena with PvP (globaly PvP must be enabled) | privileg: region_pvp
region *mvp* |  **ID** **+/-** |Enable or disable that mobs can damage the player | privileg: region_mvp
region *effect* |**ID** **none,hot,bot,holy,dot,choke,evil** | Create an effect in your zone.<br> hot = heal over time,<br> dot = damage over time,<br>...|privileg: region_effect
region *parent* | **ID** **+/-**  | Mark an region as parent. Other regions can only be placed in 'wildernesss' or in an parent region. | privileg: region_admin
region *show* | no params | Shows a list of all regions-data values from all regions | privileg: region_admin
	| **ID** | Shows a list of all values from regions-data in the region **ID** | privileg: region_admin
	| **ID1** **ID2** | Shows a list off all values in the range of **ID1** to **ID2** | privileg: region_admin 
region *import* | no params| Import the regions from raz.export_file_name. | privileg: region_admin 
region *export* |  no params| Export all region to raz.export_file_name.| privileg: region_admin 
region *convert_areas* |  no params| Conversts areas from ShadowNinja areas! - read existing areas.dat - create an raz.areas_raz_export file for import_areas.| privileg: region_admin 
region *import_areas* |  no params| Import the file: raz.areas_raz_export.| privileg: region_admin 




