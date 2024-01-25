# palworld-save-tools
Tools for converting PalWorld .sav files to JSON and back.

> [!CAUTION]
> Any versions older than v0.4 will create corrupt `Level.sav` files when converting from JSON to SAV. Please make sure to update to avoid data corruption.

This tool currently supports additional parsing of the following data not handled by `uesave`:

1. `Level.sav`:`GroupSaveDataMap`
    - Groups such as in-game organizations and guilds
1. `Level.sav`:`CharacterSaveParameterMap`
    - Characters such as players and pals

## Converting co-op saves to dedicated server saves

Please follow the instructions provided over at https://github.com/xNul/palworld-host-save-fix

## Instructions

> [!IMPORTANT]  
> Converting `Level.sav` files to JSON will result in very large files, and may require significant amounts of RAM to process. Use a modern text editor such as Visual Studio Code or a Jetbrains IDE to open these files.

### Prerequisites

1. Python. This can be installed from the Windows Store.

### Windows steps

1. Download the latest release from [https://github.com/cheahjs/palworld-save-tools/releases/latest].
1. Unzip the file into a folder.
1. Drag and drop your `.sav` file (for Steam on Windows, these are located at `%LOCALAPPDATA%\Pal\Saved\SaveGames\<SteamID>\<SaveID>`) onto `convert-single-sav-to-json.bat`.
1. To convert the `.sav.json` file back into a `.sav` file, drag and drop your `.sav.json` file onto `convert-single-json-to-sav.bat`.


# Editing save file
## Pall names

    name in game                name in save file

    Lamball
    Cattiva
    Chikipi                     ChickenPal
    Lifmunk
    Foxparks                    Kitsunebi
    Fuack
    Sparkit
    Tanzee
    Rooby
    Pengullet
    Penking
    Jolthog Cryst
    Jolthog
    Gumoss
    Gumoss (Special)
    Vixy
    Hoocrates
    Teafant
    Depresso
    Cremis
    Daedream
    Rushoar
    Nox
    Fuddler
    Killamari
    Mau Cryst
    Mau
    Celaray
    Direhowl
    Tocotoco
    Flopie
    Mozzarina
    Bristla
    Gobfin Ignis
    Gobfin
    Hangyu
    Hangyu Cryst
    Mossanda Lux
    Mossanda
    Woolipop
    Caprity
    Melpaca
    Eikthyrdeer Terra
    Eikthyrdeer
    Nitewing
    Ribunny
    Incineram
    Incineram Noct
    Cinnamoth
    Arsox
    Dumud
    Cawgnito
    Leezpunk Ignis
    Leezpunk
    Loupmoon
    Galeclaw
    Robinquill Terra
    Robinquill
    Gorirat
    Beegarde
    Elizabee
    Grintale
    Swee
    Sweepa
    Chillet
    Univolt
    Foxcicle
    Pyrin Noct
    Pyrin
    Reindrix
    Rayhound
    Kitsun
    Dazzi
    Lunaris
    Dinossom Lux
    Dinossom
    Surfent Terra
    Surfent
    Maraith
    Digtoise
    Tombat
    Lovander
    Flambelle
    Vanwyrm
    Vanwyrm Cryst
    Bushi
    Beakon
    Ragnahawk
    Katress
    Wixen
    Verdash
    Vaelet
    Sibelyx
    Elphidran Aqua
    Elphidran
    Kelpsea Ignis
    Kelpsea
    Azurobe
    Cryolinx
    Blazehowl Noct
    Blazehowl
    Relaxaurus Lux
    Relaxaurus
    Broncherry Aqua
    Broncherry
    Petallia
    Reptyro
    Ice Reptyro
    Ice Kingpaca
    Kingpaca
    Mammorest Cryst
    Mammorest
    Wumpo
    Wumpo Botan
    Warsect
    Fenglope
    Felbat
    Quivern
    Blazamut
    Helzephyr
    Astegon
    Menasting
    Anubis
    Jormuntide Ignis
    Jormuntide
    Suzaku
    Suzaku Aqua
    Grizzbolt
    Lyleen Noct
    Lyleen
    Faleris
    Orserk
    Shadowbeak
    Paladius
    Necromus
    Frostallion Noct
    Frostallion
    Jetragon


## Passive skills

### Pal overall stats
		Rank		Name				Effect
		  1			Brave				+10% Attack.						"PAL_ALLAttack_up1"
		  3			Ferocious			+20% Attack.						"PAL_ALLAttack_up2"
		 -1			Coward				-10% Attack.						"PAL_ALLAttack_down1"
		 -3			Pacifist			-20% Attack.						"PAL_ALLAttack_down1"
		  1			Hard Skin			+10% Defense.						"Deffence_up1"
		  3			Burly Body			+20% Defense.						"Deffence_up2"
		 -1			Downtrodden			-10% Defense.						"Deffence_down1"
		 -3			Brittle				-20% Defense.						"Deffence_down2"	
		  1			Aggressive			+10% Attack. -10% Defense.
		  1			Sadist				+15% Attack. -15% Defense.
		  1			Hooligan			+15% Attack. -10% Work Speed.
		  2			Musclehead			+30% Attack. -50% Work Speed.
		  1			Masochist			-15% Attack. +15% Defense.			"PAL_masochist"
		  1			Dainty Eater    		-10% Hunger drain.					"PAL_FullStomach_Down_1"
		  3			Diet Lower			-15% Hunger drain.					"PAL_FullStomach_Down_2"
		 -1			Glutton				+10% Hunger drain.					"PAL_FullStomach_Down_3"
		 -2			Bottomless Stomach	    +15% Hunger drain.
		  1			Nimble				+10% Movement Speed.
		  2			Runner				+20% Movement Speed.				"MoveSpeed_up_2"
		  3    		Swift				+30% Movement Speed.				"MoveSpeed_up_3"

### Pal Element Attack & Element Defense
		Rank		Name					Effect
			 1			Zen Mind				+10% Neutral attack damage.		"ElementBoost_Normal_1_PAL"
			 1			Abnormal				-10% Neutral attack damage.		"ElementResist_Normal_1_PAL"
			 1			Blood of the Dragon		+10% Dragon attack damage.		"ElementBoost_Dragon_1_PAL"
			 1			Dragonkiller			-10% Dragon attack damage.		"ElementResist_Dragon_1_PAL"
			 1			Fragrant Foliage		+10% Grass attack damage.		"ElementBoost_Leaf_1_PAL"
			 1			Botanical Barrier		-10% Grass attack damage.		"ElementResist_Leaf_1_PAL"
			 1			Capacitor				+10% Lighting attack damage.	"ElementBoost_Thunder_1_PAL"
			 1			Insulated Body			-10% Lighting attack damage.	"ElementResist_Thunder_1_PAL"
			 1			Veil of Darkness		+10% Dark attack damage.		"ElementBoost_Dark_1_PAL"
			 1			Cheery					-10% Dark attack damage.		"ElementResist_Dark_1_PAL"
			 1			Coldblooded				+10% Ice attack damage.
			 1			Heated Body				-10% Ice attack damage.
			 1			Power of Gaia			+10% Earth attack damage.		"ElementBoost_Earth_1_PAL"
			 1			Earthquake Resistant	-10% Earth attack damage.		"ElementResist_Normal_1_PAL"
			 1			Hydromaniac				+10% Water attack damage.		"ElementBoost_Aqua_1_PAL"
			 1			Waterproof				-10% Water attack damage.		"ElementResist_Aqua_1_PAL"
			 1			Pyromaniac				+10% Fire attack damage.
			 1			Suntan Lower			-10% Fire attack damage.

### Pal Working Efficiency
		Rank		Name					Effect
			 1			Conceited				+10% Work Speed. -10% Defense.
			 1			Work Slave				+30% Work Speed. -30% Attack.
			 2			Serious					+20% Work Speed.				"CraftSpeed_up2"
			 3			Artisan					+50% Work Speed.
			-1			Clumsy					-10% Work Speed.				"CraftSpeed_down1"
			-3			Slacker					-30% Work Speed.				"CraftSpeed_down2" 
			 1			Positive Thinker		-10% SAN drain.
			-1			Unstable				+10% SAN drain.
			 3			Workaholic				-15% SAN drain.					"PAL_Sanity_Down_2"
			-3			Destructive				+15% SAN drain.
	
### Pals Buffing Player
		Logging Foreman				"TrainerLogging_up1",
		Mine Foreman                "TrainerMining_up1"
											
        Vanguard					"TrainerATK_UP_1"
        Stronghold Strategist		"TrainerDEF_UP_1",
