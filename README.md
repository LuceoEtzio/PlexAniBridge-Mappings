# PlexAniBridge Mappings

Last generated at: February 21, 2025 10:06 PM UTC

This is an autogenerated list for mapping AniList IDs to AniDB IDs, MyAnimeList IDs, TVDb IDs, and IMDb IDs for use with [PlexAniBridge](https://github.com/eliasbenb/PlexAniBridge).

This list is generated daily at 12:00 AM UTC

## Format

This is an example mapping entry you would find in the [mappings.json](https://raw.githubusercontent.com/Kometa-Team/Anime-IDs/master/anime_ids.json) file.

```json
{
  "21234": {
    "anidb_id": 11292,
    "imdb_id": "tt5249462",
    "mal_id": 31043,
    "tmdb_show_id": 65249,
    "tvdb_epoffset": 0,
    "tvdb_id": 303071,
    "tvdb_season": 1
  }
}
```

- The main key of each entry is the AniList ID of the entry.
- `anidb_id`: This should link directly to the exact same anime on [AniDB.net](https://anidb.net).
- `imdb_id`: This should be the IMDb ID of the Series for shows and seasons, but should link directly to the IMDb ID of the Movie or Special if it is one. The field can also be an array of IMDb IDs if the show has multiple entries.
- `mal_id`: This should link directly to the exact same anime on [MyAnimeList.net](https://myanimelist.net). The field can also be an array of MyAnimeList IDs if the Anime has multiple entries.
- `tmdb_movie_id`: This looks at the AniDB site under the resources for the anime.
- `tmdb_show_id`: This looks at the AniDB site under the resources for the anime.
- `tvdb_id`: This is always the Series ID that contains the show/season/movie/special. **This should never be a TVDb Movie ID or TVDb Season ID.**
- `tvdb_season`: This is the season number if the entry is a season.
- `tvdb_epoffset`: This is the episode offset if the entry is a season. An offset of 0 means the season starts at episode 1.

## Sources

The mappings are generated using data from the following sources:

1. [Anime-Lists/anime-lists](https://github.com/Anime-Lists/anime-lists/) maps AniDB IDs to TVDb Series IDs and IMDb IDs. ([Raw List](https://raw.githubusercontent.com/Anime-Lists/anime-lists/master/anime-list-master.xml))
2. [manami-project/anime-offline-database](https://github.com/manami-project/anime-offline-database/) maps AniDB IDs to MyAnimeList IDs and AniList IDs. ([Raw List](https://raw.githubusercontent.com/manami-project/anime-offline-database/master/anime-offline-database.json))
3. [notseteve/AnimeAggregations](https://github.com/notseteve/AnimeAggregations) parses data from the AniDB site and maps the links there to TMDb IDs, IMDb IDs, and MyAnimeList IDs.

Much of the code in this repo was copied from or inspired by [Kometa-Team/Anime-IDs](https://github.com/Kometa-Team/Anime-IDs).
