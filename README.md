# Raspberry Pi Radio — Streaming with LiquidSoap + DarkIce + Ogg Vorbis

This is a small, self-hosted internet radio station I built using a Raspberry Pi 5. It uses [LiquidSoap](https://www.liquidsoap.info/) to manage audio playback and [DarkIce](http://www.darkice.org/) to stream it out in Ogg Vorbis format. You can listen using VLC or any media player that supports `.ogg` streams.

<p align="center">
  <img src="assets/IceCast%20Diagram.png" alt="System diagram of Raspberry Pi radio setup" width="50%" />
</p>

## Setup Notes

- **Raspberry Pi 5**  
  I originally installed the official active cooler, but I managed to mess up the fan header. So now it runs passively — no fan, completely silent. Turns out that's been working just fine. Temps stay stable, and honestly, I prefer the quiet.

- **LiquidSoap** handles the audio pipeline — playlists, fallback tracks, transitions
- **DarkIce** handles encoding and pushes the stream to Icecast
- The audio is streamed as **Ogg Vorbis**
- I use **VLC** or other open media players to listen

Everything is headless. Once the Pi boots, it starts streaming automatically.

## Why Ogg?

I went with Ogg Vorbis instead of something like MP3 or AAC because it’s open, efficient, and just sounds better at lower bitrates. It’s supported pretty much everywhere *except* iOS and Safari.

Apple still doesn’t support `.ogg` natively — not because they can’t, but because they won’t. It’s one of those frustrating platform decisions that makes life harder for no good reason. I’m not really interested in compromising stream quality or using worse formats just to chase compatibility.

If you’re trying to listen on an iPhone and it doesn’t work, that’s why.

## How to Listen

1. Open VLC (or any player that supports network streams)
2. Go to *Media > Open Network Stream*
3. Paste in the stream URL: http://radio.isaacpeterklein.com/radio.ogg

*p.s. - if you have the VLC iOS app, this also works in CarPlay!*
