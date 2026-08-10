# Bounce Hero Asset Credits

## 1. 목적

이 문서는 Bounce Hero에서 사용하거나 검토한 모든 외부/AI 생성 Image, Font, UI, VFX, Music, SFX, Reference의 출처와 License를 기록한다.

- 출처와 권리를 확인할 수 없는 에셋은 runtime에 포함하지 않는다.
- 무료 에셋도 원본 URL, 저작자, License, 상업적 사용 가능 여부를 기록한다.
- AI 생성 에셋은 사용 Tool/Model, 생성일, Prompt 요약, Reference 권리를 기록한다.
- 에셋을 교체하더라도 기존 출처 기록은 삭제하지 않고 상태를 `replaced` 또는 `removed`로 변경한다.

---

## 2. 현재 상태

11-G 기준으로 외부 Image/Font 파일은 runtime에 추가하지 않았다. Audio는 라이선스가 명확한 Kenney 및 OpenGameArt CC0 효과음을 사용하며 상세 원본 파일, URL, 용도는 `AUDIO_CREDITS.md`에 기록한다. Player Character/Equipment, Slime/Bat/STONE GOLEM, 일반 Room과 Boss Room 환경은 이 프로젝트를 위해 OpenAI ImageGen으로 새로 생성했다. 사용자가 제공한 상용 게임 이미지는 v2의 일반적인 pixel 비율과 가독성 방향을 논의하는 reference-only 자료로만 사용했고 배포 파일에는 포함하지 않았다.

현재 Player는 11-B, Enemy/Boss는 11-C Pixel Sprite, Arena 환경은 11-D Pixel Background로 교체됐다. 보이지 않는 Player physics collider와 Arena collision surface, UI, 일부 VFX/Hazard는 프로젝트 내부 Phaser Graphics와 코드로 생성되며 외부 저작물 파일을 사용하지 않는다.

| Asset ID | Category | Path / Location | Source | License | Status | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| `procedural-placeholder-set` | Visual placeholder | `src/scenes/BootScene.ts` 및 UI/Entity code | Project-authored procedural graphics | Project source terms | active | Player/Enemy/Boss 표시는 교체 완료. 보이지 않는 collider와 Arena/UI/일부 VFX/Hazard에만 유지 |
| `rookie-character-modular-set-v1` | Character / Equipment | `art-source/legacy/phase-11-b-v1-runtime/` | OpenAI ImageGen, project-specific generation | Applicable OpenAI service terms | replaced | 초기 smooth SD 방향. 기록과 이전 runtime을 보존 |
| `rookie-character-pixel-set-v2` | Character / Equipment | `public/assets/characters/*/rookie/`, `public/assets/equipment/armor/`, `public/assets/equipment/weapon/` | OpenAI ImageGen, project-specific generation | Applicable OpenAI service terms | active | 승인된 crisp pixel Rookie Base/Armor/Weapon 9종 |
| `phase-11-c-enemy-pixel-set` | Enemy | `public/assets/enemies/` | OpenAI ImageGen, project-specific generation | Applicable OpenAI service terms | active | Slime/Elite Slime/Bat 3종 |
| `phase-11-c-stone-golem-pixel-set` | Boss | `public/assets/bosses/stone-golem/` | OpenAI ImageGen, project-specific generation | Applicable OpenAI service terms | active | Phase 1/2 Body와 Weak Point 3종 |
| `phase-11-d-environment-pixel-set` | Background | `public/assets/backgrounds/` | OpenAI ImageGen, project-specific generation | Applicable OpenAI service terms | active | 일반 Ruins Room과 STONE GOLEM Sanctum 2종 |
| `phase-11-g-kenney-cc0-audio-set` | Audio / SFX | `public/assets/audio/` | Kenney RPG Audio, Interface Sounds, Impact Sounds, Digital Audio | CC0 1.0 Universal | active | 26개 SFX. 상세 연결표와 URL은 `AUDIO_CREDITS.md` 참고 |
| `chain-lightning-electric-crackle` | Audio / SFX | Runtime removed; proof retained in `public/assets/audio/licenses/` | BMacZero, OpenGameArt Electricity Sound Effects | CC0 1.0 Universal | replaced | 실제 Tesla generator `spark.wav` 후보. 사용자 청감 검토 후 project-authored set으로 교체 |
| `chain-lightning-procedural-crackle-set` | Audio / SFX | `public/assets/audio/sfx/skills/chain-lightning-*.wav` | Project-authored procedural generation | Project source terms | active | 실제 연결 segment 1~4개에 맞춰 0.113~0.329초로 늘어나는 비음정형 crackle 4종 |

