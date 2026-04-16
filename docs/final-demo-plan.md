# Streamdex Final Demo Plan

## Goal

Create a submission demo that stays under 2 minutes while proving three things quickly:

1. Streamdex turns trusted sources into short video briefings.
2. The system supports more than one briefing type.
3. The workflow can run repeatedly, not just as a one-off demo.

## Recommended Pipeline

Use the `hybrid` pipeline for the final submission demo.

Why `hybrid` is the right fit:

- The demo needs a mix of screen recording, product explanation, and sample output clips.
- `screen-demo` expects `transcriber` in its script stage, and the current environment has that tool unavailable.
- `hybrid` lets the screen recording stay primary while sample videos, captions, overlays, and stat cards act as support layers.
- Remotion is available, so we can use cleaner motion graphics and title cards instead of a plain stitched cut.

## Preflight Summary

Current capability envelope from the local registry:

| Capability | Configured |
|------------|------------|
| Analysis | 7/11 |
| Image generation | 4/9 |
| TTS | 2/4 |
| Video generation | 1/15 |
| Video post | 8/8 |
| Audio processing | 2/2 |
| Subtitles | 2/2 |
| Screen capture | 2/2 |
| Music generation | 0/2 |

Practical implications for the submission demo:

- Good to go for composition, trimming, subtitles, screen capture, and final assembly.
- Good enough for narration if we want it.
- Weak for generating new motion clips on demand, so the submission should lean on existing sample outputs instead of creating fresh showcase videos this late.
- No music generator is configured, so either use a user-provided royalty-free track or keep the cut clean without background music.

## Source Inventory

### Already available locally

- `assets/signal-from-tomorrow-demo.mp4` — 30.06s sample video
- `projects/demos/renders/code-to-screen.mp4` — 25.05s zero-key demo render
- `projects/demos/renders/world-in-numbers.mp4` — 23.06s zero-key demo render

### Still needed for final assembly

- Final screen recording of the Streamdex flow you want to show
- The exact sample briefing clips you want included in the final submission cut, if different from the local fallback clips above
- Optional royalty-free music track if you want background music

If those files are not ready yet, this document should still be enough to record and cut the final version quickly.

## Timing Strategy

Treat the 2-minute cap as a hard production constraint:

- Narrated shell: 70-80 seconds
- Sample videos: 30-40 seconds total
- Buffer: 5-10 seconds

Hard rules:

- Do not let sample clips exceed 45 seconds total.
- If you use 2 sample clips, keep each to 15-20 seconds.
- If you use 3 sample clips, use 8-12 second proof beats, not full plays.
- If a sample clip is especially strong, let it breathe and trim the intro or close instead of rushing the middle.

## Recommended 120-Second Structure

| Time | Duration | Segment | Notes |
|------|----------|---------|-------|
| 0:00-0:08 | 8s | Hook | "What if your tabs turned into a video briefing?" Keep this very fast. |
| 0:08-0:22 | 14s | Product setup | Show trusted inputs: news, docs, repos, calendars, broker data. |
| 0:22-0:38 | 16s | Streamdex flow | Show prompt or workflow that generates the briefing. |
| 0:38-0:56 | 18s | Sample clip A | Best proof of finished output quality. |
| 0:56-1:08 | 12s | Why it matters | Explain source-first ranking and video-first delivery. |
| 1:08-1:26 | 18s | Sample clip B | Pick a different use case from clip A. |
| 1:26-1:40 | 14s | Automation pass | Show recurring morning/evening briefing or scheduled flow. |
| 1:40-1:54 | 14s | Capability summary | Multi-source, recurring, portable workflow, evidence-backed. |
| 1:54-2:00 | 6s | Close | "Your sources. Your ranking. Your format. Your stream." |

## If You Want 3 Sample Videos

Use this alternate budget:

- Intro + setup: 30 seconds
- Sample clip A: 10 seconds
- Sample clip B: 10 seconds
- Sample clip C: 10 seconds
- Automation + capability summary: 45 seconds
- Close: 15 seconds

This version works only if the clips are already trimmed and visually distinct.

## Recommended Story Beats

Use this narrative order:

1. Problem: people are buried in tabs, feeds, dashboards, and docs.
2. Product: Streamdex turns trusted sources into a watchable briefing.
3. Proof: show 2 different sample outputs.
4. Repeatability: show automation or recurring run capability.
5. Positioning: this is a personal broadcast layer, not generic AI video generation.

## Voiceover Draft

### 0:00-0:22

"Most important information still lives across tabs, dashboards, docs, and feeds. Streamdex turns those trusted sources into short video briefings you can actually watch."

### 0:22-0:38

"You connect the inputs you care about, choose the kind of briefing you want, and Streamdex assembles a concise video from the signal instead of the noise."

### 0:38-0:56

No heavy narration. Let the first sample clip prove output quality.

### 0:56-1:08

"This can adapt to different workflows, from market updates to architecture recaps to end-of-day summaries."

### 1:08-1:26

Keep narration light again. Let the second sample clip carry the moment.

### 1:26-1:40

"It also works as a repeatable workflow, with recurring briefings scheduled through automations."

### 1:40-2:00

"So instead of depending on a feed to decide what matters, you build your own stream from the sources you trust. Your sources. Your ranking. Your format. Your stream."

## Sample Clip Selection Rules

Pick clips that prove different strengths:

- one clip should prove visual polish or finished-output quality
- one clip should prove a different use case or source mix
- a third clip, if used, should prove repeatability or breadth rather than style alone

Avoid choosing clips that all say the same thing visually.

## Best Current Proof Clips

If you need a safe fallback set right now, use:

1. `assets/signal-from-tomorrow-demo.mp4` for the strongest cinematic "wow" moment
2. `projects/demos/renders/code-to-screen.mp4` for the best developer-workflow proof
3. `projects/demos/renders/world-in-numbers.mp4` for clean chart and stat-card motion

Recommended trims:

- `signal-from-tomorrow-demo.mp4`: use a 15-16 second highlight, not the full 30 seconds
- `code-to-screen.mp4`: use 10-14 seconds
- `world-in-numbers.mp4`: use 8-12 seconds if you need a third proof beat

## Editing Notes

- Keep the screen recording visually primary in the product sections.
- Use overlays sparingly: source labels, one-line callouts, and one short capability card are enough.
- Reserve the cleanest visuals for the sample clips. Do not bury them under captions and boxes.
- If the interface is dense, stay in 16:9 for the hero cut instead of forcing a vertical crop.
- Keep subtitles high-contrast and out of the way of UI-heavy sections.

## Fast Assembly Checklist

Before cutting the final video, collect:

1. One clean screen recording of the Streamdex flow
2. Two or three already-trimmed sample videos
3. Optional music track
4. Final title card text
5. Final closing tagline

## Current Blockers

- The exact presenter-approved sample clip order is still unknown.
- The final screen recording for the Streamdex product walkthrough is still needed.
- No music generator is configured, so music must be supplied or skipped.

## Recommendation

The safest final-submission path is:

1. Build the demo around `hybrid`
2. Use 2 sample clips, not 3
3. Keep total sample footage at 36 seconds or less
4. Record one clean screen walkthrough
5. Ship a crisp 16:9 cut with optional captions and no dependency on new generation
