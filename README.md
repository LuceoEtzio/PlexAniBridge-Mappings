# PlexAniBridge Mappings

Last generated at: February 28, 2025 08:28 AM UTC

This is an autogenerated list for mapping AniList IDs to AniDB IDs, MyAnimeList IDs, TVDb IDs, and IMDb IDs for use with [PlexAniBridge](https://github.com/eliasbenb/PlexAniBridge).

This list is generated daily at 12:00 AM UTC

## Format

You can view the schema for the mappings in [mappings.schema.json](./mappings.schema.json), and below is an example mapping entry you would find in [mappings.json](./mappings.json):

```json
{
  "98310": {
    "anidb_id": 12820,
    "mal_id": [
      34915,
      36186,
      36529
    ],
    "tvdb_id": 333234,
    "tvdb_mappings": {
      "s0": "e1",
      "s1": "e1-e13"
    }
  }
}
```

- **Key**: The primary key is the AniList ID of the show/movie. The key should be a string representation of the integer ID.
- `anidb_id`: The matching AniDB ID for the entry. Currently, unused by PlexAniBridge, but may be used in the future.
- `imdb_id`: The matching IMDb ID(s) for the entry. Can be a single ID or an array of IDs. Currently only used by PlexAniBridge for movies, but may be used for shows in the future.
- `mal_id`: The matching MyAnimeList ID for the entry. Currently only used by PlexAniBridge for shows, but may be used for movies in the future.
- `tmdb_movie_id`: The matching TMDB ID(s) for the movie entry. Can be a single ID or an array of IDs.
- `tmdb_show_id`: The matching TMDB ID(s) for the show entry. Can be a single ID or an array of IDs.
- `tvdb_id`: The matching TVDB ID for the show entry.
- `tvdb_mappings`: A dictionary mapping TVDB seasons to episode patterns. Keys are in the format "sX" where X is the season number (e.g., "s1" for season 1). Values are strings that define episode mappings in the following formats:
  - All episodes: `""` maps all episodes in the season with a 1:1 mapping
  - Single episode: `"e5"` maps to just episode 5
  - Episode range: `"e1-e13"` maps episodes 1 through 13
  - Open-ended range: `"e3-"` maps all episodes starting from episode 3
  - Episode ratio (+): `"e1-e12|2"` maps episodes with a 2:1 ratio (two TVDB eisodes to one AniList episode)
  - Episode ratio (-): `"e1-e12|-2"` maps episodes with a 1:2 ratio (one TVDB episode to two AniList episodes)
  - Multiple ranges: `"e1-e12,e14-e24"` maps multiple, non-contiguous episode ranges

## Sources

The mappings are generated using data from the following sources:

1. [Anime-Lists/anime-lists](https://github.com/Anime-Lists/anime-lists/) maps AniDB IDs to TVDD series IDs and IMDb IDs. ([Raw List](https://raw.githubusercontent.com/Anime-Lists/anime-lists/master/anime-list-master.xml))
2. [manami-project/anime-offline-database](https://github.com/manami-project/anime-offline-database/) maps AniDB IDs to MyAnimeList IDs and AniList IDs. ([Raw List](https://raw.githubusercontent.com/manami-project/anime-offline-database/master/anime-offline-database.json))
3. [notseteve/AnimeAggregations](https://github.com/notseteve/AnimeAggregations) parses data from the AniDB site and maps the links there to TMDB IDs, IMDb IDs, and MyAnimeList IDs.

Much of the code in this repo was copied from or inspired by [Kometa-Team/Anime-IDs](https://github.com/Kometa-Team/Anime-IDs).
