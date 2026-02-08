# Funcionamiento del bot

.env = este archivo sirve vincular todo el bot a un servidor de dc

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
