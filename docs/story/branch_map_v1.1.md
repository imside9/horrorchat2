# Branch Map v1.2 (Scenario-ready)

## 1) Node Type Contract
- Allowed types:
- `system`
- `date`
- `choice`
- `input`
- `evidence`
- `ending_sequence`

## 2) Main Flow
1. `prologue_retention_notice` -> `start_invite`
2. `start_invite` -> `date_divider`
3. `date_divider` -> `act1_accuse_open` -> `act1_choice`
4. `act1_choice` -> `act1_press_taemin` or `act1_hold_room`
5. `act1_press_taemin`/`act1_hold_room` -> `act1_evidence_locklog`
6. `act1_evidence_locklog` -> `act2_evidence_elevatorlog` -> `act2_choice`
7. `act2_choice` -> `act2_force_kickvote` or `act2_trace_metadata`
8. `act2_force_kickvote`/`act2_trace_metadata` -> `act2_evidence_powerlog`
9. `act2_evidence_powerlog` -> `act2_silence_gap` -> `act3_intro`
10. `act3_intro` -> `puzzle_1_revision_order`
11. `puzzle_1_revision_order` success -> `puzzle_2_impossible_timestamp`, fail -> `bad_fast_fail`
12. `puzzle_2_impossible_timestamp` success -> `puzzle_3_backfill_author`, fail -> `bad_fast_fail`
13. `puzzle_3_backfill_author` success -> `act4_evidence_deleted_draft_diff`, fail -> `bad_fast_fail`
14. `act4_evidence_deleted_draft_diff` -> `act4_account_conflict` -> `final_choice`
15. `final_choice` -> `ending_true` / `ending_guilt` / `ending_madness` / `ending_loop`

## 3) Detailed Node Table

| ID | Type | Description | Next |
|---|---|---|---|
| prologue_retention_notice | system | System warns logs auto-purge in 20 minutes | start_invite |
| start_invite | system | Room 404 coordination room is reopened temporarily | date_divider |
| date_divider | date | Case anniversary marker | act1_accuse_open |
| act1_accuse_open | system | Seoyun frames Taemin as likely culprit | act1_choice |
| act1_choice | choice | Press suspect now vs preserve room stability | act1_press_taemin / act1_hold_room |
| act1_press_taemin | system | Conflict spikes and trust meter drops | act1_evidence_locklog |
| act1_hold_room | system | Surface calm, delayed doubt remains | act1_evidence_locklog |
| act1_evidence_locklog | evidence | Door-lock log shows a 7-minute null window | act2_evidence_elevatorlog |
| act2_evidence_elevatorlog | evidence | Elevator sequence conflicts with claimed movement path | act2_choice |
| act2_choice | choice | Force kick-vote vs inspect metadata chain | act2_force_kickvote / act2_trace_metadata |
| act2_force_kickvote | system | Vote fails due to permission mismatch | act2_evidence_powerlog |
| act2_trace_metadata | system | Hana exposes edit metadata fragments | act2_evidence_powerlog |
| act2_evidence_powerlog | evidence | Power spike overlaps with "offline" account posts | act2_silence_gap |
| act2_silence_gap | system | 8-10 second no-message interval before memory phase | act3_intro |
| act3_intro | system | Restore process begins under retention timer pressure | puzzle_1_revision_order |
| puzzle_1_revision_order | input | Enter correct revision order of three draft snapshots | puzzle_1_ok / bad_fast_fail |
| puzzle_1_ok | system | First restore succeeded, contradiction narrowed | puzzle_2_impossible_timestamp |
| puzzle_2_impossible_timestamp | input | Enter impossible timestamp in merged room timeline | puzzle_2_ok / bad_fast_fail |
| puzzle_2_ok | system | Second restore succeeded, author scope narrowed | puzzle_3_backfill_author |
| puzzle_3_backfill_author | input | Identify who backfilled deleted line in final draft | puzzle_3_ok / bad_fast_fail |
| puzzle_3_ok | system | Restore complete, hidden diff unlocked | act4_evidence_deleted_draft_diff |
| act4_evidence_deleted_draft_diff | evidence | Diff block shows player-authored delayed edits | act4_account_conflict |
| act4_account_conflict | system | Existing accounts emit contradictory posts in same minute | final_choice |
| final_choice | choice | Accept / surrender / deny / defer | endings |
| ending_true | ending_sequence | Acceptance ending: full disclosure | overlay |
| ending_guilt | ending_sequence | Surrender ending: official re-report | overlay |
| ending_madness | ending_sequence | Denial ending: fabricated chronology | overlay |
| ending_loop | ending_sequence | Deferral ending: room reset loop | overlay |
| bad_fast_fail | ending_sequence | Failed restoration before retention expiry | overlay |

## 4) Input Answers (Draft)
- `puzzle_1_revision_order.correctAnswer`: `B-A-C`
- `puzzle_2_impossible_timestamp.correctAnswer`: `23:17:42`
- `puzzle_3_backfill_author.correctAnswer`: `player`

## 5) Ending Text Requirements
- TRUE: explicit admission of delayed self-edit and failed rescue.
- GUILT: include system line for resubmitted official statement.
- MADNESS: include insistence that logs are forged plus trust collapse.
- LOOP: include retention timer reset and room recreation notice.
- BAD: emphasize purge completion and irrecoverable truth loss.

## 6) Season-1 Difference Checklist
- No CCTV node IDs, assets, or descriptions.
- No voice memo or recording-based input.
- No unknown user join event.
- Progression is driven by metadata/diff contradictions, not external media reveals.