### AI Asset: `rookie-character-modular-set-v1`

- Category: Character / Equipment
- Runtime backup path: `art-source/legacy/phase-11-b-v1-runtime/`
- Source/master path: `art-source/characters/*/char-*-rookie-modular-sheet-*`
- Generation tool: OpenAI ImageGen built into Codex
- Model and version: ImageGen backend version not exposed by the tool
- Generation date: `2026-08-09`
- Account/license tier used: Current project owner's configured OpenAI/Codex session
- Commercial use terms URL: Applicable OpenAI service terms; project owner should retain the terms accepted by the generating account
- Prompt record: `art-source/prompt-records/phase-11-b-rookie-character-prompts.md`
- Input image/reference list: Knight는 text-only 신규 생성. Rogue/Mage는 같은 작업에서 생성한 Knight sheet만 style/proportion reference로 사용
- Reference rights verified: Yes — project-generated reference only
- Artist cleanup/paint-over: Chroma removal, edge despill, crop, scale, common 256px canvas normalization
- Derivative variants: Base, Armor, Weapon runtime layer exports
- Watermark/signature check: Passed
- Similarity review against existing commercial characters: Passed by visual inspection; original generic rookie fantasy direction
- Status: replaced
- Reviewer: Codex technical review; project owner rejected this visual direction
- Notes: 사용자가 원하는 pixel 방향과 달라 v2로 교체. 이전 runtime은 `art-source/legacy/phase-11-b-v1-runtime/`에 보존

### AI Asset: `rookie-character-pixel-set-v2`

- Category: Character / Equipment
- Runtime path: `public/assets/characters/`, `public/assets/equipment/armor/`, `public/assets/equipment/weapon/`
- Source/master path: `art-source/characters/*/*pixel-v2*`
- Style checkpoint: `art-source/style-checkpoints/phase-11-b-v2-rookie-lineup.png`
- Generation tool: OpenAI ImageGen built into Codex
- Model and version: ImageGen backend version not exposed by the tool
- Generation date: `2026-08-09`
- Account/license tier used: Current project owner's configured OpenAI/Codex session
- Commercial use terms URL: Applicable OpenAI service terms; project owner should retain the terms accepted by the generating account
- Prompt record: `art-source/prompt-records/phase-11-b-pixel-v2-character-prompts.md`
- Input image/reference list: runtime용 modular sheet에는 프로젝트가 승인한 v2 lineup만 직접 사용. 해당 lineup의 방향 검토에는 사용자가 제공한 외부 상용 게임 screenshot을 reference-only로 사용
- Reference rights verified: External reference의 소유권/라이선스는 확인되지 않음. 파일은 runtime/source sheet에 포함하지 않고 일반적인 SD pixel 비율과 가독성 분석에만 제한
- Artist cleanup/paint-over: Chroma removal, edge despill, crop, `NEAREST` scale, common 256px canvas normalization
- Derivative variants: Knight/Rogue/Mage Base, Armor, Weapon runtime layer exports
- Watermark/signature check: Passed
- Similarity review against existing commercial characters: Passed by visual inspection; 특정 의상, 얼굴, 무기, 실루엣을 직접 복제하지 않은 original rookie fantasy design
- Status: active
- Reviewer: Project owner visual approval; Codex technical review
- Notes: Head와 Back starter Slot은 의도적으로 empty. 전체 path mapping은 `CHARACTER_ASSET_MAP.md` 참고

### AI Asset: `phase-11-c-enemy-boss-pixel-set`

- Category: Enemy / Boss
- Runtime path: `public/assets/enemies/`, `public/assets/bosses/stone-golem/`
- Source/master path: `art-source/enemies/`, `art-source/bosses/stone-golem/`
- Generation tool: OpenAI ImageGen built into Codex
- Model and version: ImageGen backend version not exposed by the tool
- Generation date: `2026-08-09`
- Account/license tier used: Current project owner's configured OpenAI/Codex session
- Commercial use terms URL: Applicable OpenAI service terms; project owner should retain the terms accepted by the generating account
- Prompt record: `art-source/prompt-records/phase-11-c-enemy-boss-prompts.md`
- Input image/reference list: 프로젝트 승인 `phase-11-b-v2-rookie-lineup.png`을 pixel/world style reference로만 사용
- Reference rights verified: Direct reference is project-generated. 그 기준본의 초기 방향 검토에 사용된 reference-only 자료 정책은 `rookie-character-pixel-set-v2` 기록을 따름
- Artist cleanup/paint-over: Red/green chroma removal, alpha validation, separated-object crop, `NEAREST` runtime export
- Derivative variants: Basic Slime, Elite Slime, Bat, Stone Golem Phase 1/2, Weak Point
- Watermark/signature check: Passed
- Similarity review against existing commercial characters: Passed by visual inspection; original generic cute fantasy enemy/ancient stone guardian design
- Status: active
- Reviewer: Codex visual/technical review; project owner in-game taste review pending
- Notes: Runtime/texture mapping과 reaction 연결은 `ENEMY_BOSS_ASSET_MAP.md` 참고

