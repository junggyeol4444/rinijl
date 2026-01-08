# Mineage Hybrid 서버 플러그인 목록

## 필수 플러그인 다운로드 URL

### 핵심 시스템
| 플러그인 | 용도 | 다운로드 URL |
|---------|------|-------------|
| **PaperMC 1.21.1** | 서버 코어 | https://papermc.io/downloads/paper |
| **PlaceholderAPI** | 플레이스홀더 지원 | https://www.spigotmc.org/resources/placeholderapi.6245/ |

### 권한 & 경제
| 플러그인 | 용도 | 다운로드 URL |
|---------|------|-------------|
| **LuckPerms** | 권한 관리 시스템 | https://luckperms.net/download |
| **Vault** | 경제 API | https://www.spigotmc.org/resources/vault.34315/ |
| **EssentialsX** | 기본 명령어 & 경제 | https://essentialsx.net/downloads.html |

### RPG 시스템
| 플러그인 | 용도 | 다운로드 URL |
|---------|------|-------------|
| **MythicLib** | MMO 라이브러리 (MMOCore 의존성) | https://www.spigotmc.org/resources/mythiclib.90306/ |
| **MMOCore** | RPG 클래스 & 레벨링 시스템 | https://www.spigotmc.org/resources/mmocore.70575/ |
| **MythicMobs Free** | 커스텀 몹 생성 | https://www.spigotmc.org/resources/mythicmobs-free-version.5702/ |
| **mcMMO** | 보조 스킬 시스템 | https://www.spigotmc.org/resources/official-mcmmo-original-author-returns.64348/ |

### 혈맹 & PvP
| 플러그인 | 용도 | 다운로드 URL |
|---------|------|-------------|
| **SaberFactions** | 혈맹 시스템 | https://www.spigotmc.org/resources/saberfactions.69771/ |
| **CombatLogX** | 전투 중 로그아웃 방지 | https://www.spigotmc.org/resources/combatlogx.31689/ |

### 월드 관리
| 플러그인 | 용도 | 다운로드 URL |
|---------|------|-------------|
| **WorldEdit** | 월드 에디팅 (WorldGuard 의존성) | https://enginehub.org/worldedit |
| **WorldGuard** | 지역 보호 & PvP 구역 설정 | https://enginehub.org/worldguard |

### 경제 & 상점
| 플러그인 | 용도 | 다운로드 URL |
|---------|------|-------------|
| **Shopkeepers** | NPC 상점 시스템 | https://www.spigotmc.org/resources/shopkeepers.80756/ |
| **AuctionHouse** | 경매 시스템 | https://www.spigotmc.org/resources/auctionhouse.61836/ |
| **Jobs Reborn** | 직업 시스템 | https://www.spigotmc.org/resources/jobs-reborn.4216/ |

### 퀘스트 & 이벤트
| 플러그인 | 용도 | 다운로드 URL |
|---------|------|-------------|
| **BetonQuest** | 퀘스트 시스템 | https://betonquest.org/ |
| **EpicBosses** | 월드 보스 레이드 | https://www.spigotmc.org/resources/epicbosses.34924/ |

### UI & 스크립팅
| 플러그인 | 용도 | 다운로드 URL |
|---------|------|-------------|
| **DeluxeMenus** | GUI 메뉴 생성 | https://www.spigotmc.org/resources/deluxemenus.11734/ |
| **Skript** | 스크립트 시스템 (커스텀 기능 구현) | https://github.com/SkriptLang/Skript/releases |

## 플러그인 설치 순서

### 1단계: 의존성 플러그인 (먼저 설치)
1. **Vault** - 경제 API (많은 플러그인이 의존)
2. **PlaceholderAPI** - 플레이스홀더 지원
3. **WorldEdit** - WorldGuard의 의존성
4. **MythicLib** - MMOCore의 의존성

### 2단계: 핵심 플러그인
5. **LuckPerms** - 권한 관리
6. **EssentialsX** - 기본 명령어 & 경제
7. **WorldGuard** - 지역 보호
8. **MMOCore** - RPG 클래스 시스템
9. **MythicMobs** - 커스텀 몹

### 3단계: 부가 기능 플러그인
10. **SaberFactions** - 혈맹 시스템
11. **mcMMO** - 보조 스킬
12. **CombatLogX** - 전투 로그아웃 방지
13. **Jobs Reborn** - 직업 시스템
14. **Shopkeepers** - 상점 시스템
15. **AuctionHouse** - 경매 시스템
16. **BetonQuest** - 퀘스트 시스템
17. **EpicBosses** - 월드 보스
18. **DeluxeMenus** - GUI 메뉴
19. **Skript** - 스크립트 시스템

## 플러그인 다운로드 및 설치 방법

