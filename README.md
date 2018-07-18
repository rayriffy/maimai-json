maimai-json
===========

[![CircleCI](https://circleci.com/gh/rayriffy/maimai-json.svg?style=svg)](https://circleci.com/gh/rayriffy/maimai-json)

maimai song list database in JSON format

Schema
------

### Category

Our JSON database will start with category table first and then the *data* will be inserted inside each category

```json
{
  "pops": [
    ...
  ],
  "nico": [
    ...
  ],
  "toho": [
    ...
  ],
  "sega": [
    ...
  ],
  "game": [
    ...
  ],
  "orig": [
    ...
  ]
}
```

| Name   | Category            |
| ------ | ------------------- |
| pops   | POPS & ANIME        |
| nico   | niconico & VOCALOID |
| toho   | TOUHOU Project      |
| sega   | SEGA                |
| game   | GAMES & VARIETY     |
| orig   | ORIGINAL & JOYPOLIS |

## Data

Our databse wil use following data structure

```json
{
  "name": {
    "en": "Tokyo Retro",
    "jp": "東京レトロ"
  },
  "artist": {
    "en": "Scop",
    "jp": "すこっぷ"
  },
  "image_url": "https://maimai.sega.jp/assets/maiSongList/jacket/620_mms_tokyo_retro.jpg",
  "version": "MURASAKi+",
  "bpm": 126,
  "level": {
    "easy": "1",
    "basic": "4",
    "advanced": "6",
    "expert": "8",
    "master": "10",
    "remaster": null
  },
  "regionlocked": 0
}
```

| Name               | Description                                                                                                                        | Data Type   | Required    | Remark          |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------- | ----------- | ----------- | --------------- |
| `name.en`          | Song name that show in English maimai machine [Japanese text is allowed if that song is region locked]                             | String      | YES         |                 |
| `name.jp`          | Song name that show in Japanese maimai machine                                                                                     | String      | YES         |                 |
| `artist.en`        | Artist name that show in English maimai machine [Japanese text is allowed if that song is region locked]                           | String      | YES         |                 |
| `artist.jp`        | Artist name that show in Japanese maimai machine                                                                                   | String      | YES         |                 |
| `image_url`        | URL of song thumbnail **must be HTTPS**. You can *copy image URL* from offlicial site [here](https://maimai.sega.jp/song/)         | String      | YES         |                 |
| `version`          | maimai version that song released (maimai, maimai+, GreeN, GreeN+, ORANGE, ORANGE+, PiNK, PiNK+, MURASAKi, MURASAKi+, MiLK, MiLK+) | String      | YES         |                 |
| `bpm`              | Song's bpm                                                                                                                         | Integer     | YES         |                 |
| `level.easy`       | Song's easy level                                                                                                                  | String      | YES         |                 |
| `level.basic`      | Song's basic level                                                                                                                 | String      | YES         |                 |
| `level.advanced`   | Song's advanced level                                                                                                              | String      | YES         |                 |
| `level.expert`     | Song's expert level                                                                                                                | String      | YES         |                 |
| `level.master`     | Song's master level                                                                                                                | String      | YES         |                 |
| `level.remaster`   | Song's Re-master level                                                                                                             | String      | NO          | Default: null   |
| `listen.youtube`   | YouTube URL for listening this song                                                                                                | String      | YES         |                 |
| `listen.niconico`  | niconico URL for listening this song                                                                                               | String      | NO          |                 |
| `regionlocked`     | Is this song region locked?                                                                                                        | Boolean     | YES         | Default: 0      |
