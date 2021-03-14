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
// Up to 10 options.

let msg = await message.channel.send(`Loading, one moment please.`),
    collector = await menu.run(msg, { filter: (react, user) => user.id === message.author.id }),
    choice = await collector.selection;
if(!choice) return msg.edit(`You didn't provide a choice?`);

// returns a number.
// 0-9
if(choice === 1) return msg.edit(`You've selected option 1!`); 
// Only include 
// , { filter: (react, user) => user.id === message.author.id }
// If you want it to be locked to the message author. 
```