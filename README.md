# Funcionamiento del bot
# Español
.env = este archivo sirve vincular todo el bot a un servidor de dc
- TOKEN= token de la app
- CLIENT_ID= id de la app
- GUILD_ID= id del servidor
- VERIFY_ROLE= debes crear un rol de verificado abajo del roll de miembro y poner su id aqui
- UNVERIFIED_ROLE= debes crear un rol de no-verificado arriba del roll de miembro y poner su id aqui
- MEMBER_ROLE= id del roll de miembro
- LOG_CHANNEL= canal de logs
- JOIN_LIMIT=5 
- JOIN_TIME=5
- SERVER_NAME= nombre de su server


index.js = lanzador de varios archivos

# ./src/
- deploy-commands.js = registra los comandos de ./src/commands/
- index.js = configuracion de inicio del bot
- utils.js = ayuda con los logs

# ./src/commands/
- /ban banea a un usuario
- /kick saca un usuario de tu discord
- /lockdown Cierra todos los canales de texto para los miembros no verificados
- /logs crea logs
- /mute aisla a un usuario
- /purge  borra hasta 100 msg
- /softban ban + unban inmediato
- /unlock Abre los canales bloqueados por lockdown
- /unmute desmutea un usuario
- /verification manda el mensaje de verficacion

# ./src/events/
- guildMemberAdd.js = al entrar un user al sv de dc le añade el roll de no verificado y le quita el roll de miembro si lo tiene, y manda un log a la carpeta ../src/logs/ y un log a un canal de logs.
- guildMemberRemove.js = un usuario al salir del discord se envia un log a la carpeta ../src/logs/ y a un canal de logs.
- interactionCreate.js = aqui se crea el botton para el embed de verificacion.
- messageCreate.js = este es el sistma  anti spam/flood, prohibir palabras, NSFW, y enlaces, este achivo manda logs a un canal de logs y a la carpeta ../src/logs/ .
- ready.js = manda un mensaje de inicio a la terminal

# ./src/utils/
- logs.js = configuracion de logs


# Bot Functionality
# English

# .env
This file connects the bot to your Discord server
TOKEN=Your bot application token
CLIENT_ID=Your application ID
GUILD_ID=Your Discord server ID
VERIFY_ROLE=ID of the Verified role (must be below the Member role)
UNVERIFIED_ROLE=ID of the Unverified role (must be above the Member role)
MEMBER_ROLE=ID of the Member role
LOG_CHANNEL=ID of the logs channel
JOIN_LIMIT=5
JOIN_TIME=5
SERVER_NAME=Your server name


index.js
Main launcher file that starts the bot


# ./src/
Main source folder

deploy-commands.js
Registers all slash commands from ./src/commands/

index.js
Bot startup configuration

utils.js
Helper utilities for logs


# ./src/commands/
Slash commands

/ban          -> Bans a user
/kick         -> Kicks a user from the Discord server
/lockdown     -> Closes all text channels for unverified members
/logs         -> Creates logs
/mute         -> Mutes a user
/purge        -> Deletes up to 100 messages
/softban      -> Ban + instant unban
/unlock       -> Reopens channels closed by lockdown
/unmute       -> Unmutes a user
/verification -> Sends the verification message


# ./src/events/
Discord event handlers

guildMemberAdd.js
When a user joins the server:
- Assigns the Unverified role
- Removes the Member role if present
- Sends logs to ../src/logs/
- Sends logs to the logs channel

guildMemberRemove.js
When a user leaves the server:
- Sends logs to ../src/logs/
- Sends logs to the logs channel

interactionCreate.js
Creates the verification button for the embed

messageCreate.js
Anti-spam system:
- Flood protection
- Banned words
- NSFW detection
- Link blocking
- Sends logs to the logs channel and ../src/logs/

ready.js
Sends a startup message to the terminal when the bot is ready


# ./src/utils/

logs.js 
logs configuration
