# 분기 맵 v1 (`scenario` 이식용)

## 1) 노드 타입 규칙
- 사용 타입: `system`, `date`, `choice`, `input`, `evidence`, `ending_sequence`
- 명명 규칙: `<act>_<seq>` 또는 `<act>_<purpose>`
- 필수 필드:
- 공통: `id`, `type`, `next?`
- 선택: `options[{label,next}]`
- 입력: `correctAnswer`, `failNext`
- 엔딩: `ending{label,title,desc}`

## 2) 메인 플로우
1. `prologue_notify` (`system`) -> `start_invite`
2. `start_invite` (`system`) -> `date_divider`
3. `date_divider` (`date`) -> `act1_1`
4. `act1_1` -> `act1_2` -> `act1_choice`
5. `act1_choice` (`choice`) -> `act1_probe` or `act1_deflect`
6. `act1_probe/deflect` -> `act1_evidence_accesslog` (`evidence`)
7. `act1_evidence_accesslog` -> `act2_1`
8. `act2_1` -> `act2_evidence_newspaper` (`evidence`) -> `act2_choice`
9. `act2_choice` (`choice`) -> `act2_push_taemin` or `act2_hold`
10. `act2_*` -> `act2_evidence_cctv_angle2` (`evidence`) -> `act3_intro`
11. `act3_intro` -> `puzzle_1_input` (`input`)
12. `puzzle_1_input` success -> `puzzle_2_input`; fail -> `bad_fast_fail`
13. `puzzle_2_input` success -> `puzzle_3_input`; fail -> `bad_fast_fail`
14. `puzzle_3_input` success -> `act4_unknown_enter`; fail -> `bad_fast_fail`
15. `act4_unknown_enter` -> `act4_evidence_deleted_draft` (`evidence`) -> `final_choice`
16. `final_choice` (`choice`) -> `ending_true` | `ending_guilt` | `ending_madness` | `ending_loop`

## 3) 상세 분기 테이블

| ID | Type | 설명 | 다음 노드 |
|---|---|---|---|
| prologue_notify | system | 부재중 번호가 음성메모/사진 전송 | start_invite |
| start_invite | system | 고시원 404 조사방 초대 | date_divider |
| date_divider | date | 사건 3주기 날짜 표시 | act1_1 |
| act1_1 | system | 서윤: 태민 의심 발언 | act1_2 |
| act1_2 | system | 태민 부인 + 플레이어 반응 요구 | act1_choice |
| act1_choice | choice | 태민 추궁 vs 진정 시도 | act1_probe / act1_deflect |
| act1_probe | system | 즉시 갈등 상승 | act1_evidence_accesslog |
| act1_deflect | system | 표면 진정, 불신 지연 상승 | act1_evidence_accesslog |
| act1_evidence_accesslog | evidence | 출입기록 공백 7분 | act2_1 |
| act2_1 | system | 서윤: 당시 기사 공유 예고 | act2_evidence_newspaper |
| act2_evidence_newspaper | evidence | 실종 기사 + 시간 불일치 | act2_choice |
| act2_choice | choice | 태민 몰이 vs 보류 | act2_push_taemin / act2_hold |
| act2_push_taemin | system | 태민 강퇴 시도 로그 실패 | act2_evidence_cctv_angle2 |
| act2_hold | system | 침묵으로 시스템 글리치 노출 | act2_evidence_cctv_angle2 |
| act2_evidence_cctv_angle2 | evidence | CCTV 각도 2개 상충 | act3_intro |
| act3_intro | system | 기억 검증 단계 진입 | puzzle_1_input |
| puzzle_1_input | input | 404호 비밀번호 조합 입력 | puzzle_1_ok / bad_fast_fail |
| puzzle_1_ok | system | 1차 복원 성공 | puzzle_2_input |
| puzzle_2_input | input | 신고 접수 시각 입력 | puzzle_2_ok / bad_fast_fail |
| puzzle_2_ok | system | 2차 복원 성공 | puzzle_3_input |
| puzzle_3_input | input | 음성메모 마지막 단어 입력 | puzzle_3_ok / bad_fast_fail |
| puzzle_3_ok | system | 숨김 로그 복원 | act4_unknown_enter |
| act4_unknown_enter | system | 알 수 없는 사용자 입장 | act4_evidence_deleted_draft |
| act4_evidence_deleted_draft | evidence | 플레이어 작성 후 삭제한 신고 초안 | final_choice |
| final_choice | choice | 진실 수용/자수/부정/정체 추궁 | 각 엔딩 |
| bad_fast_fail | ending_sequence | 핵심 입력 실패 | BAD ENDING |
| ending_true | ending_sequence | 수용 | TRUE ENDING |
| ending_guilt | ending_sequence | 자수 | GUILT ENDING |
| ending_madness | ending_sequence | 부정 | MADNESS ENDING |
| ending_loop | ending_sequence | 리셋 | LOOP ENDING |

## 4) 입력 퍼즐 정답(초안)
- `puzzle_1_input.correctAnswer`: `0404`
- `puzzle_2_input.correctAnswer`: `2317`
- `puzzle_3_input.correctAnswer`: `미안`

## 5) 엔딩 최소 텍스트 가이드
- TRUE: "네가 죽인 게 아니라, 놓친 거야"를 받아들이는 문장 포함
- GUILT: 위치 전송/신고 재접수 시스템 메시지 포함
- MADNESS: 참가자 수 급증, 동일 닉네임 스팸 포함
- LOOP: `[오류] 로그를 불러올 수 없습니다` + 방 리셋 문구 포함
- BAD: 진실 복원 실패와 기록 단절 강조
