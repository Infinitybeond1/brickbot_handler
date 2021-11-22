<p align="center"><img src="https://media.discordapp.net/attachments/774290264764055582/890955909566722048/0001-8574372447_20210924_191019_0000.png" height=200 width=400><br>
<a href="https://discord.gg/zqySsESftt"><img src="https://img.shields.io/badge/discord-invite-5865f2?style=for-the-badge&logo=discord&logoColor=white"></a>
<img src="https://img.shields.io/badge/version-3.2.1-05122A?style=for-the-badge">
<img src="https://img.shields.io/github/issues/RileCraft/DiscordBot-Template.svg?style=for-the-badge">
<img src="https://img.shields.io/github/forks/RileCraft/DiscordBot-Template.svg?style=for-the-badge">
<img src="https://img.shields.io/github/stars/RileCraft/DiscordBot-Template.svg?style=for-the-badge"></p>

# Developer currently on break

# 『 Changelog 』
<img src="https://emoji.gg/assets/emoji/3821-arroworange.png" width="18px" height="18px" alt="arroworange"> Fixed "unexpected throw" error thingy.

# 『 Currently Known Bugs 』
* It says "Unknown Interaction" in console when using `expireAfter` handler in SelectMenus.

# 『 Features 』
<img src="https://emoji.gg/assets/emoji/2522-arrow.png" width="18px" height="18px" alt="arrow"> Custom command handler with ton of handlers included to make ur life easier!<br>
<img src="https://emoji.gg/assets/emoji/2522-arrow.png" width="18px" height="18px" alt="arrow"> Custom event handler , button handler , selectmenu handler and slashcmds handler too!<br>
<img src="https://emoji.gg/assets/emoji/2522-arrow.png" width="18px" height="18px" alt="arrow"> Given reload commands with other main dev commands.<br>
<img src="https://emoji.gg/assets/emoji/2522-arrow.png" width="18px" height="18px" alt="arrow"> Organized layout.<br>
<img src="https://emoji.gg/assets/emoji/2522-arrow.png" width="18px" height="18px" alt="arrow"> Easily customizable.<br>
<img src="https://emoji.gg/assets/emoji/2522-arrow.png" width="18px" height="18px" alt="arrow"> Chalk logging.<br>

# 『 Important Notes 』
<img src="https://emoji.gg/assets/emoji/4596-froggy-arrow.png" width="24px" height="24px" alt="froggy_arrow"> This is made in **Discord.JS V13** and if you want to use this in V12 then you would have to do changes.

<img src="https://emoji.gg/assets/emoji/4596-froggy-arrow.png" width="24px" height="24px" alt="froggy_arrow"> Recommended NodeJS V16+.

<img src="https://emoji.gg/assets/emoji/4596-froggy-arrow.png" width="24px" height="24px" alt="froggy_arrow"> `message.channel.sendEmbed()` is just a additional function to make it easier to send embeds quickly. You can still use the default `message.channel.send()` like normally you do.

<img src="https://emoji.gg/assets/emoji/4596-froggy-arrow.png" width="24px" height="24px" alt="froggy_arrow"> SlashCommands are auto deployed and you don't have to run any code to create them manually. But you have to run the delete code from discord.js docs manually to delete them.

<img src="https://emoji.gg/assets/emoji/4596-froggy-arrow.png" width="24px" height="24px" alt="froggy_arrow"> Global SlashCommands only update per hour. It is recommended to first make a guild command for testing as guild commands are updated immediately and then make them a global command.

<img src="https://emoji.gg/assets/emoji/4596-froggy-arrow.png" width="24px" height="24px" alt="froggy_arrow"> If you want to change the `ready` event then remember to use these to get the values.
```js
const info = require(HOME + "/Home/Classes/Handler")
info.Handler.loadSlashCommands(client) // Required to be in ready event.
client.commands.size
client.aliases.size
client.events.size
client.buttonCommands.size
client.selectMenus.size
info.slashCount.length
```

# 『 Setup / Configuration 』
<img src="https://emoji.gg/assets/emoji/9266_arrow_rainbow.gif" width="18px" height="18px" alt="arrow_rainbow"> Install the required modules in the `package.json` file using the command `npm i`.<br>
<img src="https://emoji.gg/assets/emoji/9266_arrow_rainbow.gif" width="18px" height="18px" alt="arrow_rainbow"> Fill / Edit the contents of either `config.json` or `.env`.<br>
<img src="https://emoji.gg/assets/emoji/9266_arrow_rainbow.gif" width="18px" height="18px" alt="arrow_rainbow"> Make sure you have read the `Important Notes` sector.<br>

# 『 Examples 』
## Normal Command
```js
module.exports = {
    name : 'ping', // Name of command
    aliases: ["pp", "e"], // Aliases. Optional
    // Check below for avaliable optional options that can be used here.
    run : async(client, message, args, Discord) => {
    	// Your code here.
    }
}      
```

## Events
### Client Event
```js
module.exports = {
	name: 'messageDelete', // Name of event that is executed.
	once: true, // Execute event only once. Default: False.
	run: async(client, message) => { // Your event args.) {
		// Event Code
	},
};
```

### Non Client Event
```js
module.exports = {
	custom: true,
	run: async(client) => {
		client.distube.on("error", (message, error) => {
		console.error(error)
            })
		},
};
```

