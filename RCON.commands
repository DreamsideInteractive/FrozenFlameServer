# Server Commands
Server commands allow you to get more information regarding your server's players, control their access to it and affect their in-game state or inventory.
Currently servers support following commands:
- Angle brackets disignate <Required-parametres> - such parametres must be entered for the command to work.	
- Square brackets disignate [Optional-parametres] - such parametres can be entered in addition to the command.
	
	
* **Users and Profiles**:
	- Admin_GetOnlinePlayers - Displays names and IDs of currently joined players.
	- Admin_ListUserProfiles - Lists profiles of all players who ever joined the server.
	- Admin_ReloadUserProfiles - Reloads user profiles; useful in case of profile deletion/transfer.
	- Admin_SaveUserProfile - Saves user profiles in their current state.
	- Admin_RemoveUserProfile <PlayerID> - Removes the stated user's profile.
	- Admin_RemoveProfile <PlayerID> - Removes the stated player from the server, including his save data.
	- Admin_AddUserProfile <PlayerID> <UserRoleAsString> - Adds a disignated role to the stated user.
	- Admin_InfoUserProfile <PlayerID> - Displays detailed profile info of the stated user.
	
* **Kicks and Bans**:
	- Admin_KickPlayer <PlayerID> <Reason> - Kicks the stated player with shown reason.
	- Admin_Chatban <PlayerID> <Seconds> <Reason> - Bans the stated player from using chat for the specified amount of time.
	- Admin_ChatUnban <PlayerID> - Allows the stated player to use chat again.
	- Admin_Ban <PlayerID> <Seconds> <Reason> - Bans the stated player from the server for the specified amount of time.
	- Admin_Unban <PlayerID> - Unbans the stated player.
	
* **Server Manipulation**:
	- Admin_Shutdown - Shuts down the server.
	- Admin_Restart - Restarts the server.
	- Admin_ServerWorld - Displays the current version of the server.
	- Admin_SaveWorld - Saves the world in its current state.
	- Admin_SaveAll - Saves both the world and player profiles in their current state.
	- Admin_ScheduleMaintenanceMode <Seconds> - Schedules a maintenance and displays an in-game message.
	- Admin_CancelScheduledMaintenanceMode - Cancels the scheduled maintenance.
		
* **Player Interaction**:
	- Admin_GetPlayerInfo <PlayerID> - Displays additional information about a player.
  	- Admin_GetPlayerInventory <PlayerID> - Displays item IDs and their amount in a player's inventory.
	- Admin_AddItem <PlayerID> <ItemID> <Amount> - Adds stated items to a player's inventory.
	- Admin_RemoveItem <PlayerID> <ItemID> <Amount> - Removes stated items from a player's inventory.
	- Admin_AddFlame <PlayerID> <Amount> - Gives the specified amount of XP to the stated player.
	- Admin_RemoveFlame <PlayerID> <Amount> - Removes the specified amount of XP from the stated player; cannot reduce the player's level.
	- Admin_Respawn <PlayerID> - Respawns the stated player.
	- Admin_SetCurse <PlayerID> <Amount> - _DEPRECATED! USE AT YOUR OWN RISK!_ Afflicts the stated player with Curse.
	- Admin_RemoveCurse <PlayerID> <Amount> - The supposed remedy for the previous command.
	- Admin_ChatMessage [Message] - Displays the stated message in the game chat.
	
	# Item IDs
* Consumables and Currency:
	- Coin_C - Coin
	- FrozenFlame_C - Frozen Flame
	- TeleportStone_C - Return Stone
	- HealthPotion_C - Health Potion
	- EnergyPotion_C - Energy Potion
	- StaminaPotion_C - Stamina Potion
	- SolidEssence_c - Solid Essence
	- CrystalEssence_C - Crystal Essence
	- PortalEssence_C - Astral Essence
	
