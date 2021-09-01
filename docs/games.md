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
