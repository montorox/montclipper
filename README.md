# MontClipper

Turn finished Twitch and YouTube streams into clips that are ready to post. Paste the link, Claude finds the best
moments, and every clip comes out ready: a vertical video for Shorts, TikTok and Reels and a wide video, with
word-by-word captions, a title on screen, the streamer's credit, a cover image for each, and a notes file with the
caption, description and hashtags. MontClipper Lite makes up to 5 clips per stream.

**Want clips while the streamer is still live?** MontClipper Pro clips live streams 1 to 3 minutes after each
moment and sends every clip to your phone, so you post first. It's in
[Chris Ife Studio Premium](https://dub.sh/chrisifestudio).

Everything runs on your own Mac. No account, no API key and nothing to pay beyond your Claude plan.

Stuck, or want to see what others are making? [Join Chris Ife Studio on Skool](https://dub.sh/chrisifestudio).

## What you need

- A Mac or a Windows PC with about 5 GB free
- Claude Code: https://claude.com/claude-code
- Mac: Homebrew (https://brew.sh). Windows: Git for Windows, `winget install Git.Git`

Your agent installs the rest for you (FFmpeg, yt-dlp, whisper.cpp and uv). It asks first.

## Install

Open Claude Code and say:

> Read https://github.com/montorox/montclipper and install the skill for me. Set up anything that's missing.

It downloads about 2.5 GB once (the speech model and the music checker). Restart Claude Code when it's done.

If a command fails on your computer, tell your agent. It reads the error and fixes it.

### Windows, step by step

1. Open "Terminal" from the Start menu and paste these one at a time, then close and reopen Terminal:
   ```
   winget install Git.Git
   winget install Gyan.FFmpeg
   winget install Streamlink.Streamlink
   winget install yt-dlp.yt-dlp
   winget install astral-sh.uv
   ```
2. Open Claude Code and give it the install sentence above. It runs the setup in Git Bash.

## Make your first clips

Say this to Claude:

> MontClipper, clip this stream: https://www.twitch.tv/videos/...

Your clips appear in the **MontClipper** folder in your home folder, under **Upload to Socials**. To watch them
all, say "MontClipper, show me my clips".

The full guide, in plain words, is in `montclipper/USER-GUIDE.md` (and in your MontClipper folder after install).

## How it picks moments

Chat spikes from many different viewers (YouTube streams), the streamer suddenly getting loud, and a Claude
read of everything the streamer says. Claude then watches each moment, decides if it's good enough, sets the start
and end, and writes the title. It skips GTA 6 story spoilers, avoids violent first seconds (YouTube ads rule),
and checks every clip for music: a real song gets a clear "remove the music before posting" note.

## Clipping rules

Credit the streamer on every clip (MontClipper does it for you), and post clips of streamers who allow it.
Many big streamers run paid clipping programs: joining one gives you permission and pays you per view.

## For AI agents

Install by copying the `montclipper` folder from this repository into `~/.claude/skills/`. Check for the tools
below and ask before installing what's missing. Mac: `brew install ffmpeg streamlink yt-dlp whisper-cpp uv`.
Windows: `winget install` Git.Git, Gyan.FFmpeg, Streamlink.Streamlink, yt-dlp.yt-dlp and astral-sh.uv (one id per
command), then run every command in Git Bash (setup downloads whisper.cpp itself on Windows). Then run
`bash ~/.claude/skills/montclipper/setup.sh`: it creates `~/MontClipper`, downloads the models and builds
MontClipper's Python, and ends with `mc check`, which must print "Everything is ready." If a command fails on
this computer, read the error and fix it, including in the skill's own files, rather than handing it back to
the user. Tell the user to restart Claude Code.

## Licence

MIT. See `LICENSE` and `NOTICE.md`.