* Tools and Weapons
	- **I Tier**:
		- WoodenAxe_W - Stone Axe
		- WoodenPike_W - Stone Pickaxe
		- WoodenTorch_W - Wooden Torch
		- WoodenClub_W - Stone Mace
		- WoodenGreatSword_W - Stone Two-handed Sword
		- WoodenSword_W - Stone Sword
		- WoodenGreatAxe_W - Stone Battleaxe
		- WoodenStaff_W - Wooden Staff
		- WoodenBow_RW - Wooden Bow
	- **II Tier**:
		- BoneAxe_W - Bone Axe
		- BonePick_W - Bone Pickaxe
		- BoneTorch_W - Bone Torch
		- BoneClub_W - Bone Mace
		- BoneSword_W - Bone Sword
		- BoneGreatSword_W - Two-handed Bone Sword
		- BoneGreatAxe_W - Bone Battleaxe
		- BoneStaff_W - Bone Staff
		- BoneBow_RW - Bone Bow
	- **III Tier**:
		- MetalAxe_W - Metal Axe
		- MetalPick_W - Metal Pickaxe
		- MetalTorch_W - Metal Torch
		- MetalMace_W - Metal Mace
		- MetalSword_W - Metal Sword
		- MetalGreatSword_W - Metal Two-handed Sword
		- MetalGreatAxe_W - Metal Battleaxe
		- MetalStaff_W - Metal Staff
		- MetalBow_RW - Metal Bow
	
* Armor and Equipment:
	- **Cloth Set**:
		- ClothHelmet_A - Cloth Bandana
		- ClothArmor_A - Cloth Robe 
		- ClothGloves_A - Cloth Gloves
		- ClothPants_A - Cloth Pants
		- ClothBoots_A - Cloth Foot Wraps
	- **Rawgide Set**:
		- RawhideHelmet_A - Rawhide Helmet
		- RawhideArmor_A - Rawhide Armor
		- RawhideGloves_A - Rawhide Gloves
		- RawhidePants_A - Rawhide Pants
		- RawhideBoots_A - Rawhide Boots
	- **Leather Set**:
		- LeatherHelmet_A - Leather Helmet
		- LeatherArmor_A - Leather Armor
		- LeatherGloves_A - Leather Gloves
		- LeatherPants_A - Leather Pants
		- LeatherBoots_A - Leather Boots
	- **Bone Set**:
		- BoneHelmet_A - Bone Helmet
		- BoneArmor_A - Bone Armor
		- BoneGloves_A - Bone Gauntlets
		- BonePants_A - Bone Pants
		- BoneBoots_A - Bone Boots
	- **Chitin Set**:
		- ChitinHelmet_A - Chitin Helmet
		- ChitinArmor_A - Chitin Armor
		- ChitinGloves_A - Chitin Gloves
		- ChitinPants_A - Chitin Pants
		- ChitinBoots_A - Chitin Boots
	- **Metal Set**:
		- MetalHelmet_A - Metal Helmet
		- MetalArmor_A - Metal Armor
		- MetalGloves_A - Metal Gloves
		- MetalPants_A - Metal Pants
		- MetalBoots_A - Metal Boots
	- **Masks**:
		- BoneheadMask_A - Bone Mask
		- StrangerMask_A - Warrior Mask
		- ZombieIronMask_A - Black Mask
		- BubbleHelmet_A - Bubble
	
* **Resources**:
	- Branches_M - Branch
	- Wood_M - Log
	- Plank_M - Plank
	- Fiber_M - Fiber
	- Fabric_M - Fabric
	- Leather_M - Nibbler Leather
	- Hide_M - Large Boar Hide
	- Fur_M - Ram Hide
	- Hide_02_M - Manticore Hide
	- Bones_M - Ancient Bones
	- Ivory_M - Tusks
	- Horn_M - Ram Horn
	- Stone_M - Stone
	- Flint_M - Flint
	- Block_M - Stone Block
	- Ore_M - Iron Ore
	- Coal_M - Coal
	- IronBar_M - Iron Ingot
	- FlaskEmpty_C - Empty Waterskin

* **Quest Items**:
	- Quest_CradleBowZombieMask_C - Skull Hunter Mask
	- Quest_CradleAxeZombieMask_C - Raging Slayer Mask
	- Quest_CradleStaffZombieMask_C - Smoldering Warlock Mask
	- Quest_CradleClubZombieMask_C - Master's Mask
	- Quest_Tambourine_C - Cursed Tambourine
	- Quest_TambourineMallet_C - Cursed Tambourine Mallet
	- Quest_Dombra_C - Cursed Dombra
	- Quest_Flute_C - Cursed Flute
	- Quest_BoneheadToy_C - Unusual Toy
		
