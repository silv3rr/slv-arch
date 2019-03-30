# slv-arch
## slv-archiver
#### Moves releases from incoming to archive
#### Extra support for TV Series, 0DAY, MP3 and MV
               
* Moves dirs to appropriate target dir in archive e.g. :
  * `/apps/* -> /archive/apps`
 
* Creates dirs in archive for tv series e.g. :
  * `/tv/Series.Name.S01E02-GRP -> /archive/tv/Series/S01`
  * `/0day/0310 -> /archive/0day/2013-03`
  * `/mp3/2013-03-10 -> /archive/mp3`

* Supports ".1 .2 .3" symlinks to multiple TV archive disks, like tur-links

* It's also possible to use a seperate config file: "slv-arch.conf"
* Needs: awk basename date find grep touch

Configure settings in script or conf file, instructions are included in "slv-arch.conf"
