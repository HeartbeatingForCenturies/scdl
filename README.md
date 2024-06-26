# Soundcloud Music Downloader
## Description

This script is able to download music from SoundCloud and set id3tag to the downloaded music.
Compatible with Windows, OS X, Linux.


## System requirements

* python3
* ffmpeg
* pip

# Installation Instructions
```
pip install git+https://github.com/HeartbeatingForCenturies/scdl
```

### Update
 `pip install git+https://github.com/HeartbeatingForCenturies/scdl --upgrade`

## Configuration
There is a configuration file left in `~/.config/scdl/scdl.cfg`

When typing arguments that take a value, use `=` to separate.
Example Configuration:
```
[scdl]
auth_token =
path = {MusicFolder}
download_archive = my/folder/for/music/downloaded.txt

[arguments]
args = --original-art --addtofile --flac -t -c
```

## Examples:
```
# Download track & repost of the user QUANTA
scdl -l https://soundcloud.com/quanta-uk -a

# Download likes of the user Blastoyz
scdl -l https://soundcloud.com/kobiblastoyz -f

# Download one track
scdl -l https://soundcloud.com/jumpstreetpsy/low-extender

# Download one playlist
scdl -l https://soundcloud.com/pandadub/sets/the-lost-ship

# Download only new tracks from a playlist
scdl -l https://soundcloud.com/pandadub/sets/the-lost-ship --download-archive archive.txt -c

# Sync playlist
scdl -l https://soundcloud.com/pandadub/sets/the-lost-ship --sync archive.txt

# Download your likes (with authentification token)
scdl me -f
```

## Options:
```
    -h --help                   Show this screen
    --version                   Show version
    me                          Use the user profile from the auth_token
    -l [url]                    URL can be track/playlist/user
    -s                          Download the stream of a user (token needed)
    -a                          Download all tracks of user (including reposts)
    -t                          Download all uploads of a user (no reposts)
    -f                          Download all favorites of a user
    -C                          Download all commented by a user
    -p                          Download all playlists of a user
    -m                          Download all liked and owned playlists of user
    -c                          Continue if a downloaded file already exists
    -o [offset]                 Begin with a custom offset
    --addtimestamp              Add track creation timestamp to filename, which allows for chronological sorting
    --addtofile                 Add artist to filename if missing
    --debug                     Set log level to DEBUG
    --download-archive [file]   Keep track of track IDs in an archive file, and skip already-downloaded files
    --error                     Set log level to ERROR
    --extract-artist            Set artist tag from title instead of username
    --hide-progress             Hide the wget progress bar
    --hidewarnings              Hide Warnings. (use with precaution)
    --max-size [max-size]       Skip tracks larger than size (k/m/g)
    --min-size [min-size]       Skip tracks smaller than size (k/m/g)
    --no-playlist-folder        Download playlist tracks into main directory, instead of making a playlist subfolder
    --onlymp3                   Download only the streamable mp3 file, even if track has a Downloadable file
    --path [path]               Use a custom path for downloaded files
    --remove                    Remove any files not downloaded from execution
    --flac			Convert original files to .flac
    --no-album-tag		On some players tracks get the same cover art if it is from the same album, this prevents it
    --original-art              Downloads the original artwork from the soundcloud CDN
```


## Features
* Automatically detect the type of link provided
* Download all songs from a user
* Download all songs and reposts from a user
* Download all songs from one playlist
* Download all songs from all playlists from a user
* Download all songs from a user's favorites
* Download only new tracks from a list (playlist, favorites, etc.)
* Sync Playlist
* Set the tags with mutagen (Title / Artist / Album / Artwork)
* Create playlist files when downloading a playlist


## License

[GPL v2](https://www.gnu.org/licenses/gpl-2.0.txt), original author [flyingrub](https://github.com/flyingrub)
