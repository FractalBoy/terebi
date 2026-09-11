# Live TV API shape

The guide loads `GET /api/channels/channels/summary/`, all paginated results
from `GET /api/channels/logos/` and `GET /api/epg/epgdata/`, and
`GET /api/epg/grid/`. All requests use the saved bearer token.

Each summary channel joins to EPG data through `epg_data_id`. The matching EPG
data record supplies `tvg_id`, which joins to each grid program's `tvg_id`.
Logo records are indexed by `id` and their `cache_url` is used as artwork.

Selecting a channel plays `/proxy/ts/stream/<channel.uuid>?output_profile=1`.
