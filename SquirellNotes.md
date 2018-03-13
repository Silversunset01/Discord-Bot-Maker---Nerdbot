# Discord Bot Maker Scripting Tips and Tricks

## Prefix
Usage | Script
:- |:-
the bot as client (user) | `${this.getDBM().Bot.bot` 
the command message | `${msg`
the current server (where 'this message' was sent) | `${msg.guild`

## Javascript Magic
Usage | Script
:- | :-
Force Lower case | `.toLowerCase()`
Force Upper case | `.toUpperCase()`
Force string | `.toString()`
Replace | `.replace("old text","new text")` 
Switch | `switch(thing to eval) {` <br /> `case "OPT1": action to execute on match; break;` <br />`case "OPT2": action to execute on match; break;` <br />`case "OPT3": action to execute on match; break;` <br />`default: action to execute on match; break;` <br /> `}`
If/Then (Ternery) | `(A < 1 ? "value if true" : "value if false")`
If/Then (Normal) | `if(thing to evaluate) {value if true} else {value if false}`

    
## Math & Operations
Usage | Script
:- | :-    
round down | `${Math.floor(yourvariable)}`
Force variable to be read as a number | `${parseInt(yourvariable)}`
Translate milliseconds to days | `${Math.floor((tempVars("uptime-ms") % 31536000) / 86400)}` 
Translate milliseconds to hours (up to 24) | `${Math.floor((tempVars("uptime-ms") % 86400) / 3600)} `
Translate milliseconds to minutes (up to 60) | `${Math.floor((tempVars("uptime-ms") % 3600) / 60)}`
Translate milliseconds to seconds (up to 60) | `${Math.round(tempVars("uptime-ms") % 60)}`
    
## Lists
Usage | Script
:- | :-    
Show items in a list | `.array}`
Count items in the specified list | `.array().length}`

## Emojis
Usage | Script
:- | :-    
Find Emoji | `client.emojis.find("name", "NameOfTheEmoji")`
Add reactions to message (embed) | `msg.channel.send(tempVars("e"))` <br/> `.then(function (message) {` <br/> `message.react("👍")` <br/> `message.react("👎")` <br/> `}).catch(function() {` <br/> `msg.channel.send("is broke yo")` <br/> `});`
Add reactions to message (normal) | `msg.channel.send("your text here"` <br/> `.then(function (message) {` <br/> `message.react("👍")` <br/> `message.react("👎")` <br/> `}).catch(function() {` <br/> `msg.channel.send("is broke yo")` <br/> `});`

## Miscellaneous
Usage | Script
:- | :-
skip ahead some number | `this.callNextAction(#)`
store variables via script | `this.storeValue(output, 1 ,"totalUsers", cache)` <br /> (*1 = temp, 2 = server, 3 = global*)
Show current date/time in timezone | `new Date().toLocaleString("en-US", {timeZone: "America/New_York"})`
Create server invite | `msg.channel.createInvite({temporary: true}," Showing the usage").then(invite=> msg.channel.send(invite.url))`
Return Server Icon URL | `${msg.guild.iconURL}`
Return Server Verification Level | `${msg.guild.verificationLevel}`
Return Server Explicit Content Filter | `${msg.guild.explicitContentFilter}`
Return Server Creation Date | `${msg.guild.createdAt}`
Return Server Name | `${msg.guild.name}`
Return Server Owner Display Name | `${msg.guild.owner.displayName}`
Return Server Available Status | `${msg.guild.available}`
Return Server Region | `${msg.guild.region}`
Return Server Creation Date | `${msg.guild.createdAt}`
Return Server Owner Display Name | `${msg.guild.emojis.array().length}`
Return Server Emojis List | `${msg.guild.emojis.array()}`
Return Server Emojis Count | `${msg.guild.emojis.array().length}`
Return Server Count of Roles | `msg.guild.roles.array().length`
Return Server Member Count | `${msg.guild.memberCount}`
Return Server Online members | `${msg.guild.members.filter(m => m.user.presence.status == \"online\").size}`
Return Server Offine members | `${msg.guild.members.filter(m => m.user.presence.status == \"offline\").size}`
Return Server Idle members | `${msg.guild.members.filter(m => m.user.presence.status == \"idle\").size}`
Return Server DND members | `${msg.guild.members.filter(m => m.user.presence.status == \"dnd\").size}`
Return Server Count of Channels | `${msg.guild.channels.array().length}`
Return Server Count of Text Channels | `${msg.guild.channels.findAll('type', 'text').length}`
Return Server Count of Voice Channels | `${msg.guild.channels.findAll('type', 'voice').length}`
Return Server AFK Channel | `${msg.guild.afkChannel}`
Return Server AFK Timeout (in seconds) | `${msg.guild.afkTimeout}`
Return Count of Members in all Bot Guilds | `${this.getDBM().Bot.bot.users.array().length}`
Return Count all Bot Guilds | `${this.getDBM().Bot.bot.guilds.array().length}`
Return List all Bot Guilds | `${this.getDBM().Bot.bot.guilds.array()}`
Program memory usage (in MB) | `${Math.floor((process.memoryUsage().heapUsed / 1024)/1024)}`

