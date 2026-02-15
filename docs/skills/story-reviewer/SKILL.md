---
name: story-reviewer
description: 채팅형 공포 스토리의 재미, 개연성, 분기 유의미성, 엔딩 회수력을 점검하는 로컬 검토 스킬
---

# Story Reviewer

## Objective
`horrorchat2` 스토리 문서를 구현 전 단계에서 검토해, 플레이 재미와 서사 정합성을 확보한다.

## Inputs
- `docs/story/story_blueprint_v1.md`
- `docs/story/branch_map_v1.md`

## Review Workflow
1. 스토리 목표(플레이타임, 분위기, 반전, 멀티 엔딩)가 문서에 명시됐는지 확인한다.
2. 분기별 인과관계를 따라가며 "왜 이 선택이 이 결과를 만드는가"를 점검한다.
3. 각 엔딩이 서로 다른 감정 결말을 제공하는지 확인한다.
4. 단서 회수와 반전 공개 시점이 논리적으로 연결되는지 확인한다.
5. 구현 가능한 노드 타입(`system/date/choice/input/evidence/ending_sequence`)만 사용했는지 확인한다.

## Scoring Rubric (5점 만점 x 4축)
1. 재미(긴장 곡선)
- 5: 장면 전환마다 긴장 상승/이완 리듬이 뚜렷함
- 3: 긴장 포인트가 있으나 반복 패턴이 단조로움
- 1: 사건 전개가 평면적이고 체감 긴장 부족
2. 개연성(인과)
- 5: 동기, 증거, 반전이 모순 없이 연결됨
- 3: 일부 점프가 있으나 보완 가능
- 1: 핵심 전환이 설명되지 않음
3. 분기 유의미성
- 5: 선택마다 체감 가능한 결과 차이 존재
- 3: 일부 선택은 의미가 약함
- 1: 선택 대부분이 같은 결과로 수렴
4. 엔딩 회수력
- 5: 모든 엔딩이 복선을 다르게 회수
- 3: 엔딩 구분은 되나 회수 포인트가 겹침
- 1: 엔딩 차별성이 부족

## Pass Criteria
- 총점 16/20 이상
- 각 축 최소 3점 이상

## Fail Handling
1. 3점 미만 축을 우선 수정 대상으로 지정한다.
2. `story_blueprint_v1.md`와 `branch_map_v1.md`를 함께 수정한다.
3. 재평가를 최소 1회 수행한다.

## Output Format
검토 결과는 `docs/review/story_review_report_v1.md`에 다음 순서로 기록한다.
1. 요약 결론(합격/보완 필요)
2. 축별 점수 및 근거
3. 발견 이슈(심각도: high/medium/low)
4. 수정 권고안
5. 재검토 여부
