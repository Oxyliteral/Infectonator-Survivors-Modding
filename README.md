Modding this game is surprisingly easy. Most of the data is made up of .xml files, which you can edit with a text editor like Notepad. Of course, first you have to get those .xml files.
'https://flashpointarchive.org/datahub/Extracting_Flash_Games' -> SWF Decompiling
Through the use of 'https://github.com/jindrapetrik/jpexs-decompiler/releases', you can extract the .SWF file. First, run Infectonator Survivors, then run ffdec, go to Tools > Search SWFs in memory, and click on the Infectonator Survivors app. Open or save the .swf file, and then you have the game's data. You can look through the scripts, but more importantly, you can open up the binaryData, which contains the .xml files used to make up the game's data.

For example, you can edit characters, weapons, zombies, perks, teams, materials, etc. Just look for the associated .xml file, save it as a new file, and edit it. Then, you can put it inside of the game's 'assets/mods/[Mod Name]' folder, and voila, you've created your own mod.

I've created a link to the game's .xml files, and also created a mod myself to show you how its done.
To download the .xml files, download the 'binaryData' folder.
To download my mod, download the 'Reinfected' folder. Extract it, and place it in the game's 'assets/mods' folder. It's entirely made up of .xml files, which you can edit yourself, so if you don't like a certain thing, you can simply change it.
https://drive.google.com/drive/folders/1zUKFpuVgxyt0PnzcOTKrWt4Ei1nGmZ6i?usp=sharing

Notes

When editing teams, 'new' teams will be appended to the end of the team selection screen. If you want to edit the order of the teams, you'll need to directly edit the teams in the order they originally appeared. So to set a team as the first in the list, you'll need to edit 'The Survivors', which has an id of 'team1', to be whatever team you want it to be. Then you can add 'The Survivors' back in at the end of the list by making a new team with a different id but with the same members.

Character stats:
Max Health : Min 50 - Max 300, 25/point
Speed : Min 0 - Max 100, 10/point
Search : Min 0 - Max 50, 5/point
Build : Min 0 - Max 50, 5/point
Accuracy : Min 0 - Max 100, 10/point
Melee : Min 0 - Max 100, 10/point

Most characters have a default of:
Hunger : 20
Stamina : 20

For reference, here is a character list (based of character descriptions):

Sydney - Journalist

Scientist - Search

Worker - Construction

Cop - Firearms

Cheerleader - Agile

Nerd - Runs fast when threatened

Hobo - Fights for food

Hero-Bill - L4D

Hero-Francis - L4D

Hero-Louis - L4D

Hero-Zoey - L4D

Researcher - Pharmaceuticals

Thug - Gangsta

SWAT - Special Weapons and Tactics unit

Boxer - Mean left hook

Detective - Investigator

Outdoorsman - Ordinary

Hunter - Attends open hunting season

FreddieWong - Youtube Gunmen #1

Pwnisher - Youtube Gunmen #2

Pewdiepie - King of Brofists

CutiePie - Queen of Marzipans

Ranged Accuracy Formula:
if(Math.random() * 100 > aim)
{
isMiss = true;
}
Aim directly translates to your hit percentage, so 100 aim is 100%, 0 aim is 0%, and 50 aim is 50% to hit.
Ranged Crit Formula:
if(Math.random() * 1000 < criticalChance)
{
crit = true;
}
dmg = atkDamage * (crit == true ? 2 : 1);
Ranged crits deal 2x damage, and operate off of the weapon's crit chance. Most weapons have a default 100 criticalChance, which translates to 10%.
Melee Crit Formula:
if(Math.random() * 1000 < criticalChance * (melee / 100))
{
crit = true;
}
dmg = atkDamage * (crit == true ? 3 : 1) * (melee / 100);
dmg = dmg + extraDmg;
Melee dmg is affected by them melee stat, directly translating to damage. 90 Melee means 90% melee damage, for example. Melee crits deal 3x damage, and operate on the weapon's crit chance, same as above, but is also affected by the user's melee stat. Extra damage is not affected by crits.
