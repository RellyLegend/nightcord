# Discord

## Discord Bot - Autopost stats to Discord Bot List (also known as top.gg)

```js
const Nightcord = require('nightcord');

const Discord = require('discord.js');
const client = new Discord.Client({ intents: [] }); // Put your bot's intents in [], like [Discord.Intents.FLAGS.GUILDS] or [Discord.Intents.FLAGS.GUILD_MESSAGES], or for both [Discord.Intents.FLAGS.GUILDS, Discord.Intents.FLAGS.GUILD_MESSAGES]

const config = {
    token: "Super secret bot token",
    dbl: "Super secret top.gg token"
};

const dbl = new Nightcord.DBL(config.dbl, client)

client.on('ready', () => {
    console.log(`${client.user.tag} is ready!`); // Send message on console when the bot is ready.
    dbl.autoPost.readyMessage('Stats posted!')
    dbl.autoPost(); // Autopost stats to Top.gg
});

client.login(config.token);
```

After deploying the code, wait a few seconds and in your console, there will be a message saying that the autopost was successful.

## Discord - Send Webhook messages & embed

### Message:

```js
const Nightcord = require('nightcord');
const webhook = new Nightcord.Webhook("Your Discord Webhook URL");

webhook.send("Hey! This is a webhook message.");
```

Output:

![](https://cdn.discordapp.com/attachments/882169401594486796/882176875118592071/unknown.png)

### Embed:

```js
const Nightcord = require('nightcord');
const webhook = new Nightcord.Webhook("Your Discord Webhook URL");
const { MessageEmbed } = require('discord.js');

const embed = new MessageEmbed()
.setDescription(`Hey! This is a webhook message posted with Nightcord!`)
.setColor(`BLURPLE`)
.setFooter(`Made with Nightcord`);

webhook.sendEmbed(embed);
```

Output:

![](https://cdn.discordapp.com/attachments/882169401594486796/882177852588572672/unknown.png)
