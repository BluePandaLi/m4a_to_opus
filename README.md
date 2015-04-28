# m4a\_to\_opus converter

An user friendly frontend for avconv and avprobe to transcode audio to
vorbis or opus using the bitrate of the source material by
default.

The distinguishing feature is it only transcodes if the source material is
in AAC, so it can be played from more devices.

Also provides a more conventient output (percent finished and ETA
instead of current position in seconds).

It was originally made to work with
[youtube-dl](https://rg3.github.io/youtube-dl/), but also serves well as
standalone program.
