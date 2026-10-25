# Shogo Kajiyama (kajisho5)

**Video / Audio / Streaming Engineer** — SEVENTHWELL, Japan
Building tools for real-world event production. **AI × FFmpeg × Automation**

I build agent skills and production software: tools that let AI coding agents (Claude Code, Cursor, Codex) do real media work — measuring first, editing deterministically, and verifying the result before calling it done. By day I run video/audio/streaming on live event floors; the software below comes from that work.

---

## Flagship

### [ffmpeg-skill](https://github.com/kajisho5/ffmpeg-skill) — ★2,700+ · 200+ forks
A local video editor for coding agents: **42 typed FFmpeg tools** with a machine-readable contract and a contract-derived MCP server. The workflow is fixed — **probe → edit → check → verify** — so the agent never guesses frame rates, codecs or container limits.

- Cut, join, silence removal, aspect fitting, captions & word-timed karaoke, overlays, motion graphics
- HDR10 / HLG / Dolby Vision → SDR, 3D LUTs and primary grading
- Audio cleanup, typed dynamics, EBU R128 two-pass loudness, multicam sync with drift correction
- Delivery checks against YouTube / Shorts / Reels / TikTok / X / LinkedIn specs, with fixes
- Project rendering from a declarative file, folder-wide batch with content-hash caching
- No API keys, no cloud, Python standard library only · Install: `npx ffmpeg-skill`
- 50 days on GitHub Trending (peak #46) · Reviewed by tech media in China, Italy and Japan (note)

---

## Agent skills for media production

Each skill is a self-contained package with a machine-readable contract, a `doctor` capability check, and verification built in. They compose: most execute through ffmpeg-skill.

- **[video-editing-skill](https://github.com/kajisho5/video-editing-skill)** — Executes typed video-edit requests (`video-editing/request@1`) deterministically via ffmpeg-skill and validates the output against the request.
- **[remotion-ffmpeg-skill](https://github.com/kajisho5/remotion-ffmpeg-skill)** — Renders measured Remotion motion graphics onto real recordings via ffmpeg-skill; every step verified before the next.
- **[motion-graphics-skill](https://github.com/kajisho5/motion-graphics-skill)** — Deterministic motion-graphics rendering onto video: lower thirds, picture-in-picture, chroma key, timeline validation.
- **[subtitle-skill](https://github.com/kajisho5/subtitle-skill)** — Generates SRT/WebVTT subtitles deterministically and burns them into video, with font, outline and placement control.
- **[transcription-skill](https://github.com/kajisho5/transcription-skill)** — Local speech-to-text with faster-whisper; validated transcripts with a defined hand-off format for editing skills.
- **[color-grading-skill](https://github.com/kajisho5/color-grading-skill)** — Typed colour-grading operations executed via ffmpeg-skill, capability-checked against the local FFmpeg build.
- **[audio-production-skill](https://github.com/kajisho5/audio-production-skill)** — Executes typed audio operation graphs (cleanup, dynamics, mixing, loudness) via ffmpeg-skill.
- **[media-analysis-skill](https://github.com/kajisho5/media-analysis-skill)** — Measures media files locally with ffprobe/ffmpeg and returns structured observations other skills can plan on.
- **[thumbnail-skill](https://github.com/kajisho5/thumbnail-skill)** — Renders typed thumbnail documents into validated PNG/JPEG images.
- **[imagemagick-skill](https://github.com/kajisho5/imagemagick-skill)** — Local, non-destructive image editing for coding agents with ImageMagick, plus an MCP interface. HEIC/WebP aware.
- **[hyperframes-skill](https://github.com/kajisho5/hyperframes-skill)** — Renders HTML scenes to verified video via HyperFrames and ffmpeg.
- **[blender-skill](https://github.com/kajisho5/blender-skill)** — Headless Blender pipeline for agents: inspect, convert, optimize and render 3D assets locally.
- **[qc-skill](https://github.com/kajisho5/qc-skill)** — Deterministic QC of video, audio, subtitle and delivery artifacts against typed rules.
- **[artifacts-skill](https://github.com/kajisho5/artifacts-skill)** — Locally verifies AI-generated documents and produces evidence-backed receipts.

### Orchestration
- **[AI-video-production-OS](https://github.com/kajisho5/AI-video-production-OS)** — Open contracts and shared infrastructure for AI-native video production across independent skills.
- **[video-production-agent](https://github.com/kajisho5/video-production-agent)** — Orchestrator that plans media work and executes it through ffmpeg-skill and the skill family.

### Design
- **[design-check-skill](https://github.com/kajisho5/design-check-skill)** — Audit-only: checks Apple app screens and specs against HIG checklists (iPhone / iPad / Mac) in an audit loop until gaps close. It audits; it does not generate designs.

---

## Released software

### Event production (from the floor, for the floor)
- **[paddock](https://github.com/kajisho5/paddock)** — Conference reception system: monitors NAS speaker folders read-only, manages reception intake, delivers materials to venues. Used at real academic conferences.
- **Remain monitors** — read-only remaining-playback-time monitors with a browser UI: [disguise](https://github.com/kajisho5/disguise-remain-monitor), [QLab](https://github.com/kajisho5/qlab-remain-monitor), [PIXERA](https://github.com/kajisho5/pixera-remain-monitor), [Grass Valley T2/T3](https://github.com/kajisho5/grassvalley-remain-monitor), [ProVideoPlayer](https://github.com/kajisho5/provideoplayer-remain-monitor)
- **[conductor](https://github.com/kajisho5/conductor)** — Button-deck show control from iPad/iPhone: video switchers, media servers, Stream Deck ([drivers](https://github.com/kajisho5/conductor-drivers)).
- **[crosspoint](https://github.com/kajisho5/crosspoint)** — iOS remote for Roland V-160HD / V-80HD video switchers over LAN, USB or Bluetooth MIDI.
- **[timer](https://github.com/kajisho5/timer)** — Event countdown timer for Windows: separate display and control windows, Rust core.
- **[sw-ars](https://github.com/kajisho5/sw-ars)** — Realtime audience polling and quizzes for live venues (PULSE), with add-ons for Slides / PowerPoint / Zoom / Teams.

### Audio
- **[voicebooth](https://github.com/kajisho5/voicebooth)** — Small vocal DAW for song covers: sing over an off-vocal track, check pitch against the guide, export WAV. Free download (Windows / Mac).
- **[sw-audio](https://github.com/kajisho5/sw-audio)** — 132 SEVENTHWELL audio plugins as CLAP, with VST3 and AU builds.
- **[model_600](https://github.com/kajisho5/model_600)** — Auto-mixing audio suite for OBS Studio: five units for voice, calls, game audio, music and master.

### Disc authoring (pure Python, no external tools)
- **[bdmvkit](https://github.com/kajisho5/bdmvkit)** — Blu-ray (BDMV) authoring: titles, chapters, menus, subtitles.
- **[vtskit](https://github.com/kajisho5/vtskit)** — DVD-Video authoring: writes VIDEO_TS discs with titles, menus, subtitles.
- **[udfkit](https://github.com/kajisho5/udfkit)** — UDF writer for DVD-Video and Blu-ray disc images.
- **[dvdcc](https://github.com/kajisho5/dvdcc)** — Embeds line-21 closed captions (CEA-608) into DVD MPEG-2 video without re-encoding.
- **[oncemore](https://github.com/kajisho5/oncemore)** — Mac app that turns videos into DVD/Blu-ray disc images with menus, chapters and subtitles.

### Apps & utilities
- **[fresnel](https://github.com/kajisho5/fresnel)** — Liquid Glass icon composer for layered iOS / macOS / watchOS app icons.
- **[iOS_atena](https://github.com/kajisho5/iOS_atena)** — Ad-free iPhone/iPad app that prints Japanese addresses on postcards and envelopes; all data stays on-device.
- **[iOS_QR_reader](https://github.com/kajisho5/iOS_QR_reader)** — Ad-free QR/barcode reader and creator for iOS/iPadOS, entirely on-device.
- **[zippeek](https://github.com/kajisho5/zippeek)** — Mac app to compress, extract, and peek inside archives without extracting them.

---

## Principles
- **Measure, don't guess** — probe the actual file before deciding anything
- **Verify before "done"** — every workflow ends with a check, not a claim
- **Names match what the thing actually does** — no over-broad claims

## Links
- Web: [seventh-well.com](https://seventh-well.com/)
- X: [@kebura_P](https://x.com/kebura_P)
- LinkedIn: [in/seventhwell](https://www.linkedin.com/in/seventhwell)
