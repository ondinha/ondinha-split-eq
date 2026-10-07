# Ondinha Split EQ

**Transient / tonal split EQ: separate gain for the attack and the sustain in every band. Lift the snare crack without making cymbals harsher.**

A VST3 and Audio Unit plug-in from [Ondinha](https://github.com/ondinha), a DAW 2.0: native AI tools combined with traditional sound engineering tools.

An EQ that hears the difference between a hit and a held note. It splits your audio into a **transient** layer (attacks, clicks, noise bursts) and a **tonal** layer (sustained, pitched sound), and every band has its own gain for each.

So you can add 4 kHz to the kick and snare attack without the vocal or the cymbal wash getting brighter, or open up the air on the tonal part of a master while the hats stay where they are.

Comes with its own window: a spectrum with both layers and draggable bands.

## What it's good for

- Master: more kick punch in the lows (transient only), more air up top (tonal only).
- Drums: bring the stick attack forward without boosting the room ring.
- Make a wide mix tighter: narrow the transient layer, keep the tonal layer wide.

## Controls

| Control | Range | What it does |
|---|---|---|
| 6 bands | low shelf, 4 bells, high shelf | Each with freq, Q / slope, **transient gain** and **tonal gain** (+-18 dB). |
| Split | -12 to +12 dB | Moves the line between what counts as transient and tonal. |
| Separation | 0-100 % | How strictly the two layers are separated. |
| Transient / Tonal level | -36 to +12 dB | Level of each layer. |
| Transient / Tonal width | 0-200 % | Stereo width of each layer. |
| Output | +-18 dB |  |

## Presets

Built in as host programs (your DAW's preset menu):

- Master: punch low, tonal air

## Download and install

Builds will be on the [Releases](../../releases) page.

**macOS:** copy `Ondinha Split EQ.vst3` to `~/Library/Audio/Plug-Ins/VST3` and `Ondinha Split EQ.component` to `~/Library/Audio/Plug-Ins/Components`, then rescan plug-ins in your DAW.

| Format | Platform |
|---|---|
| VST3 | macOS |
| Audio Unit (AU) | macOS |

Works in any VST3 or AU host: Ableton Live, Logic Pro, Reaper, Bitwig Studio, Cubase, Studio One, FL Studio and others.

## How it works

Harmonic / percussive separation (after Fitzgerald, 2010) on an STFT: per bin, the median over ~110 ms is the tonal level and the median across frequency of each bin's rise above it is the transient level; a soft mask divides the two. Masks come from both channels together, so the stereo image stays put, and they sum to one: **with every band flat, the layers add back to the input exactly**. The EQ curves are matched to analog (no cramping near Nyquist). Latency is about 96 ms at 48 kHz, reported to the host.

## More Ondinha plug-ins

- [Ondinha Bus Comp](https://github.com/ondinha/ondinha-bus-comp): Console-style glue compressor for the mix bus and groups.
- [Ondinha Limiter](https://github.com/ondinha/ondinha-limiter): True-peak brickwall limiter for mastering, with an optional oversampled clipper.
- [Ondinha Unmask](https://github.com/ondinha/ondinha-unmask): Spectral side-chain ducking: dips a track only at the frequencies where the key is loud, only while it plays.
- [Ondinha Resonance](https://github.com/ondinha/ondinha-resonance): Dynamic resonance tamer for harsh mixes, vocals and guitars: pulls down narrow peaks only while they ring and leaves the broad tone alone.
- [Ondinha Imager](https://github.com/ondinha/ondinha-imager): Multiband stereo imager with mono low end: width for lows, mids and highs on phase-matched Linkwitz-Riley crossovers.
- [Ondinha Delay](https://github.com/ondinha/ondinha-delay): Tempo-synced stereo / ping-pong delay with filtered, saturated feedback and ducking, so the echoes stay out of the way of the vocal.
- [Ondinha Graphic EQ](https://github.com/ondinha/ondinha-graphic-eq): 10-band octave graphic EQ with analog-matched bells (31 Hz - 16 kHz, +-12 dB).
- [Ondinha Tube Air](https://github.com/ondinha/ondinha-tube-air): High-frequency exciter with a tube stage: adds warm even or bright odd harmonics above a frequency, under the untouched signal.

## Feedback

Found a bug or a host where it misbehaves? [Open an issue](../../issues) with your DAW, its version and your OS.
