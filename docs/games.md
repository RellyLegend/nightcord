# Games

## Setup

```js
const Nightcord = require('nightcord');
const games = new Nightcord.Games();
```

### Number Generator:

```js
const Nightcord = require('nightcord');
const games = new Nightcord.Games();

console.log(games.generateNumber(`5`, `10`);
```

Output will be a random number ranging from 5 to 10. 2 numbers (`generateNumber('first number', 'second number')`) are needed, Nightcord will randomly pick a number.

### Get Minecraft Player Stats

```js
const Nightcord = require('nightcord');
const games = new Nightcord.Games();
const minecraft = games.Minecraft;

minecraft.getPlayer('Relly2K').then(player => console.log(player.name));
```

Output:

```
Relly2K
```

`player` has the following properties:

```js
{
  name: "Player name",
  UUID: "Player UUID",
  textures: "Player textures"
  
}