### AI Asset: `phase-11-d-environment-pixel-set`

- Category: Background
- Runtime path: `public/assets/backgrounds/`
- Source/master path: `art-source/backgrounds/`
- Generation tool: OpenAI ImageGen built into Codex
- Model and version: ImageGen backend version not exposed by the tool
- Generation date: `2026-08-09`
- Account/license tier used: Current project owner's configured OpenAI/Codex session
- Commercial use terms URL: Applicable OpenAI service terms; project owner should retain the terms accepted by the generating account
- Prompt record: `art-source/prompt-records/phase-11-d-environment-prompts.md`
- Input image/reference list: 프로젝트 승인 `phase-11-b-v2-rookie-lineup.png`, Boss Room에 한해 프로젝트 생성 `phase-11-c-stone-golem-pixel-rgba.png`
- Reference rights verified: Yes — direct references are project-generated assets
- Artist cleanup/paint-over: Center crop, gameplay floor guide alignment, 1280×720 RGB export, palette/contrast review
- Derivative variants: Room별 low-intensity tint/overlay/flip variation은 Phaser runtime config로 적용
- Watermark/signature check: Passed
- Similarity review against existing commercial environments: Passed by visual inspection; original generic ancient fantasy ruins design
- Status: active
- Reviewer: Codex visual/technical review; project owner in-game taste review pending
- Notes: Runtime/layer/collision mapping은 `ENVIRONMENT_ASSET_MAP.md` 참고

### AI Asset: `phase-11-e-skill-icon-pixel-set`

- Category: UI / Skill Icon
- Runtime path: `public/assets/ui/skill-icons/`
- Source/master path: `art-source/ui/skill-icons/phase-11-e-skill-icon-sheet-v2-source.png`
- Generation tool: OpenAI ImageGen built into Codex
- Model and version: ImageGen backend version not exposed by the tool
- Generation date: `2026-08-09`
- Account/license tier used: Current project owner's configured OpenAI/Codex session
- Commercial use terms URL: Applicable OpenAI service terms; project owner should retain the terms accepted by the generating account
- Prompt record: `art-source/prompt-records/phase-11-e-skill-icon-prompts.md`
- Input image/reference list: 프로젝트 승인 `art-source/style-checkpoints/phase-11-b-v2-rookie-lineup.png`을 pixel density와 world cohesion reference로만 사용
- Reference rights verified: Yes — direct reference is a project-generated asset
- Artist cleanup/paint-over: Green chroma removal, edge despill, 4×2 cell split, alpha crop, `NEAREST` scale, 128×128 RGBA normalization
- Derivative variants: Active 4종, Passive 4종 runtime icons
- Watermark/signature check: Passed
- Similarity review against existing commercial characters: Passed by visual inspection; original generic action-fantasy skill symbols
- Status: active
- Reviewer: Codex visual/technical review; project owner in-game taste review pending
- Notes: Magenta-key first attempt is retained as rejected source because chroma removal damaged internal highlights. Runtime mapping is documented in `SKILL_ICON_ASSET_MAP.md`

---

## 3. 승인 상태

| Status | 의미 |
| --- | --- |
| `proposed` | 후보로 수집했지만 사용 승인 전 |
| `review` | Style/License 검토 중 |
| `approved` | runtime 사용 승인 |
| `active` | 현재 build에서 사용 중 |
| `replaced` | 새 에셋으로 교체됐지만 기록 보존 |
| `removed` | build에서 제거됨 |
| `rejected` | 권리/Style/품질 문제로 사용하지 않음 |

---

## 4. External Asset 기록 Template

아래 항목을 에셋 단위 또는 동일 출처 Pack 단위로 복사해 사용한다.

