# SubChordium

#### A Discord bot that browses and plays music from one or multiple Subsonic servers.

### Why the name SubChordium?

#### `Sub`sonic for the source medium. Dis`C`h`ord` for the target medium written with an h to make it more musical. And `ium` to make it sound like an element.

### Features

- Play music from one or multiple Subsonic servers.
- Search and queue system with pagination.
- Usual player controls: `Pause`, `Continue`, `Stop`, `Skip`, `Shuffle` via Discord [/commands](https://discord.com/developers/docs/interactions/application-commands).

### Prerequisites

- **Node.JS** (Guide on [nodejs.org](https://nodejs.org)) - _Tested versions: 18, 20 & 22_
- **Discord Bot** (Guide on [discord.com](https://discord.com/developers/docs/getting-started))
- **Subsonic Server** (Guide on [subsonic.org](https://www.subsonic.org/pages/help.jsp))

### Installation

1. Clone repository:

```shell
git clone https://github.com/zlyfer/subsonic-music-bot
```

2. Install packages:

```shell
npm install
```

3. Copy [`credentials.template.json`](credentials.template.json) to `credentials.json`.
4. [Insert](#credentialsjson) your credentials into `credentials.json`.
5. Copy [`config.template.json`](config.template.json) to `config.json`.
6. [Adjust](#configjson) the `config.json` to your needs.

### [credentials.json](credentials.json)

| name                           | type   | description                                                         |
| ------------------------------ | ------ | ------------------------------------------------------------------- |
| version                        | number | The version of the credentials file. Should not be edited manually. |
| [discord](#discord)   | object | The discord bot credentials.                                        |
| [subsonic](#subsonic) | array  | The subsonic server credentials.                                    |

#### discord

| name      | type   | description                |
| --------- | ------ | -------------------------- |
| token     | string | The discord bot token.     |
| client_id | string | The discord bot client id. |

#### subsonic

| name     | type   | default | description                          |
| -------- | ------ | ------- | ------------------------------------ |
| name     | string |         | The name of the subsonic server.     |
| protocol | string | http    | The protocol of the subsonic server. |
| host     | string |         | The host of the subsonic server.     |
| port     | string | 80      | The port of the subsonic server.     |
| username | string |         | The username of the subsonic server. |
| password | string |         | The password of the subsonic server. |

### [config.json](config.json)

| name           | type            | default | description                                                              |
| -------------- | --------------- | ------- | ------------------------------------------------------------------------ |
| volume         | number (0-1000) | 100     | The volume for the player.                                               |
| showProvider   | boolean         | true    | Whether to show the provider (subsonic server) of the song in the queue. |
| maxPageEntries | number          | 10      | The maximum number of entries per page.                                  |
| bufferTime     | number          | 3000    | The buffer time of the player. Only change if you experience issues.     |