## Button Commands
```js
module.exports = {
    name : 'evalbtn', // Must be same as button's Custom Id
    // Check below for avaliable optional options that can be used he
    run : async(client, interaction, Discord) => {
interaction.reply("yo")
    }
}     
```

## SelectMenu Commands
```js
module.exports = {
    name : 'fun', // Should be same as Menu Custom Id or The menu options set values.
    // Check below for avaliable optional options that can be used he
    run : async(client, interaction, Discord) => {
    	interaction.reply("e")
    }
}     
```

## SlashCommands
```js
module.exports = {
    name : 'fun', // Name of the slash command.
    aliases: ["meow"], // Multiple Aliases. Optional.
    guild: "GuildID" or ["GuildID", "GuildID"], // Makes this command a guild command in these guilds. // Optional
    description: "A fun command :)", // Description of slash command. Optional
    type: "CHAT_INPUT", // Type of / command. Optional
    options: [{
      name: 'Are you having fun?',
      description: 'Choose true / false.',
      required: true,
      type: "BOOLEAN",
    }], // Options for / command. Optional
    // Check below for avaliable optional options that can be used he
    run : async(client, interaction, Discord) => {
    	interaction.reply("pog")
    }
}     
```

# 『 Avaliable Options for all commands and interactions. 』
`ownerOnly: true / false`
* Default: `false`. 
* When true, The command will only be runnable by the bot owner.

`authorOnly: true / false` 
* **Only for button commands**
* Default: `false`
* When true, Only the person who ran the command which had the buttons will be able to interact with them.

`expireAfter: Time in ms`
* **Only for button and selectmenu commands**
* Default: `None`
* The buttons / selectmenu will be disabled after this time has passed.
For SelectMenu use, Refer to `Home/CMDFiles/SelectMenus/select.js`

`cooldown: Time in ms`
* Default: `0`.
* Sets up a global user cooldown for the command for the provided time limit.

`userPermissions: ["SEND_MESSAGES" . . .]`
* Default: `None`.
* The user of the command must have all of the provided permissions to be able to run the command. **Permission(s) names must be in full capital**.

`clientPermissions: ["SEND_MESSAGES" . . .]`
* Default: `None`.
* The client must have all of the provided permissions to be able to run the command. **Permission(s) names must be in full capital**.

`anyUserPermissions: ["SEND_MESSAGES" . . .]`
* Default: `None`.
* The user of the command must any one of the provided permissions to be able to run the command. **Permission(s) names must be in full capital**.

`anyClientPermissions: ["SEND_MESSAGES" . . .]`
* Default: `None`.
* The client must any one of the provided permissions to be able to run the command. **Permission(s) names must be in full capital**.

`guildOnly: true / false`
* Default: `true`.
* When false, The command will be able to be run in DMs as well.

`allowBots: true / false`
* Default: `false`.
* When true, Bots will also be able to run the command.

`onlyUsers: ["User ID", "User ID" . . .]`
* Default: `None`
* Only the provided user IDs will be able to run the command.

`onlyRoles: ["Role ID", "Role ID" . . .]`
* Default: `None`
* Only the users with one of the provided roles will be able to run the command.

`onlyChannels: ["Channel ID", "Channel ID" . . .]`
* Default: `None`
* The command will only be able to be run in the provided channels.

`onlyGuilds: ["Server ID", "Server ID" . . .]`
* Default: `None`
* The command will only be able to be run in the provided guilds.

# Return Errors Options
These are a part of the above options. You can choose which option should give the error and which option shouldn't.

`returnNoErrors: true / false`
* Default: `false`
* When true, None of the errors usually sent by the options above will be sent. Basically it is like having all the options below as `false`.

`returnCooldownError: true / false`
* Default: `true`
* When false, The error message sent by the `cooldown handler` will not be sent.

`returnOwnerOnlyError: true / false`
* Default: `true`
* When false, The error message sent by the `ownerOnly handler` will not be sent.

`returnUserPermissionsError: true / false`
* Default: `true`
* When false, The error message sent by the `userPermissions handler` will not be sent.

`returnClientPermissionsError: true / false`
* Default: `true`
* When false, The error message sent by the `clientPermissions handler` will not be sent.

`returnAnyUserPermissionsError: true / false`
* Default: `true`
* When false, The error message sent by the `anyUserPermissions handler` will not be sent.

`returnAnyClientPermissionsError: true / false`
* Default: `true`
* When false, The error message sent by the `anyClientPermissions handler` will not be sent.

`returnOnlyUsersError: true / false`
* Default: `true`
* When false, The error message sent by the `onlyUsers handler` will not be sent.

`returnOnlyRolesError: true / false`
* Default: `true`
* When false, The error message sent by the `onlyRoles handler` will not be sent.

`returnOnlyChannelsError: true / false`
* Default: `true`
* When false, The error message sent by the `onlyChannels handler` will not be sent.

`returnOnlyGuildsError: true / false`
* Default: `true`
* When false, The error message sent by the `onlyGuilds handler` will not be sent.

# 『 Contribution 』
If you want to contribute towards this repository then follow these steps.
* Fork this Repository.
* Edit your fork and save the changes you want to make.
* Open the pull request.
* We will check out the code and if it is fine then your PR will be merged.
