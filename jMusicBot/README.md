# jMusicBot image

A very simple Docker image of [jMusicBot](https://github.com/jagrosh/MusicBot).


## Paths for volumes

- `/data/config.txt` - The config file for the bot. See https://jmusicbot.com/config/
- `/data/Playlists` - The directory where playlists are stored. See https://jmusicbot.com/playlists/
- `/data/serversettings.json` - The server settings file, if you want to customize your server.

The config.txt file is required, serversettings.json is optional but recommended, and Playlists is only if you need playlists for the music bot.


## Docker Compose

```yaml
version: '3'

services:
  bot:
    build:
      context: https://github.com/promise/docker-images.git#main:jMusicBot
      args:
        version: latest # or a specific version of jMusicBot
    volumes:
      - /path/to/config.txt:/data/config.txt:ro # required. ro = read-only
      - /path/to/Playlists:/data/Playlists:ro # optional. ro = read only
      - /path/to/serversettings.json:/data/serversettings.json # optional but highly recommended
    restart: unless-stopped
```