```md
### Asset: <asset-id>

- Category: Character / Equipment / Enemy / Boss / Background / UI / VFX / Font / Music / SFX / Reference
- Runtime path: `public/assets/...`
- Source title:
- Author / Studio:
- Original URL:
- Download / acquisition date: YYYY-MM-DD
- License name and version:
- License URL or proof:
- Commercial use allowed: Yes / No / Unclear
- Modification allowed: Yes / No / Unclear
- Attribution required: Yes / No
- Required attribution text:
- Modifications made:
- Status: proposed / review / approved / active / replaced / removed / rejected
- Reviewer:
- Notes:
```

---

## 5. AI Generated Asset 기록 Template

```md
### AI Asset: <asset-id>

- Category:
- Runtime path: `public/assets/...`
- Source/master path:
- Generation tool:
- Model and version:
- Generation date: YYYY-MM-DD
- Account/license tier used:
- Commercial use terms URL:
- Prompt record path or summary:
- Input image/reference list:
- Reference rights verified: Yes / No / Not applicable
- Artist cleanup/paint-over:
- Derivative variants:
- Watermark/signature check: Passed / Failed
- Similarity review against existing commercial characters: Passed / Failed
- Status: proposed / review / approved / active / replaced / removed / rejected
- Reviewer:
- Notes:
```

AI Prompt 전체가 너무 길면 `art-source/prompt-records/<asset-id>.md`에 보관하고 이 문서에는 요약과 경로를 남긴다.

---

## 6. Audio Asset 기록 Template

```md
### Audio: <asset-id>

- Type: BGM / Ambience / Player SFX / Enemy SFX / Boss SFX / UI SFX
- Runtime path: `public/assets/audio/...`
- Source/master path:
- Title:
- Composer / Creator:
- Original URL:
- License:
- Commercial use allowed:
- Attribution required:
- Generation/recording tool if applicable:
- Duration:
- Sample rate / channels:
- Loop: Yes / No
- Loop point:
- Editing and mix changes:
- Status:
- Notes:
```

---

## 7. Font 기록 Template

```md
### Font: <font-family>

- Font files:
- Designer / Foundry:
- Original URL:
- License:
- License file included at:
- Web embedding allowed:
- Commercial use allowed:
- Modification/subsetting allowed:
- Required attribution:
- Used in:
- Status:
- Notes:
```

---

## 8. Reference-only 자료

Reference로만 사용하고 runtime에 포함하지 않는 자료도 직접 복제 위험과 출처 추적을 위해 기록한다.

| Reference ID | Purpose | Creator / Source | URL / Local proof | Rights note | Used by | Status |
| --- | --- | --- | --- | --- | --- | --- |
| `user-pixel-style-example-2026-08-09` | SD 비율, pixel cluster, 밝은 outer rim의 일반적 방향 논의 | 사용자가 제공한 외부 상용 게임 screenshot; 원 저작자 미확인 | Codex attachment, runtime 미포함 | 권리 미확인. Reference-only 분석으로 제한하고 직접 복제하지 않음 | `phase-11-b-v2-rookie-lineup` 방향 확정 | reviewed |

특정 상용 게임 Character를 Style Prompt의 직접 대상으로 사용하지 않는다. 일반적인 `cute SD fantasy`, `crisp pixel cluster`, `ultra-deformed proportions`, `warm outer rim` 같은 비독점적 특징으로 설명한다.

---

## 9. Attribution 출력 영역

Release에서 Credits 화면이나 배포 문서에 표시해야 할 문구를 여기에 모은다.

```text
Required attribution: none.
Optional credit: Sound effects by Kenney (kenney.nl), licensed CC0 1.0.
Optional credit: Electric spark recording by Brian MacIntosh (BMacZero), licensed CC0 1.0.
```

Attribution이 필요한 에셋이 추가되면 게임 내 Credits, README 또는 배포 페이지 중 License가 요구하는 위치에 반영한다.

---

## 10. Pre-merge License Checklist

- [ ] 원본 URL과 저작자 확인
- [ ] License 원문 또는 영수증/약관 증빙 보관
- [ ] 상업적 사용 가능 여부 확인
- [ ] 수정 및 재배포 가능 여부 확인
- [ ] Attribution 요구사항 반영
- [ ] AI Tool/Model/Reference 기록
- [ ] watermark/signature 제거 및 권리 검토
- [ ] runtime path와 실제 파일 일치
- [ ] 교체된 에셋의 이전 기록 보존
- [ ] 최종 Reviewer와 승인 상태 기록

권리가 `Unclear`인 에셋은 승인하지 않는다.