### 자동 다운로드 스크립트 (Linux/Mac)
```bash
#!/bin/bash
# download-plugins.sh

# plugins 폴더 생성
mkdir -p plugins
cd plugins

# 참고: 실제 다운로드 링크는 각 사이트에서 직접 받아야 합니다
# 아래는 예시입니다

echo "플러그인을 수동으로 다운로드하여 plugins 폴더에 넣어주세요:"
echo "1. Vault.jar"
echo "2. PlaceholderAPI.jar"
echo "3. LuckPerms-Bukkit.jar"
echo "4. EssentialsX.jar"
echo "5. WorldEdit-bukkit.jar"
echo "6. WorldGuard-bukkit.jar"
echo "7. MythicLib.jar"
echo "8. MMOCore.jar"
echo "9. MythicMobs.jar"
echo "10. SaberFactions.jar"
echo "11. mcMMO.jar"
echo "12. CombatLogX.jar"
echo "13. Jobs.jar"
echo "14. Shopkeepers.jar"
echo "15. AuctionHouse.jar"
echo "16. BetonQuest.jar"
echo "17. EpicBosses.jar"
echo "18. DeluxeMenus.jar"
echo "19. Skript.jar"
```

### 수동 다운로드 방법
1. 각 플러그인의 다운로드 URL 방문
2. 1.21.1 또는 최신 버전 다운로드
3. `.jar` 파일을 `plugins/` 폴더에 복사
4. 서버 재시작

## 버전 호환성

### 최소 요구사항
- **Minecraft 버전**: 1.21.1
- **Java 버전**: Java 21 이상
- **서버 타입**: PaperMC (Spigot 호환)

### 플러그인 버전 권장사항
- **LuckPerms**: v5.4.x 이상
- **Vault**: v1.7.x 이상
- **EssentialsX**: v2.20.x 이상
- **MMOCore**: 1.12.x 이상
- **MythicMobs**: 5.6.x 이상 (Free 버전)
- **WorldGuard**: 7.0.x 이상
- **Skript**: 2.8.x 이상

## 선택적 플러그인 (추가 기능)

### 추천 플러그인
| 플러그인 | 용도 | URL |
|---------|------|-----|
| **ProtocolLib** | 패킷 처리 (일부 플러그인에서 사용) | https://www.spigotmc.org/resources/protocollib.1997/ |
| **Citizens** | NPC 생성 (BetonQuest와 연동) | https://www.spigotmc.org/resources/citizens.13811/ |
| **HolographicDisplays** | 홀로그램 표시 | https://dev.bukkit.org/projects/holographic-displays |
| **LuckPerms Web Editor** | 웹 기반 권한 편집 | 내장 기능 (`/lp editor`) |

### 성능 최적화 플러그인
| 플러그인 | 용도 | URL |
|---------|------|-----|
| **ClearLag** | 자동 엔티티 정리 | https://www.spigotmc.org/resources/clearlagg.68271/ |
| **LaggRemover** | 렉 제거 | https://www.spigotmc.org/resources/lagg-remover.59799/ |

## 데이터베이스 설정 참고

모든 플러그인은 **파일 기반 저장(YAML/JSON)**을 사용합니다.

### LuckPerms
```yaml
storage-method: yaml
```

### mcMMO
```yaml
# config.yml
MySQL:
  Enabled: false
```

### Jobs Reborn
```yaml
storage-method: sqlite
# 또는
storage-method: h2
```

### SaberFactions
기본적으로 JSON 파일 저장 사용

## 문제 해결

### 플러그인 의존성 오류
- "Could not load plugin X" 메시지가 나타나면:
  1. 의존성 플러그인이 설치되었는지 확인
  2. 서버 로그에서 정확한 오류 메시지 확인
  3. 플러그인 버전이 1.21.1과 호환되는지 확인

### 플러그인 충돌
- 비슷한 기능을 하는 플러그인이 충돌할 수 있습니다
- 예: Factions 계열 플러그인 여러 개 동시 사용 금지

### 업데이트
```bash
# 플러그인 업데이트 시
# 1. 서버 중지
# 2. 기존 .jar 파일 백업
# 3. 새 버전 .jar 파일로 교체
# 4. 서버 재시작
```

## 추가 리소스

### 공식 문서
- **PaperMC**: https://docs.papermc.io/
- **LuckPerms**: https://luckperms.net/wiki
- **MMOCore**: https://gitlab.com/phoenix-dvpmt/mmocore/-/wikis/home
- **MythicMobs**: https://git.mythiccraft.io/mythiccraft/MythicMobs/-/wikis/home
- **BetonQuest**: https://docs.betonquest.org/
- **Skript**: https://docs.skriptlang.org/

### 커뮤니티
- **SpigotMC 포럼**: https://www.spigotmc.org/
- **PaperMC Discord**: https://discord.gg/papermc
- **한국 마인크래프트 커뮤니티**: 각 커뮤니티 포럼

---

**마지막 업데이트**: 2026-01-08
