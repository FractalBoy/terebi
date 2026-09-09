# Recordings API shape

The DVR library consumes `GET /api/channels/recordings/` with a bearer token. Each item supplies `id`, `start_time`, `end_time`, and `custom_properties`.

The UI reads `custom_properties.poster_url` as an absolute poster image URL, `status` as `recording` or `completed`, `file_url` for playback, and `program.title`, `program.sub_title`, `program.description`, `program.start_time`, and `program.end_time` for poster and expanded details.
