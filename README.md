# WoW_BiS_List

Note: page-data.json files were manually downloaded from wowtbc.gg as the python-Requests calls were reading as html/text instead of application/json.
**If you wish to run this script, you'll need to manually download those .json files yourself!**

For legal reasons, I've put a git.ignore on the "wowtbc/" folder referrenced in my code because I am utilizing data that is not my own (wowtbc's). Although it is public, and therefore I assume it is safe to utilize/consume, I'm still a new programmer and I'd rather play it safe!

# Project Goal
Raiding is stressful enough, but loot just dropped and people are fighting/arguing what is BiS (Best in Slot) for them vs someone else -- That makes things REAL stressful!

No one person can be expected to the BiS rankings of every item dropped in raid to each cooresponding class/spec! (Not even multiple people can likely fragment that information between them).

##### Goal:
> Create dictionaries that can help Raid leaders/Loot Masters determine, at a glance, who are the BiS users when an item drops in raid

What this code will do:

1. Compile information from various BiS websites
2. Rank items from "1" to "X" based on the respective website's BiS ranking indicator (Ex: wowtbc.gg has "final_value" where a larger value indicates that item being better than another item of the same slot/spec/class)
3. Have 2 dictionaries:
> a) Dicitionary indicating BiS items for a given Class/Spec <br>
> b) Dictionary indicating the class/spec ranking for a given item (reverse of A)
4. Write these dictionaries to .csv
5. (Not shown here, done separately outside of python) Create an amazing Google Sheet utilizing this information to allow Raid Leaders + Loot Masters to make educated decisions when it comes to distribution of loot based on their guild's loot rules (Ex: MS > OS, No Loot over Loot)
---- If my guild is okay with random viewers, I may be able to provide a "view only" link to said Google Sheet, but I will need their permission first.

# Outputs (**Not provided** - Run the code on your own to generate these!)
1. `wowtbc_list.csv` = List of all current phase ("T4") items and their class/spec/slot/ranking/source.
2. `raid_BiS_wowtbc_list.csv` = A shortened version of (1) which only contains raid specific loot. Used in my google sheet to run a vlookup(class+spec+slot) to generate a BiS list (like what wowtbc.gg shows on their webpage -- only they have these green arrows which actually indicate that item being **better** than what they were displaying ... not sure why they do this).
3. (The ultimate goal I was coding for) `BiS_dictionary_wowtbc.csv` = Dictionary to do a reverse search of the above (2) list. Input = ItemName, Output = BiS ranking for all class/spec that use it. In my google sheet I use this to run a vlookup(item_name) and have it spit out who the item is BiS for. That way the raid can focus on playing the game, and less on "That is my BiS" or "I think that is my BiS".