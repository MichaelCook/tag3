tag3
====

Edit the tags of MP3 files by applying arbitrary Perl expressions.

In the Perl expression:
    * $_ is the title, artist, album or genre to modify.
    * $FILE is the name of the MP3 file.
    * $MMSS is the duration in minutes and seconds.
    * $SECONDS is the duration in seconds.

Example:
    tag3 --title='s/^/Podcast: /' podcast*.mp3

Insert at the beginning of the title the string "MMDD", the month & day of
the last-modification time of each mp3 file.

    tag3 --title='($m,$d)=(localtime((stat$FILE)[9]))[4,3];s/^/sprintf"%02d%02d ",$m+1,$d/e' *.mp3
