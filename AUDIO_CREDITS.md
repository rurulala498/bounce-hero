# Bounce Hero Audio Credits

## 사용 정책

- 취득일: 2026-08-10
- 제작자/배포자: Bounce Hero project, Kenney (Kenney Vleugels), BMacZero (Brian MacIntosh; replaced candidate)
- 라이선스: Creative Commons Zero 1.0 Universal (CC0 1.0)
- 상업적 사용: 가능
- 저작자 표시: 의무 아님. 프로젝트에서는 출처 추적과 감사의 의미로 기록한다.
- 수정 사항: 원본 OGG/WAV를 음질 변환 없이 용도별 파일명으로 복사했다. 재생 볼륨, pitch 범위, 중복 재생 간격은 코드에서 조정한다.
- 라이선스 증빙: `public/assets/audio/licenses/`

## 원본 Pack

| Pack | 원본 URL | License proof | Runtime 용도 |
| --- | --- | --- | --- |
| Kenney RPG Audio | https://kenney.nl/assets/rpg-audio | `kenney-rpg-audio-license.txt` | Blade Orbit |
| Kenney Interface Sounds | https://kenney.nl/assets/interface-sounds | `kenney-interface-sounds-license.txt` | Hover, Confirm, Pause, Resume |
| Kenney Impact Sounds | https://kenney.nl/assets/impact-sounds | `kenney-impact-sounds-license.txt` | Bounce, Stomp, Hit, Death, Boss impact |
| Kenney Digital Audio | https://kenney.nl/assets/digital-audio | `kenney-digital-audio-license.txt` | Air Jump, Dash, Dive, Skill, Boss cue, Run result |
| OpenGameArt Electricity Sound Effects | https://opengameart.org/content/electricity-sound-effects-0 | `opengameart-electricity-sound-effects-cc0.txt` | 교체된 Chain Lightning 후보; 현재 Runtime 미사용 |

공통 라이선스 원문: https://creativecommons.org/publicdomain/zero/1.0/

## Runtime 파일 연결표

| Runtime 파일 | 원본 파일 | 출처 Pack | 사용 용도 |
| --- | --- | --- | --- |
| `sfx/player/bounce.ogg` | `impactSoft_medium_000.ogg` | Impact Sounds | 일반 바닥 Bounce |
| `sfx/player/air-jump.ogg` | `phaseJump1.ogg` | Digital Audio | Air Jump |
| `sfx/player/dash.ogg` | `cloth4.ogg` | RPG Audio | Dash — 짧고 가벼운 천/공기 스침 |
| `sfx/player/dive.ogg` | `phaserDown2.ogg` | Digital Audio | Dive 시작 |
| `sfx/player/player-hit.ogg` | `impactPunch_medium_002.ogg` | Impact Sounds | Player 피격 |
| `sfx/player/player-death.ogg` | `lowDown.ogg` | Digital Audio | Player 사망 |
| `sfx/combat/stomp.ogg` | `impactPunch_heavy_001.ogg` | Impact Sounds | Stomp 성공 |
| `sfx/combat/enemy-hit.ogg` | `impactSoft_medium_002.ogg` | Impact Sounds | 일반 Enemy 피격 |
| `sfx/combat/enemy-death.ogg` | `impactSoft_heavy_004.ogg` | Impact Sounds | 일반 Enemy 사망 |
| `sfx/skills/skill-cast.ogg` | `powerUp3.ogg` | Digital Audio | Active Skill 공통 Cast |
| `sfx/skills/skill-hit.ogg` | `zap1.ogg` | Digital Audio | Active Skill 적중 |
| `sfx/skills/chain-lightning-1.wav` | `scripts/generate_chain_lightning_sfx.py` | Project-authored procedural audio | Chain Lightning 1 segment — 0.113초 |
| `sfx/skills/chain-lightning-2.wav` | `scripts/generate_chain_lightning_sfx.py` | Project-authored procedural audio | Chain Lightning 2 segments — 0.185초 |
| `sfx/skills/chain-lightning-3.wav` | `scripts/generate_chain_lightning_sfx.py` | Project-authored procedural audio | Chain Lightning 3 segments — 0.257초 |
| `sfx/skills/chain-lightning-4.wav` | `scripts/generate_chain_lightning_sfx.py` | Project-authored procedural audio | Chain Lightning 4 segments — 0.329초 |
| `sfx/skills/shockwave.ogg` | `impactBell_heavy_003.ogg` | Impact Sounds | Shockwave |
| `sfx/skills/blade-orbit.ogg` | `knifeSlice2.ogg` | RPG Audio | Blade Orbit |
| `sfx/skills/bounce-burst.ogg` | `phaserUp6.ogg` | Digital Audio | Bounce Burst |
| `sfx/ui/hover.ogg` | `select_001.ogg` | Interface Sounds | UI Hover |
| `sfx/ui/confirm.ogg` | `confirmation_002.ogg` | Interface Sounds | UI Confirm |
| `sfx/ui/level-up.ogg` | `powerUp11.ogg` | Digital Audio | Level Up 선택 진입 |
| `sfx/ui/pause.ogg` | `minimize_003.ogg` | Interface Sounds | Pause |
| `sfx/ui/resume.ogg` | `maximize_003.ogg` | Interface Sounds | Resume |
| `sfx/boss/telegraph.ogg` | `lowThreeTone.ogg` | Digital Audio | Boss 공격/소환 예고 |
| `sfx/boss/slam.ogg` | `impactMining_004.ogg` | Impact Sounds | Ground Shockwave Slam |
| `sfx/boss/projectile.ogg` | `phaserDown3.ogg` | Digital Audio | Rock Projectile 발사 |
| `sfx/boss/hit.ogg` | `impactMetal_heavy_002.ogg` | Impact Sounds | Boss Weak Point 피격 |
| `sfx/boss/death.ogg` | `impactBell_heavy_004.ogg` | Impact Sounds | Boss 사망 |
| `sfx/run/stage-clear.ogg` | `threeTone1.ogg` | Digital Audio | Stage Clear |
| `sfx/run/game-over.ogg` | `threeTone2.ogg` | Digital Audio | Game Over |

모든 Runtime 경로의 기준 디렉터리는 `public/assets/audio/`이다.

## Project-authored Chain Lightning SFX

- Source generator: `scripts/generate_chain_lightning_sfx.py`
- Generation date: 2026-08-10
- External recording/sample input: 없음
- Method: deterministic high-passed noise, irregular micro-impulse snaps, short electrical sizzle bed
- Stable pitched oscillator: 사용하지 않음
- Format: mono PCM16 WAV, 44.1kHz
- Variants: 실제 Lightning segment 1~4개에 대응
- Runtime policy: Skill level 자체가 아니라 실제 연결된 target/segment 수에 맞는 variant를 재생
- Rights: Project-authored source/output; 외부 attribution 불필요

이전에 검토한 OpenGameArt `spark.wav` Runtime은 제거했다. 출처와 CC0 증빙은 교체 이력 보존을 위해 유지한다.

## BGM 상태

일반 Room과 Boss Room의 BGM 전환 API와 중복 재생 방지 구조는 준비했다. 이번에 검증한 Kenney Pack에는 게임 길이에 맞는 명확한 loop BGM이 없어 짧은 효과음을 음악처럼 반복 사용하지 않았다. 따라서 현재 `room`/`boss` BGM mapping은 비어 있으며, 적합한 CC0 음악을 확보한 뒤 파일과 출처를 이 문서에 추가한다.
