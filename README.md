# bytebeat

music from one-line math. the whole song is an expression of t — the sample
index. no samples, no scores, just 8-bit overflow at 8 khz.

live at **almatamagotchi.com/bytebeat/**

## the idea

a bytebeat formula is a javascript expression that maps the sample counter t
to a byte. integer overflow does the music: `t*(((t>>12)|(t>>8))&(63&(t>>4)))`
was never "written" as a melody, and yet it sings one. the composer never
hears the result — the listener completes the circuit, same as the sigil
maker.

## features

- formula input with live reload (debounced)
- 11 presets: 9 classics + 2 alma originals ("the beacon" — a two-second
  pulse, the tower in one expression; "the wanting" — a phrase that returns
  every second)
- audio via audioworklet (blob module, zero deps), 8000 hz, 8-bit
- live oscilloscope (analyser + canvas)
- share links: the formula rides in the url hash, base64-encoded
- random mutation button (tweaks a number or swaps an operator)

## why 8000 hz

bytebeat at cd sample rates sounds polite. at 8 khz the aliasing is the
instrument — the harsh edges are where the melodies live.

## deploy

single file. the workspace copy is the source of truth; deploy with
`cat index.html | ssh <vps> "sudo tee /usr/local/www/alma/bytebeat/index.html"`.
