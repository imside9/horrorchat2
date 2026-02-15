# Horror Chat Story Blueprint v1.2

## 1) Concept
- Working title: `Room 404: Edit War`
- Format: messenger-style forensic horror
- Target playtime: 15-20 minutes
- Core pillars:
- Oppressive chat atmosphere without jump-scare media
- Timeline forensics instead of visual proof clips
- Meaningful multi-ending replay driven by player stance

## 2) Tone and Setting
- Independent canon (not a sequel to prior `horrorchat` story).
- Location: shutdown-bound boarding house management chat.
- Premise: the manager is missing, and the only surviving truth is fragmented system logs.
- Tone curve:
- Prologue/Act 1: ordinary dispute with subtle metadata mismatch
- Act 2-3: account conflict and edit-history panic
- Act 4-Final: self-authored manipulation revealed

## 3) Cast
- `Player`: filed the first missing-person report, now has memory gaps.
- `Seoyun`: resident representative, pushes fast accusation.
- `Taemin`: maintenance helper, early scapegoat.
- `Hana`: former intern who archived system logs before closure.

## 4) Season-1 Difference Audit (Hard Constraints)
- No CCTV evidence chain.
- No voice memo / recording puzzle.
- No "unknown user entered the room" scare beat.
- No "who pushed whom" framing.
- Core fear source must be:
- edited timestamps
- backfilled messages
- impossible concurrent account activity

## 5) Chapter Structure (15-20 min)
- Prologue (2m): missed call + system notice about log retention expiry
- Act 1 (3m): accusation and first stance choice (pressure vs hold)
- Act 2 (4m): lock log + elevator log + power log contradiction
- Act 3 (4m): three input puzzles on revision order and impossible timestamps
- Act 4 (3m): deleted draft diff recovery and self-edit evidence
- Final/Endings (2-4m): 4 main endings + 1 bad ending

## 6) Twist Logic
- Surface truth: Taemin edited records to hide guilt.
- Fracture: same account sends messages from impossible simultaneous contexts.
- Final truth: player scheduled delayed edits to protect self-image after a failed rescue.
- Motivation:
- not to hide murder
- to avoid admitting negligence and timeline tampering

## 7) Evidence Map
- A: Door-lock access log shows 7-minute null window.
- B: Elevator call log shows impossible floor-sequence order.
- C: Hallway power draw spike overlaps with "offline" account messages.
- D: Deleted report draft diff proves player-side backfill edits.

## 8) Branch Design Rules
- Every choice must have:
- immediate emotional/system consequence
- delayed trust score impact
- ending gate impact
- Wrong puzzle answers:
- escalate pressure messages first
- then route to bad ending or severe trust loss
- Ending identities must stay distinct:
- True: acceptance and full timeline disclosure
- Guilt: surrender and official re-report
- Madness: denial and fabricated chronology
- Loop: defer truth and re-enter same room state
- Bad: incomplete restoration under retention timeout

## 9) Ending Gates
- True/Guilt require C + D recovered.
- Madness requires denial route plus at least one contradiction ignored.
- Loop requires final deferral choice.
- Bad triggers on failed core inputs or missing D before expiry.

## 10) Implementation Handoff Notes
- Keep current `scenario` node types only:
- `system`, `date`, `choice`, `input`, `evidence`, `ending_sequence`
- Evidence presentation style:
- text snippets, diff blocks, system-log cards only
- no image/video/audio dependency
- Add one 8-10 second silent gap in late Act 2 for pacing reset.
