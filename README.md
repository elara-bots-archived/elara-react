# Getting Started

### RichDisplay
```js
const { RichDisplay } = require("elara-react"),
      { MessageEmbed } = require("discord.js");

const menu = new RichDisplay(new MessageEmbed())

menu.addPage(embed => {
    embed.setTitle(`Title!`)
    return embed;
});

menu.run(await message.channel.send(`Loading, one moment please!`), { filter: (react, user) => user.id === message.author.id })

// Only include 
// , { filter: (react, user) => user.id === message.author.id }
// If you want it to be locked to the message author. 
```



### RichMenu
```js
const { RichMenu } = require("elara-react"),
      { MessageEmbed } = require("discord.js");

const menu = new RichMenu(new MessageEmbed())

menu.addOption(`Option 1`, `Description for the option`);
// Up to 9 options.

menu.run(await message.channel.send(`Loading, one moment please!`), { filter: (react, user) => user.id === message.author.id })

// Only include 
// , { filter: (react, user) => user.id === message.author.id }
// If you want it to be locked to the message author. 
```