# Nightcord

Nightcord is a simple, helpful and easy-to-use package that retrieves information from specific websites.

```npm i nightcord```

## Get started

To install nightcord on your own project, use `npm i nightcord`

Define Nightcord:

```js
const Nightcord = require('nightcord');
```

You are now ready to use Nightcord, view the functions below.

Functions:

[YouTube](/nightcord/youtube)
[Discord](/nightcord/discord)
[Games](/nightcord/games)

Output:

```
Unknown Brain - Faceless (ft. Marvin Divine & Bri Tolani) [NCS Lyrics]
Unknown Brain - Jungle of Love (ft. Glaceo) [NCS Lyrics]
Unknown Brain - Candy (ft. Linn Sandin) [NCS Lyrics]
Unknown Brain - Blackhole (ft. Ava King) [NCS Lyrics]
Unknown Brain - Blackhole (ft. Ava King) [NCS Lyrics]
Unknown Brain - DEAD (ft. KAZHI) [NCS Lyrics]
Unknown Brain - Oh Darling [NCS Lyrics]
Unknown Brain - Dancing On The Moon ft. Luke Burr [NCS Lyrics]
Unknown Brain - Hollywood Perfect (ft. NotEvenTanner) [NCS Lyrics]
Unknown Brain - Forget You (ft. Shiah Maisel) [NCS Lyrics]
Unknown Brain - Dance With Me (ft. Alexis Donn) [NCS Lyrics]
Unknown Brain - Let You Go (ft. NotEvenTanner) [NCS Lyrics]
Unknown Brain & Kyle Reynolds - I'm Sorry Mom [NCS Lyrics]
Unknown Brain - Childhood Dreams [NCS Lyrics]
Unknown Brain - Don't Bother (ft. Emily J) [NCS Lyrics]
Unknown Brain - Last Thing (ft. Charlotte Sands) [NCS Lyrics]
Unknown Brain & Hoober - Phenomenon (ft. Dax & VinDon) [NCS Lyrics]
```

`list` has the following properties:

```js
{
    title: "Playlist Title",
    id: "Playlist ID",
    url: "Playlist Link",
    videosCount: "Amount of videos in this playlist",
    viewCount: "Amount of views altogether from the videos in this playlist",
    createdDate: "Date of when the playlist was created",
    videos: "Display all videos on this playlist and information in JSON.",
    thumbnail: "Playlist Thumbnail Link",
    author: {
        name: "Playlist's channel name",
        channelURL: "Playlist's channel URL"
    }
}
```

## Discord

#### Discord Bot - Autopost stats to Discord Bot List (also known as top.gg)
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

### Discord - Send Webhook messages & embed

#### Message:

```js
const Nightcord = require('nightcord');
const webhook = new Nightcord.Webhook("Your Discord Webhook URL");

webhook.send("Hey! This is a webhook message.");
```

Output:

![](https://cdn.discordapp.com/attachments/882169401594486796/882176875118592071/unknown.png)

#### Embed:

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

### Games

Setup

```js
const Nightcord = require('nightcord');
const games = new Nightcord.Games();
```

Number Generator:

```js
const Nightcord = require('nightcord');
const games = new Nightcord.Games();

console.log(games.generateNumber(`5`, `10`);
```

Output will be a random number ranging from 5 to 10. 2 numbers (`generateNumber('first number', 'second number')`) are needed, Nightcord will randomly pick a number.
Join our [support server](https://discord.gg/W88aEhEbbq) for help on this package.
