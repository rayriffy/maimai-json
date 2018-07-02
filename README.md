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
  "name_en": "Tokyo Retro",
  "name_jp": "東京レトロ",
  "artist_en": "Scop",
  "artist_jp": "すこっぷ",
  "image_url": "https://maimai.sega.jp/assets/maiSongList/jacket/620_mms_tokyo_retro.jpg",
  "version": "MURASAKi+",
  "bpm": 126,
  "level_easy": "1",
  "level_basic": "4",
  "level_advanced": "6",
  "level_expert": "8",
  "level_master": "10",
  "level_remaster": null,
  "listen_youtube": "https://www.youtube.com/watch?v=17WsZ2J1f9s",
  "listen_niconico": "http://www.niconico.jp/watch/sm21113426",
  "regionlocked": 0
}
```

| Name             | Description                                                                                                                        | Data Type   | Required    | Remark          |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ----------- | ----------- | --------------- |
| name_en          | Song name that show in English maimai machine [Japanese text is allowed if that song is region locked]                             | String      | YES         |                 |
| name_jp          | Song name that show in Japanese maimai machine                                                                                     | String      | YES         |                 |
| artist_en        | Artist name that show in English maimai machine [Japanese text is allowed if that song is region locked]                           | String      | YES         |                 |
| artist_jp        | Artist name that show in Japanese maimai machine                                                                                   | String      | YES         |                 |
| image_url        | URL of song thumbnail **must be HTTPS**. You can *copy image URL* from offlicial site [here](https://maimai.sega.jp/song/)         | String      | YES         |                 |
| version          | maimai version that song released (maimai, maimai+, GreeN, GreeN+, ORANGE, ORANGE+, PiNK, PiNK+, MURASAKi, MURASAKi+, MiLK, MiLK+) | String      | YES         |                 |
| bpm              | Song's bpm                                                                                                                         | Integer     | YES         |                 |
| level_easy       | Song's easy level                                                                                                                  | String      | YES         |                 |
| level_basic      | Song's basic level                                                                                                                 | String      | YES         |                 |
| level_advanced   | Song's advanced level                                                                                                              | String      | YES         |                 |
| level_expert     | Song's expert level                                                                                                                | String      | YES         |                 |
| level_master     | Song's master level                                                                                                                | String      | YES         |                 |
| level_remaster   | Song's Re-master level                                                                                                             | String      | NO          | Default: null   |
| listen_youtube   | YouTube URL for listening this song                                                                                                | String      | YES         |                 |
| listen_niconico  | niconico URL for listening this song                                                                                               | String      | NO          |                 |
| regionlocked     | Is this song region locked?                                                                                                        | Boolean     | YES         | Default: 0      |