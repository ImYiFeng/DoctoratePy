# DoctoratePy
Python server implementation of a certain anime tower defense game. This repo is for the CN TapTap Version.

Discord Invite: [Link](https://discord.gg/pUj8HQ5FQU)

## How To

1. Install [mitmproxy](https://mitmproxy.org/) and [python3](https://www.python.org/downloads/).
2. Clone the repo.
3. Open emulator.
4. Run `setup_mitmproxy.bat`.
5. Configure your proxy ip address in `config\config.json` in the `host` key.
6. Run `start.bat` in the cloned folder.

Note: There should be a total of 4 cmd windows opened.

## Currently tested emulator to be working
1. LDPlayer9

## Changing contengency contract season
Change the value of key `selectedCrisis` in `config\config.json` to whatever you want. The avaiable seasons are under `data\crisis`.

## Customizing indivual operators level, potentials, skill ranks and others
Customize each operator indivually by adding new info in `customUnitInfo` key in `config\config.json`. You can find <operator_key_name> from [here](https://raw.githubusercontent.com/Kengxxiao/ArknightsGameData/master/zh_CN/gamedata/excel/character_table.json). By default, all characters will have max level, max potentials, max mastery.

- `favorPoint` - Trust points (25570 is 200% Trust) [link to exact point to %](https://gamepress.gg/arknights/core-gameplay/arknights-guide-operator-trust)
- `mainSkillLvl` - Skill Rank (Put mastery at 0 if this is lower than 7)
- `potentialRank` - 0-5
- `evolvePhase` - 0 - E0, 1 - E1, 2 - E2
- `skills` - Mastery level for each skill starting from S1.

### Format
```
"<operator_key_name>": {
    "favorPoint": 25570,
    "mainSkillLvl": 7,
    "potentialRank": 2,
    "level": 50, 
    "evolvePhase": 1,
    "skills": [1, 0]
}
```

## Customizing support unit
Customize the support unit list by changing the unit info in `assistUnit` key in `config\config.json`. All characters info can be found [here](https://raw.githubusercontent.com/Kengxxiao/ArknightsGameData/master/zh_CN/gamedata/excel/character_table.json).

- `charId` - key of the character
- `skinId` - skinId of the character (Skin List can be found [here](https://raw.githubusercontent.com/Kengxxiao/ArknightsGameData/master/zh_CN/gamedata/excel/skin_table.json))
- `skillIndex` - Skill Index of the support unit (Index starts from 0).

Note: Characters stats and skill masteries are based on the above parameters.

### Format
```
{
    "charId": "char_350_surtr",
    "skinId": "char_350_surtr@it#1",
    "skillIndex": 2
}
```

## TODO
- [ ] Add more info about mods
- [ ] Add a UI for easy editing
