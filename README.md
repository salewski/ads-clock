# ads-clock

The `ads-clock` program allows you to use your terminal as a clock.

Got a laptop that you plug into a much larger display? Rather than close the
lid on the laptop or otherwise abandon it while working on the larger display,
throw an `ads-clock` on that bad boy.

Stupid, I know...

Here's an animated GIF (created from a screencast in an xterm stretched across
most of the screen) on my 3200x1800 laptop display:

![screenshot of ads-clock](/doc/video/ads-clock-screencast-001.gif)

Depending on the screen on which you are viewing the above animated image, you
may or may not be able to see the tiny text typed at the console at the
beginning of the loop. It is just the `ads-clock` command invoked with no
arguments. The end of the loop shows quitting out of the clock by hitting
`CTRL-C` (which sends a `SIGINT` to the `ads-clock` program).
