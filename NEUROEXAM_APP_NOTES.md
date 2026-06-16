# Neuro Exam 기록 코칭 & 앱(index.html) 개선 메모

> 환자 허영숙 케이스 기준. 내 기록(6/13, hyperacute) vs 시니어 NP 기록(6/16, day 3) 비교.
> ⚠️ 3일 간격이므로 값 차이의 상당수는 disease interval change이며 기록 오류가 아님.
> 코칭 초점 = 포맷 / 완결성 / 컨벤션.

## 교차검증으로 확정된 것 (내 판단이 옳았음)
- **Facial: Lt CTFP** — 시니어도 동일하게 `Lt.CTFP`. 최초 ER기록의 "Rt"는 side 오기재였음이 확정.
- **SPE: 정상 대칭** — 시니어 `SPE(+/+)`. 내 `SPE(+/-)`(=Rt weak)는 over-read였음. 
  → hemispheric(UMN) 병변에선 연구개 bilateral innervation으로 대개 symmetric. 단독 SPE 비대칭은 경고 대상.

## 시니어에게 배워 내 기록/앱에 반영할 것 (TODO)
1. **Trend / interval 주석** — `gaze preference 호전양상`처럼 직전 검사 대비 호전/악화 표기.
   → 앱: 각 항목(또는 요약)에 "이전 대비 ▲호전/▼악화/= 유지" 토글 또는 free-text trend 필드. (현재 없음)
2. **EOM 방향 구체화** — 단순 "Limitation (+)" → `Lt lateral limitation`처럼 제한 방향 명시.
   → 앱(line 80 eom): "Limitation (+)" 선택 시 방향 sub-field(Lt/Rt × lateral/medial/up/down) 추가.
   - 임상 메모: day3 새 Lt 외전제한은 IVH/raised ICP의 false-localizing CN VI 가능성 → trend로 잡아야.
3. **Extinction / 고위피질기능 섹션** — 시니어는 Sensory에 `Extinction(+)` 기록. 내 6/13엔 누락(반복 실수).
   → 앱: Sensory에 Extinction(DSS) 필드 + 별도 "Higher cortical function" 섹션(neglect, asomatognosia). (현재 전부 없음)
4. **Uvular Deviation 항상 기록** — 내가 6/13에 누락. 앱엔 필드 존재(line 95) → 입력만 빠짐. 기본 노출 강화.
5. **비교 표기 "Rt > Lt"** — facial sense 등 좌우 비대칭을 comparative로. (현재 Lt/Rt decreased만)
6. **Motor range/half grade** — 시니어 `III~IV`. 앱은 4+/4/4-까지만, range(3~4) 불가.
   → 앱(line 107~111): "3~4" 같은 range 옵션 또는 이중 select 허용 검토.
7. **Facial sense 환측 검사** — 내 6/13 "symm intact" but 시니어 Lt 저하. cortical hemisensory면 face도 포함될 수 있음 → 환측 facial sense 항상 확인.

## 내가 더 잘한 것 (앱에서 반드시 유지)
- GCS(E/V/M), NPi(pupillometer 수치), 지남력 답변 인용("허영숙/병원/13일"), 3-step O-C 명시
- VFD **side 명시**(Lt) — 시니어는 side 없이 VFD(+)만
- **Muscle tone (Rigidity/Spasticity) + parkinsonism 귀속** — 시니어 미기록
- Sensory **modality 분리**(Touch / Pain) — 시니어는 통합
- 요약 라인 `* Lt side weakness`

## 6/13 → 6/16 임상 interval change (참고)
- Orientation: time (+)→(-)  | Lt motor 3→2 악화(arm/leg)  | 새 Lt lateral gaze limitation
- 새 Lt facial sense 저하 | Extinction(+) 문서화 | gaze preference는 호전
- 해석: day 3 perihematomal edema / IVH 경과 패턴. Lt 외전제한은 ICP 관점 추적 필요.

## 앱 cross-check(경고) 로직 후보
- facial/SPE/uvula 등의 **side**가 hemiparesis·VFD·neglect 등 다른 편측 소견과 **반대쪽**이면 경고.
  (이번 "Rt facial", "SPE(+/-)" 같은 단독 역방향 소견을 입력단에서 포착)
