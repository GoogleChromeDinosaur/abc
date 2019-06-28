| anyoneCanAdjust | Boolean | Whether anyone can adjust volume. | false |
| ownerOverMember | Boolean | Whether the owner over-rides `CanAdjust` and `CanSkip`. | false |
| anyoneCanLeave | Boolean | Whether anyone can make the bot leave the currently connected channel. | false |
| ownerID | String | The ID of the Discord user to be seen as the owner. Required if using `ownerOverMember`. | NaN |
| logging | Boolean | Some extra none needed logging (such as caught errors that didn't crash the bot, etc). | true |
| requesterName | Boolean | Whether or not to display the username of the song requester. | true |
| inlineEmbeds | Boolean | Whether or not to make embed fields inline (help command and some fields are excluded). | false |
| musicPresence | Boolean | Whether or not to make the bot set its presence to currently playing music. | false |
| clearPresence | Boolean | Whether or not to clear the presence instead of setting it to "nothing" | false |
| insertMusic | Boolean | Whether or not to insert the music bot data into `<Client>.music` on start. | false |
| channelWhitelist | Object/Array | Sets a list of ID's allow when running messages. | [ ] |
| channelBlacklist | Object/Array | Sets a list of ID's ignore when running messages. | [ ] |
| bitRate | String | Sets the preferred bitRate for the Discord.js stream to use. | "120000" |
| nextPresence | [PresenceData](https://discord.js.org/#/docs/main/stable/typedef/PresenceData) | PresenceData to set after instead of clearing it (clearPresence). | null |

## Multi-Prefix Option Example
```js
<Client>.guilds.forEach
<Music>.start(<Client>, {
  youtubeKey: "Data Key",
  botPrefix: <MapObject>
});

// Exmaple Map Structure
{serverID: { prefix: "!" } }
```
See [examples](https://github.com/DarkoPendragon/discord.js-musicbot-addon/blob/master/examples/examples.md) for more info.
## Cooldown
| Option | Type | Description | Default |  
| --- | --- | --- | --- |
| cooldown | Object | The main cooldown object | |
| cooldown.enabled | Boolean | Whether or not cooldowns are enabled. | true |
| cooldown.timer | Number | Time in MS that cooldowns last. | 10000 |
| cooldown.exclude | Object/Array | Array of command names to exclude. Uses default names, not set names | ["volume","queue","pause","resume","np"] |  

## Command Options.  
Commands pass a bit different. Each command follows the same format as below. Valid commands are `play`, `remove`, `help`, `np`, `queue`, `volume`, `pause`, `resume`, `skip`, `clearqueue`, `loop`, `leave`.
```js
music.start(client, {
  <command>: {
    enabled: false,                    // True/False statement.
    alt: ["name1","name2","name3"],    // Array of alt names (aliases).
    help: "Help text.",                // String of help text.
    name: "play"                       // Name of the command.
    usage: "{{prefix}}play bad memes", // Usage text. {{prefix}} will insert the bots prefix.
    exclude: false                     // Excludes the command from the help command.
  }
});
```
