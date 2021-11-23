# slv-archiver

## Move releases from incoming to archive

Includes extra support for TV Series, 0DAY, MP3 and MV sections

- Moves dirs to appropriate target dir in archive:

    `/apps/* -> /archive/apps`

- Creates dirs in archive for tv series:

    `/tv/Series.Name.S01E02-GRP -> /archive/tv/Series/S01`

- Handles daydirs:

    `/0day/0310 -> /archive/0day/2013-03`

    `/mp3/2013-03-10 -> /archive/mp3`

Other features:

- Checks diskspace before moving
- Move releases that are x days old or oldest x dirs
- Use regular expressions to match releases
- Supports ".1 .2 .3" symlinks to multiple TV archive disks, like tur-links

## Installation

_Required: awk basename date find grep touch ls* (linux)_

1. Copy slv-arch.sh and conf file to /glftpd/bin
2. Configure settings in conf file (**recommended**) or in script iself
3. Follow instructions included in "slv-arch.conf"

### Testing

To test settings run `./slv-arch.sh debug`

This does not actually mkdir and mv but only shows what actions the script would have executed.

### Scheduling

If all works fine you should setup a daily crontab such as:

`15 2 * * *      /glftpd/bin/slv-arch.sh >/dev/null 2>&1`

Or, alternatively create a [systemd timer](https://www.freedesktop.org/software/systemd/man/systemd.timer.html) instead.
