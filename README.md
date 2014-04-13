spotifyripper
=============

based on robbeofficial's work: 
a small player and ripper script for spotify (rips playlists to mp3 and includes ID3 tags) 

NOTE: stream ripping violates the ToS of libspotify, spotify and, possibly, local copyright laws. Don't do that.

usage
-----
    ./jbripper.py [username] [password] [spotify_url]

examples
--------
    "./jbripper.py user pass spotify:track:52xaypL0Kjzk0ngwv3oBPR" creates "Beat It.mp3" file
    "./jbripper.py user pass spotify:user:[user]:playlist:7HC9PMdSbwGBBn3EVTaCNx rips entire playlist

features
--------
* real-time VBR ripping from spotify PCM stream

* writes id3 tags (including album covers)

* creates files and directories based on the following structure artist/album/song.mp3

prerequisites:
--------------
* lame, python-dev and eyeD3 installed (via apt-get)

* libspotify (download at https://developer.spotify.com/technologies/libspotify/, install via included make.install). you may need other -dev packages, check make errors if they occur.

* pyspotify (sudo pip install -I pyspotify==1.11)

* spotify binary appkey (download at developer.spotify.com and copy to wd, requires premium!)


TODO
----
- [ ] check AndersTornkvist fork for sensible improvements
- [ ] skip exisiting track (avoid / completed tracks / completed = successful id3)
- [ ] detect if other spotify instance is interrupting
- [ ] add album supprt : spotify:album:1UnRYaeCev9JVKEHWBEgHe
- [ ] update to support pyspotify v2.x (breaks module calls)

