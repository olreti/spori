spori
=============
This is a small player and ripper script for spotify. It rips playlists to mp3 and includes ID3 tags.

It is largely based on both spotifyripper-projects by AndersTornkvis and robbeofficial respectively.
Please note that this is intended to be a learning project, i.e. improving python coding skills at a practical example. The code is likely to be a lot messier and clumsy than in the original versions. 
That does not mean, however, that I do not want to share the code. If you happen to find something useful here for your own project, then by all means, go ahead.

NOTE: stream ripping violates the ToS of libspotify, spotify and, possibly, local copyright laws. Don't do that.
Usage:
--------

    usage: jbripper [-h] -u USER -p PASSWORD -U URL [-l [LIBRARY]] [-O OUTPUTDIR]
                    [-P] [-V VBR] [-I] [-f | -d]
    
    Rip Spotify songs
    
    optional arguments:
      -h, --help            show this help message and exit
      -u USER, --user USER  spotify user
      -p PASSWORD, --password PASSWORD
                            spotify password
      -U URL, --url URL     spotify url
      -l [LIBRARY], --library [LIBRARY]
                            music library path
      -O OUTPUTDIR, --outputdir OUTPUTDIR
                            music output dir (default is current working directory)
      -P, --playback        set if you want to listen to the tracks that are currently ripped (start with "padsp ./jbripper.py ..." if using pulse audio)
      -V VBR, --vbr VBR     Lame VBR quality setting. Equivalent to Lame -V parameter. Default 0
      -I, --ignoreerrors    Ignore encountered errors by skipping to next track in playlist
      -o, --oldtags         set to write ID3v2 tags version 2.3.0 instead of newer version 2.4.0
      -f, --file            Save output mp3 file with the following format: "Artist - Song - [ Album ].mp3" (default)
      -d, --directory       Save output mp3 to a directory with the following format: "Artist/Album/Song.mp3"
    
    Example usage:
            rip a single file: ./jbripper.py -u user -p password -U spotify:track:52xaypL0Kjzk0ngwv3oBPR
            rip entire playlist: ./jbripper.py -u user -p password -U spotify:user:username:playlist:4vkGNcsS8lRXj4q945NIA4
            check if file exists before ripping: ./jbripper.py -u user -p password -U spotify:track:52xaypL0Kjzk0ngwv3oBPR -l ~/Music
            

features
--------
* real-time VBR ripping from spotify PCM stream

* writes id3 tags (including album covers)

* creates files and directories based on the followng structure artist/album/song.mp3

* Check for existing songs


prerequisites:
--------------
* lame, python-dev and eyeD3 installed (via apt-get)

* libspotify (download at https://developer.spotify.com/technologies/libspotify/, install via included make.install). you may need other -dev packages, check make errors if they occur.

* pyspotify (sudo pip install -I pyspotify==1.11)

* a binary appkey by spotify (download at developer.spotify.com and copy to wd, requires premium!)


TODO
----
- [ ] check fork for sensible improvements
- [ ] skip exisiting track (avoid / completed tracks / completed = successful id3)
- [ ] detect if other spotify instance is interrupting
- [ ] add album supprt : spotify:album:1UnRYaeCev9JVKEHWBEgHe
- [ ] update to support pyspotify v2.x (breaks module calls)

