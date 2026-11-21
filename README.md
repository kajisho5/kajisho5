# Shogo Kajiyama (kajisho5)

**Video / Audio / Streaming Engineer** — SEVENTHWELL, Japan
Building tools for real-world event production. **AI × FFmpeg × Automation**

I build agent skills and production software: tools that let AI coding agents (Claude Code, Cursor, Codex) do real media work — measuring first, editing deterministically, and verifying the result before calling it done. By day I run video/audio/streaming on live event floors; the software below comes from that work.

---

## Flagship

### [ffmpeg-skill](https://github.com/kajisho5/ffmpeg-skill) — ★5,200+ · 430+ forks
A local video editor for coding agents: **42 typed FFmpeg tools** with a machine-readable contract and a contract-derived MCP server. The workflow is fixed — **probe → edit → check → verify** — so the agent never guesses frame rates, codecs or container limits. Now at **v4**.

- Cut, join, silence removal, aspect fitting, captions & word-timed karaoke, overlays, motion graphics
- HDR10 / HLG / Dolby Vision → SDR, 3D LUTs and primary grading
- Audio cleanup, typed dynamics, EBU R128 two-pass loudness, multicam sync with drift correction
- Delivery checks against YouTube / Shorts / Reels / TikTok / X / LinkedIn specs, with fixes
- Project rendering from a declarative file, folder-wide batch with content-hash caching
- No API keys, no cloud, Python standard library only · One command on a new machine: `npx ffmpeg-skill setup`
- 50 days on GitHub Trending (peak #46) · Reviewed by tech media in China, Italy and Japan (note)

### [Velisa](https://github.com/kajisho5/Velisa) — Verified Execution Layer for Intent, Skills & Agents
An open foundation for AI-native video production — not another AI video generator. Open contracts, a capability registry, a one-command installer, a plugin marketplace and a dashboard that let independent Skills and Agents turn production intent into deterministic, verifiable changes. Formerly *AI Video Production OS*.

Today it is mostly architecture and contracts, not a running system — the Skills it coordinates are real, tested and released on their own: **33 components in 10 departments**.

---

## The Velisa ecosystem

Each Skill is a self-contained package with a machine-readable contract, a `doctor` capability check, and verification built in. Most execute through ffmpeg-skill.

**Command**
- **[video-production-agent](https://github.com/kajisho5/video-production-agent)** — Orchestrator: plans a production and calls the Skills below.

**Ingest**
- **[ingest-skill](https://github.com/kajisho5/ingest-skill)** — Media offload from cards, recorders and URLs with checksum-verified copies, dual backup and a clip inventory.

**Visual**
- **[video-editing-skill](https://github.com/kajisho5/video-editing-skill)** — Cut, trim, concat, fit; computes retake and duplicate candidates.
- **[color-grading-skill](https://github.com/kajisho5/color-grading-skill)** — Colour correction, LUT, HDR to SDR.
- **[motion-graphics-skill](https://github.com/kajisho5/motion-graphics-skill)** — Titles, lower thirds, logos, picture-in-picture and chroma key.
- **[subtitle-skill](https://github.com/kajisho5/subtitle-skill)** — Subtitle validation, SRT/WebVTT generation, burn-in and animated captions.
- **[thumbnail-skill](https://github.com/kajisho5/thumbnail-skill)** — Thumbnail rendering.
- **[remotion-ffmpeg-skill](https://github.com/kajisho5/remotion-ffmpeg-skill)** — Remotion motion graphics on real footage, timed from ffmpeg-skill measurements.
- **[hyperframes-skill](https://github.com/kajisho5/hyperframes-skill)** — Renders HTML scenes to verified video with HyperFrames.
- **[blender-skill](https://github.com/kajisho5/blender-skill)** — Headless Blender: inspect, convert, optimize and render 3D assets.

**Audio**
- **[audio-production-skill](https://github.com/kajisho5/audio-production-skill)** — Gain, mix, loudness normalization, dynamics, denoise, filler and silence removal.
- **[voice-enhance-skill](https://github.com/kajisho5/voice-enhance-skill)** — AI voice isolation, dereverberation and mic-bleed reduction for recorded speech.
- **[dubbing-skill](https://github.com/kajisho5/dubbing-skill)** — AI narration, voice replacement, fitting translated lines to source timing, audio description.
- **[sound-design-skill](https://github.com/kajisho5/sound-design-skill)** — BGM and sound-effect generation.

**Recognition**
- **[transcription-skill](https://github.com/kajisho5/transcription-skill)** — Speech to timestamped transcript (local faster-whisper).
- **[diarization-skill](https://github.com/kajisho5/diarization-skill)** — Speaker diarization for transcripts.
- **[detection-skill](https://github.com/kajisho5/detection-skill)** — Face, text (OCR) and object detection, and the frame-accurate shot table.
- **[slide-sync-skill](https://github.com/kajisho5/slide-sync-skill)** — Slide import, slide-change detection, slide text.

**Verification**
- **[qc-skill](https://github.com/kajisho5/qc-skill)** — Rule-based QC: PASS / WARN / FAIL / UNKNOWN against the plan or spec.
- **[media-analysis-skill](https://github.com/kajisho5/media-analysis-skill)** — Observation only: measures facts about a media file.
- **[artifacts-skill](https://github.com/kajisho5/artifacts-skill)** — Verifies AI-generated documents and issues evidence-backed receipts.

**Delivery**
- **[publish-skill](https://github.com/kajisho5/publish-skill)** — Upload and metadata for delivery platforms.
- **[nle-bridge-skill](https://github.com/kajisho5/nle-bridge-skill)** — Timeline interchange with Premiere Pro and DaVinci Resolve (OTIO / FCP7 XML / EDL), with round trip of the editor's changes.
- **Disc authoring, pure Python** — [bdmvkit](https://github.com/kajisho5/bdmvkit) (Blu-ray), [vtskit](https://github.com/kajisho5/vtskit) (DVD-Video), [udfkit](https://github.com/kajisho5/udfkit) (UDF images), [dvdcc](https://github.com/kajisho5/dvdcc) (CEA-608 captions without re-encoding), and [oncemore](https://github.com/kajisho5/oncemore), a Mac app that turns videos into disc images with menus, chapters and subtitles.

**Utility**
- **[imagemagick-skill](https://github.com/kajisho5/imagemagick-skill)** — Still-image editing with ImageMagick.
- **[stepcap](https://github.com/kajisho5/stepcap)** — Record a task once; get a how-to guide for people and a `SKILL.md` for agents.

**Governance**
- **[skillpact](https://github.com/kajisho5/skillpact)** — Machine-readable contracts for Agent Skills: declared side effects, conformance tests, signatures.
- **[system-intelligence](https://github.com/kajisho5/system-intelligence)** — Read-only auditing of repositories and multi-repository ecosystems.

---

## Skills and tools for working with agents

- **[assume-nothing](https://github.com/kajisho5/assume-nothing)** — Makes Claude Code, Cursor, Codex, Gemini CLI and OpenCode check the machine before acting and look things up before answering. A mechanism, not a request.
- **[first-try](https://github.com/kajisho5/first-try)** — Lets a model guess how to call a command-line tool, runs the guesses, and turns each miss into an answer the tool returns and a test that keeps it.
- **[skill-diet](https://github.com/kajisho5/skill-diet)** — Audits a skill, trims a copy, and proves the shorter one still behaves the same.
- **[choosing-models](https://github.com/kajisho5/choosing-models)** — Picks the Claude model and effort that fit a task, and says so honestly when the current model is not enough.
- **[github-solo-skill](https://github.com/kajisho5/github-solo-skill)** — Diagnoses and safely configures a solo developer's GitHub repository, free features only, with `restore`.
- **[slopscope](https://github.com/kajisho5/slopscope)** — Reports a page's visual audit (opinion) and its Chromium measurements (fact) separately, before and after a fix.
- **[hig-design-skill](https://github.com/kajisho5/hig-design-skill)** — Designs Apple-platform app screens that follow the Human Interface Guidelines, from spec to mockups.
- **[design-check-skill](https://github.com/kajisho5/design-check-skill)** — Audit-only: checks Apple app screens and specs against HIG checklists until the gaps close.
- **[japanese-medical-writing.skill](https://github.com/kajisho5/japanese-medical-writing.skill)** — Writing and pre-submission checks for Japanese-language medical papers, built to run with a local LLM.

---

## Released software

### Event production (from the floor, for the floor)
- **[paddock](https://github.com/kajisho5/paddock)** — Conference reception system: monitors NAS speaker folders read-only, manages reception intake, delivers materials to venues. Used at real academic conferences.
- **[trapdoor](https://github.com/kajisho5/trapdoor)** — Video playout for operators: cue list, A/B decks with the next cue already parked on its first frame, and a 16-button clip bank on one screen. Windows.
- **Remain monitors** — read-only remaining-playback-time monitors with a browser UI: [disguise](https://github.com/kajisho5/disguise-remain-monitor), [QLab](https://github.com/kajisho5/qlab-remain-monitor), [PIXERA](https://github.com/kajisho5/pixera-remain-monitor), [Grass Valley T2/T3](https://github.com/kajisho5/grassvalley-remain-monitor), [ProVideoPlayer](https://github.com/kajisho5/provideoplayer-remain-monitor)
- **[conductor](https://github.com/kajisho5/conductor)** — Button-deck show control from iPad/iPhone: video switchers, media servers, Stream Deck ([drivers](https://github.com/kajisho5/conductor-drivers)).
- **[crosspoint](https://github.com/kajisho5/crosspoint)** — iOS remote for Roland V-160HD / V-80HD video switchers over LAN, USB or Bluetooth MIDI.
- **[TwinKeys](https://github.com/kajisho5/ableton-twinkeys)** — Fires the same sound cue on a main Mac and a backup Mac at once, for show playback. Unofficial third-party tool.
- **[timer](https://github.com/kajisho5/timer)** — Event countdown timer for Windows: separate display and control windows, Rust core.
- **[sw-panel-loader](https://github.com/kajisho5/sw-panel-loader)** — Puts an image on a TURZX 8.8-inch panel so it shows at power-on, in one Windows screen.
- **PULSE** — Realtime audience polling and quizzes for live venues, with add-ons such as [Teams](https://github.com/kajisho5/sw-ars-for-teams).

### Audio
- **[voicebooth](https://github.com/kajisho5/voicebooth)** — Small vocal DAW for song covers: sing over an off-vocal track, check pitch against the guide, export WAV. Free download (Windows / Mac).
- **[sw-audio](https://github.com/kajisho5/sw-audio)** — 132 SEVENTHWELL audio plugins as CLAP, with VST3 and AU builds.
- **[model_600](https://github.com/kajisho5/model_600)** — Auto-mixing audio suite for OBS Studio: five units for voice, calls, game audio, music and master.

### Apps & utilities
- **[vaultsweep](https://github.com/kajisho5/vaultsweep)** — Diagnoses a 1Password vault, ranks risky passwords, and walks through changing them and closing unused accounts. Windows / Mac, unofficial.
- **[hushtv](https://github.com/kajisho5/hushtv)** — Switches off the ads, trackers and promo rows on Android TV and Google TV over Wi-Fi. Nothing uninstalled, every change undoable.
- **[fresnel](https://github.com/kajisho5/fresnel)** — Liquid Glass icon composer for layered iOS / macOS / watchOS app icons.
- **[zippeek](https://github.com/kajisho5/zippeek)** — Mac app to compress, extract, and peek inside archives without extracting them.
- **[KATA UI](https://github.com/kajisho5/KATA-UI)** — 137 components, 21 blocks and 7 templates from one set of design tokens. No framework, no build step.
- **[Claude Continuity](https://github.com/kajisho5/claude-continuity)** — Desktop app for continuing Claude conversations over the Anthropic API. Unofficial.

### Infrastructure
- **[runway](https://github.com/kajisho5/runway)** — Builds Apple apps on GitHub Actions and sends them to TestFlight, without owning a Mac.
- **[tower](https://github.com/kajisho5/tower)** — One repository that issues and rotates Cloudflare tokens and provisions KV / D1 / R2 / DNS for every app.

### In progress
- **[rustevo](https://github.com/kajisho5/rustevo)** — A Rust framework for apps that agents evolve: every change leaves a record that can be replayed.
- **[onchip](https://github.com/kajisho5/onchip)** — Research prototype: a GPU-resident video filter graph where frames never leave the chip. Not an FFmpeg replacement.
- **[genba-tokei](https://github.com/kajisho5/genba-tokei)** — A clock for the event floor on iPhone / iPad / Apple Watch, to 1/100 of a second.
- **[petacal](https://github.com/kajisho5/petacal)** — A calendar that keeps photos, spending and fan activities alongside the schedule.
- **[Skillwright](https://github.com/kajisho5/skillwright)** — An iPhone / iPad app for writing, checking and publishing `SKILL.md` / `CLAUDE.md` / `AGENTS.md`. Design phase.

---

## Principles
- **Measure, don't guess** — probe the actual file before deciding anything
- **Verify before "done"** — every workflow ends with a check, not a claim
- **Names match what the thing actually does** — no over-broad claims

## Links
- Web: [seventh-well.com](https://seventh-well.com/)
- X: [@kebura_P](https://x.com/kebura_P)
- LinkedIn: [in/seventhwell](https://www.linkedin.com/in/seventhwell)
