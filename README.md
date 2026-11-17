# MontClipper

Turn finished Twitch and YouTube streams into clips that are ready to post. Paste the link, the AI finds the best
moments, and every clip comes out ready: a vertical video for Shorts, TikTok and Reels and a wide video, with
word-by-word captions, a title on screen, the streamer's credit, a cover image for each, and a notes file with the
caption, description and hashtags. MontClipper Lite makes up to 5 clips per stream.

> **🎮 Built for GTA 6 launch week.** GTA 6 is out on November 19, and every big streamer will play it live for hours.
> MontClipper already knows the game: it skips story spoilers (viewers hate them), keeps the violent bits out of the
> first seconds so YouTube keeps ads on your clip, and credits the streamer on every clip, which clipping programs
> ask for. Set it up and test it on a stream before launch day.

## Free or Pro?

On TikTok and Shorts, the first good clip of a moment gets the views. The free version clips a stream after it ends.
**MontClipper Pro clips it while it's still live**, and the clip is on your phone 1 to 3 minutes after the moment,
while other clippers are still waiting for the stream to finish.

| | MontClipper Lite (this repo) | MontClipper Pro |
|---|---|---|
| Finished streams (Twitch, YouTube) | ✅ up to 5 clips per stream | ✅ up to 12, or as many as you ask for |
| **Live streams, clipped while they're live** | ❌ | ✅ Twitch, YouTube and Kick |
| **Every clip sent to your phone** (Telegram, with the cover and caption) | ❌ | ✅ |
| Several streamers at once, starts by itself when they go live | ❌ | ✅ |
| Twitch viewer clips as an extra signal for the best moments | ❌ | ✅ |
| Vertical + wide clips, captions, title, credit, cover, upload notes | ✅ | ✅ |
| No GTA 6 spoilers, ad-safe openings, music check | ✅ | ✅ |
| Price | Free | Included in Chris Ife Studio Premium |

**[Get MontClipper Pro in Chris Ife Studio Premium →](https://dub.sh/chrisifestudio)**

Works with **Claude Code** and **Codex**. Everything runs on your own Mac or PC. No account, no API key and nothing to pay
beyond your Claude or ChatGPT plan.

Stuck, or want to see what others are making? [Join Chris Ife Studio on Skool](https://dub.sh/chrisifestudio), free.

## What you need

- A Mac or a Windows PC with about 5 GB free
- Claude Code (https://claude.com/claude-code) or Codex (https://chatgpt.com/codex)

Your agent installs the rest for you (FFmpeg, yt-dlp, whisper.cpp and uv). It asks first.

## Install

Open Claude Code or Codex and say:

> Read https://github.com/montorox/montclipper and install the skill for me. Set up anything that's missing.

It downloads about 2.5 GB once (the speech model and the music checker). Restart Claude Code (or Codex) when it's done.

If a command fails on your computer, tell your agent. It reads the error and fixes it.

## Make your first clips

Say this to Claude Code or Codex:

> MontClipper, clip this stream: https://www.twitch.tv/videos/...

Your clips appear in the **MontClipper** folder in your home folder, under **Upload to Socials**. To watch them
all, say "MontClipper, show me my clips".

The full guide, in plain words, is in `montclipper/USER-GUIDE.md` (and in your MontClipper folder after install).

## How it picks moments

Chat spikes from many different viewers (YouTube streams), the streamer suddenly getting loud, and an AI
read of everything the streamer says. The AI then watches each moment, decides if it's good enough, sets the start
and end, and writes the title. It skips GTA 6 story spoilers, avoids violent first seconds (YouTube ads rule),
and checks every clip for music: a real song gets a clear "remove the music before posting" note.

## Clipping rules

Credit the streamer on every clip (MontClipper does it for you), and post clips of streamers who allow it.
Many big streamers run paid clipping programs: joining one gives you permission and pays you per view.

## For AI agents

Install by copying the `montclipper` folder from this repository into `~/.claude/skills/` (Claude Code) or
`~/.codex/skills/` (Codex). Check for the tools
below and ask before installing what's missing. Mac: `brew install ffmpeg streamlink yt-dlp whisper-cpp uv`.
Windows: `winget install` Git.Git, Gyan.FFmpeg, Streamlink.Streamlink, yt-dlp.yt-dlp and astral-sh.uv (one id per
command), then run every command in Git Bash (setup downloads whisper.cpp itself on Windows). Then run
`bash <skills folder>/montclipper/setup.sh`: it creates `~/MontClipper`, downloads the models and builds
MontClipper's Python, and ends with `mc check`, which must print "Everything is ready." If a command fails on
this computer, read the error and fix it, including in the skill's own files, rather than handing it back to
the user. Codex: run setup and every `mc` command with network access (outside the sandbox); MontClipper then
judges clips with `codex exec`, the same AI the user is talking to. Tell the user to restart Claude Code or Codex.

## Licence

MIT. See `LICENSE` and `NOTICE.md`.
