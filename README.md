# m4a\_to\_opus converter

An user friendly front end for avconv and avprobe to transcode audio to
ogg/vorbis or ogg/opus using the bitrate of the source material.

The distinguishing feature is it only transcodes if the source material
is in AAC, so it can be played from more devices. It also provides a
more convenient output (“percent finished” and ETA instead “current
position in seconds”).

~~m4a\_to\_opus is suitable for use with
[youtube-dl](https://rg3.github.io/youtube-dl/), but also serves well as
a standalone program.~~
Update: As it turned out most youtube content is lossy low-quality sound,
transcoded to high bitrate AAC. Another transcoding step is no good unless
you want an extremely low bitrate and don't care about bad quality. In that
case use [youtube-podcast](https://github.com/gregor-b/youtube-podcast).

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

positional arguments:
  path               Path to the input file.

optional arguments:
  -h, --help         show this help message and exit
  -o O               Output path, default is source file path
                         with appropriately replaced extension.
  -d                 Delete orginal file after conversion.
  -y                 Overwrite output file if it already exists.
  -f                 Always transcode, don't check source extension.
  --bitrate BITRATE  Desired bitrate limit in kbit/s, silently superseeds the
                         BITRATE variable.
  --vorbis           Transcode to vorbis instead of opus.
```
