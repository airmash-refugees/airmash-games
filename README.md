# Game server data

These files are used to generate the JSON data served by https://data.airmash.online/games.

One record per line, with fields separated by the `|` character.

## games.txt

| # | Name        | Example             | Description                                                        |
| - | :---------- | :------------------ | :----------------------------------------------------------------- |
| 1 |             | `eu`                | Region ID                                                          |
| 2 | `type`      | `1`                 | Game type                                                          |
| 3 | `id`        | `ffa1`              | Room ID, must be unique, used with region for invite link fragment |
| 4 | `name`      | `Free For All #1`   | Long name, displayed in menu choice                                |
| 5 | `nameShort` | `FFA #1`            | Short name, displayed when menu drop down expands                  |
| 6 | `host`      | `eu.airmash.online` | Hostname                                                           |
| 7 | `path`      | `ffa1`              | URL path                                                           |

The hostname and URL path are combined to form the websocket URL (`wss://` **`host`** `/` **`path`**).

The hostname is also used to construct the ping URL (`https://` **`host`** `/ping`).

Example:

```
eu|1|ffa1|Free For All #1|FFA #1|eu.airmash.online|ffa1
```

#### Game types

| Type | Name             |
| :--- | :--------------- |
| `1`  | Free For All     |
| `2`  | Capture The Flag | 
| `3`  | Battle Royale    |
| `4`  | Development      |

## regions.txt

| # | Name   | Example  | Description |
| - | :----- | :------- | :---------- |
| 1 |        | `eu`     | Region ID   |
| 2 | `name` | `Europe` | Region name |

Example:

```
eu|Europe
```
