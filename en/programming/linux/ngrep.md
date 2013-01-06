# ngrep

For Web traffic you almost always want the -W byline option, which preserves linebreaks, and -q is a useful argument which suppresses some additional output about non-matching packets. Specify -d dev to force to listen to the dev interface.

Here’s an example that captures all packets that contain GET or POST:
```
ngrep -q -W byline -d en1 "^(GET|POST) .*"
```