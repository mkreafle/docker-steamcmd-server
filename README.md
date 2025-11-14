# SteamCMD in Docker optimized for Unraid
This Docker will download and install SteamCMD. It will also install Voyagers of Nera Dedicated Server and run it.

**Update Notice:** Simply restart the container if a newer version of the game is available.

## Env params
| Name | Value | Example |
| --- | --- | --- |
| STEAMCMD_DIR | Folder for SteamCMD | /serverdata/steamcmd |
| SERVER_DIR | Folder for gamefile | /serverdata/serverfiles |
| GAME_ID | The GAME_ID that the container downloads at startup. If you want to install a static or beta version of the game change the value to: '3937860 -beta YOURBRANCH' (without quotes, replace YOURBRANCH with the branch or version you want to install). | 3937860 |
| GAME_PARAMS | Enter your start up commands for the server if needed. | none |
| UID | User Identifier | 99 |
| GID | Group Identifier | 100 |
| VALIDATE | Validates the game data | true |
| USERNAME | Leave blank for anonymous login | blank |
| PASSWRD | Leave blank for anonymous login | blank |

## Run example
```
docker run --name VoyagersOfNera -d \
	-p 7777-7779:7777-7779/tcp -p 7777-7779:7777-7779/udp \
	--env 'GAME_ID=3937860' \
	--env 'UID=99' \
	--env 'GID=100' \
	--volume /path/to/steamcmd:/serverdata/steamcmd \
	--volume /path/to/voyagersofnera:/serverdata/serverfiles \
	mkreafle/steamcmd:voyagers
```


This Docker was mainly edited for better use with Unraid, if you don't use Unraid you should definitely try it!


This Docker is forked from mattieserver, then from ich777, thank you for this wonderfull Docker.
