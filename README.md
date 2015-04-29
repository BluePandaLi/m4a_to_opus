# m4a\_to\_opus converter

An user friendly frontend for avconv and avprobe to transcode audio to
vorbis or opus using the bitrate of the source material by default.

The distinguishing feature is it only transcodes if the source material
is in AAC, so it can be played from more devices. It also provides a
more conventient output (percent finished and ETA instead of current
position in seconds).

m4a\_to\_opus is suitable for use with
[youtube-dl](https://rg3.github.io/youtube-dl/), but also serves well as
a standalone program.

```
$ m4a_to_opus -h
usage: m4a_to_opus [-h] [-o O] [-d] [-y] [-f] [--bitrate BITRATE] [--vorbis]
                   path

Transcodes given file to opus or vorbis, if it has an aac-like extension
(aac, 3gp, mp4, m4a, m4b, mpg).

By default the bitrate of the source material is used, but may be
limited by the --bitrate parameter or the BITRATE environment variable,
both in kbit/s.

If a given bitrate differs from source bitrate, -f (force transcoding)
is implied.

Usage with youtube-dl in a shell script:
    youtube-dl "$@" -x --exec "m4a_to_opus -d"

positional arguments:
  path               path to the input file

optional arguments:
  -h, --help         show this help message and exit
  -o O               output path, default is source file path with
                     appropriately replaced extension.
  -d                 delete orginal file after conversion
  -y                 overwrite output file if it already exists
  -f                 always transcode, don't check source extension
  --bitrate BITRATE  desired bitrate limit in kbit/s, silently superseeds the
                     BITRATE variable
  --vorbis           transcode to vorbis instead of opus
```
