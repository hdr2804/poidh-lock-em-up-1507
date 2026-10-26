# PROCESS — how this remix was built

## 1. Reference study

Both videos linked from the bounty brief were watched in full before any production:

- **Original (2:40)** — POV fisherman confronted by a bald, moustached grandpa in a blue-green plaid shirt, seated in a white GMC truck by a pond. The fisherman claims written permission from Trey Taylor (Crew Tractor). The comedy is repetition and escalation: “state property” vs private land, the name Trey repeated as a shield, “hit the road, dude”, and the climax — the grandpa reveals “I’m his daddy!” and quotes Trey: “Lock them up.”
- **Example remix (0:26)** — the grandpa’s face composited onto a ceremonial guard on a London bus. It stops after the opening beats: the reveal and the title line never arrive.
- The one rival claim visible during production (claim 9092) was a static slideshow with a young Balaji sketch and crawl text — no scene, no dialogue arc.

Concept chosen from that study: keep the **whole arc** (setup → escalation → reveal → title line), cast Balajiss as an elderly grandpa in the same truck/pond setup, and add exactly one twist at the end instead of pasting crypto jokes over the scene.

## 2. Script (16 lines, all original performances)

| # | Speaker | Line |
|---|---|---|
| 1 | Fisherman | I’ve got written permission from Trey Taylor. |
| 2 | Grandpa | Who said you could fish here? |
| 3 | Fisherman | I thought this was state property. |
| 4 | Grandpa | State property? Did you say STATE? This land’s been private since before your fishing app finished loading. |
| 5 | Fisherman | Trey Taylor gave me the permission. He works over at Crew Tractor. |
| 6 | Grandpa | You keep saying Trey like that name is a smart contract. |
| 7 | Fisherman | Then call him. Check for yourself. |
| 8 | Grandpa | Oh, I’ll check, all right. But first… hit the road, dude. |
| 9 | Fisherman | I’m not moving till Trey says so. |
| 10 | Grandpa | Trey? Son… I’m his daddy. |
| 11 | Grandpa | Trey, it’s your daddy. Got some boys fishing my pond again. |
| 12 | Trey (phone) | Lock ’em up. |
| 13 | Grandpa | You heard the man. |
| 14 | Grandpa | And son, I don’t call the cops. I deploy them. |
| 15 | Fisherman | Wait. Did you just file me… on-chain? |
| 16 | Grandpa | Lock ’em up. Settled on Base. |

Lines 1–13 follow the original’s beats (permission claim, state-property argument, name repetition, the reveal, the phone call). Lines 14–16 are the added twist.

## 3. Visuals

- Three AI-generated base stills at 1152×2048: Grandpa in the truck (stern), Grandpa holding a smartphone (sly), and a fisherman POV. The phone still and master still carry the scene; the POV still was not used as a main shot because its truck came out red instead of white.
- The grandpa stills were generated from a generic elderly-man master, then identity-edited against a public photograph of Balaji Srinivasan so the aged face keeps his brow, nose, ears and jaw.
- Crops (wide / mid / face) were derived per line so cuts land on dialogue beats; each shot gets a slow sinusoidal drift in ffmpeg — no AI video generation.
- Graphics built in code: title banner (“BALAJISS AS GRANDPA”), the “TRESPASS CLAIM FILED — Status: CONFIRMED · Network: Base · Jurisdiction: forked.” popup, comic jail bars for the “filed on-chain” beat, and the end card.

## 4. Audio

- All 16 lines synthesised (three voices: Fisherman, Grandpa, Trey). The long line 4 is split across two shots at its midpoint for a mid-rant cut.
- Trey’s line runs through a phone EQ (high-pass 320 Hz / low-pass 3.3 kHz).
- Ring and confirmation chimes are generated sine tones.
- Per-segment 30 ms fades at every cut; final mix loudness-normalised to −14 LUFS, true peak −1 dB.

## 5. Assembly & QC

- Per-segment render (still + drift + captions burned in last) → concat → loudnorm → faststart MP4, 1080×1920, 30 fps, CRF 18.
- QC: ffprobe stream/duration check, frame grabs at segment midpoints and cut points (caption legibility, no broken frames), integrated loudness measurement.

## 6. Honest limitations

- No source footage or source audio is embedded: YouTube’s download path was bot-gated in the production environment, so this is a re-enacted remix of the reference’s scene and script beats, not a re-edit of the original file.
- Motion is ffmpeg drift over stills, not filmed or AI-generated video.
- The aged Balajiss likeness is an AI interpretation from a public photo, guided by the brief’s casting (“Balajiss as Grandpa”).
