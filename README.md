# slv-arch
#### slv-archiver - Moves releases from incoming to archive
#### Includes extra support for TV Series, 0DAY, MP3 and MV

* Moves dirs to appropriate target dir in archive e.g. :
  * `/apps/* -> /archive/apps`

* Creates dirs in archive for tv series e.g. :
  * `/tv/Series.Name.S01E02-GRP -> /archive/tv/Series/S01`
  * `/0day/0310 -> /archive/0day/2013-03`
  * `/mp3/2013-03-10 -> /archive/mp3`

* Supports ".1 .2 .3" symlinks to multiple TV archive disks, like tur-links

* It's also possible to use a seperate config file: "slv-arch.conf"
* Needs: awk basename date find grep touch

## Installation

* Copy script and conf files to /glftpd/bin
* Configure settings in script or conf file
* Instructions are included in "slv-arch.conf"

Test by running: `./slv-arch.sh debug`

This does not actually mkdir and mv but just shows what actions the script would have executed instead.

## Crontab

If all works fine you should setup a daily crontab such as:

`15 2 * * *      /glftpd/bin/slv-arch.sh >/dev/null 2>&1`

