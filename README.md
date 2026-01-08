# Mineage Hybrid 서버 (리니지 클래식 + 현대 하이브리드 스타일)

## 서버 개요
**Mineage Hybrid**는 리니지 클래식의 감성과 마인크래프트의 재미를 결합한 하이브리드 RPG 서버입니다.

- **서버 버전**: PaperMC 1.21.1 (최신 빌드)
- **데이터베이스**: 사용하지 않음 (모든 데이터는 YAML/JSON 파일로 저장)
- **화폐 단위**: 아데나
- **최대 레벨**: 99

## 주요 특징

### 1. 클래스 시스템
- 기사 (Knight)
- 워리어 (Warrior)
- 마법사 (Mage)
- 요정 (Elf)
- 다크엘프 (Dark Elf)
- 최대 레벨 99, 전직 시스템 포함

### 2. 리니지 스타일 몹
- 오크 (Orc)
- 트롤 (Troll)
- 스켈레톤 솔져 (Skeleton Soldier)
- 웨어울프 (Werewolf)
- 드레이크 (Drake)

### 3. 혈맹 시스템
- 혈맹 생성 및 관리
- 혈맹전 선언
- 영지 점령
- 혈맹 랭킹 1위 특전 (AFK 존 XP 2배 버프)

### 4. PvP & PK 시스템
- PvP 전용 구역 설정
- PK 시 일정 확률로 강화 아이템 드랍
- 전투 중 로그아웃 방지

### 5. AFK 자동사냥 존
- AFK 상태에서 자동 몹 스폰 및 사냥
- 24시간 제한 시스템

### 6. 아이템 강화 시스템
- +1~+7: 80% 성공률
- +8~+10: 30% 성공률
- +11 이상: 5% 성공률
- 실패 시 아이템 파괴 위험

### 7. 가챠 시스템
- `/가챠` 명령어로 실행
- 에픽 아이템 1% 확률

### 8. 경제 시스템
- NPC 상점
- 경매 시스템
- 직업 시스템 (채광사, 어부, 사냥꾼 등)

### 9. 이벤트
- 주간 보스 레이드
- 월드 보스
- 성 점령전

### 10. 랭킹 시스템
- `/랭킹` 명령어로 확인
- 킬수 및 레벨 상위 10명 표시

## 서버 설치 가이드

### 1단계: Java 설치
```bash
# Java 21 이상 필요
sudo apt update
sudo apt install openjdk-21-jdk
java -version
```

### 2단계: PaperMC 서버 다운로드
```bash
# 서버 디렉토리 생성
mkdir mineage-server
cd mineage-server

# PaperMC 1.21.1 다운로드
# https://papermc.io/downloads/paper 에서 최신 빌드 다운로드
wget https://api.papermc.io/v2/projects/paper/versions/1.21.1/builds/latest/downloads/paper-1.21.1-latest.jar -O paper.jar
```

### 3단계: 초기 서버 실행 (EULA 동의)
```bash
# 첫 실행
java -Xmx4G -Xms2G -jar paper.jar --nogui

# EULA 동의
echo "eula=true" > eula.txt
```

### 4단계: 플러그인 설치
모든 플러그인을 `plugins/` 폴더에 다운로드하세요. 자세한 플러그인 목록은 `PLUGIN_LIST.md`를 참고하세요.

```bash
# plugins 폴더로 플러그인 파일들 복사
mkdir -p plugins
# 각 플러그인 jar 파일을 plugins 폴더에 넣기
```

### 5단계: 설정 파일 복사
이 저장소의 `plugins/` 폴더 전체를 서버의 `plugins/` 폴더에 덮어쓰기 하세요.

```bash
# 이 저장소를 클론한 경우
cp -r /path/to/rinijl/plugins/* /path/to/mineage-server/plugins/
```

### 6단계: 서버 시작
```bash
# 서버 시작 스크립트
java -Xmx4G -Xms2G -jar paper.jar --nogui
```

또는 `start.sh` 스크립트를 생성:
```bash
#!/bin/bash
java -Xmx4G -Xms2G -jar paper.jar --nogui
```

권한 부여 후 실행:
```bash
chmod +x start.sh
./start.sh
```

### 7단계: 관리자 권한 설정
서버 콘솔에서:
```
op <당신의_닉네임>
```

또는 LuckPerms를 통해:
```
lp user <닉네임> parent set admin
```

## 서버 관리 명령어

### 기본 명령어
- `/가챠` - 가챠 시스템 실행
- `/랭킹` - 킬수/레벨 랭킹 확인
- `/전직` - 클래스 전직
- `/강화` - 아이템 강화

### 혈맹 관련
- `/f create <혈맹명>` - 혈맹 생성
- `/f join <혈맹명>` - 혈맹 가입
- `/f leave` - 혈맹 탈퇴
- `/f claim` - 영지 점령

### 관리자 명령어
- `/mm mobs spawn <몹이름>` - MythicMobs 몹 소환
- `/mmocore admin class <플레이어> <클래스>` - 클래스 설정
- `/rg define <지역명>` - WorldGuard 지역 정의
- `/jobs admin` - 직업 관리

## 서버 파일 구조
```
mineage-server/
├── paper.jar                    # PaperMC 서버 파일
├── plugins/                     # 플러그인 폴더
│   ├── LuckPerms/              # 권한 관리
│   ├── Vault/                  # 경제 API
│   ├── Essentials/             # 기본 명령어
│   ├── MMOCore/                # RPG 클래스 시스템
│   ├── MythicLib/              # MMO 라이브러리
│   ├── MythicMobs/             # 커스텀 몹
│   ├── SaberFactions/          # 혈맹 시스템
│   ├── Skript/                 # 스크립트 시스템
│   ├── WorldGuard/             # 지역 보호
│   ├── WorldEdit/              # 월드 에디트
│   ├── mcMMO/                  # 보조 스킬
│   ├── CombatLogX/             # 전투 로그아웃 방지
│   ├── PlaceholderAPI/         # 플레이스홀더
│   ├── Jobs/                   # 직업 시스템
│   ├── EpicBosses/             # 월드 보스
│   ├── BetonQuest/             # 퀘스트 시스템
│   ├── Shopkeepers/            # 상점 시스템
│   ├── AuctionHouse/           # 경매 시스템
│   └── DeluxeMenus/            # GUI 메뉴
├── world/                      # 메인 월드
├── world_nether/               # 네더 월드
├── world_the_end/              # 엔드 월드
└── server.properties           # 서버 기본 설정
```

## 문제 해결

### 플러그인이 로드되지 않는 경우
1. 플러그인 파일이 `.jar` 확장자인지 확인
2. 플러그인이 1.21.1 버전과 호환되는지 확인
3. 의존성 플러그인이 먼저 설치되었는지 확인
   - Vault → 경제 플러그인
   - PlaceholderAPI → 많은 플러그인에서 사용
   - WorldEdit → WorldGuard
   - MythicLib → MMOCore

### 데이터베이스 오류가 발생하는 경우
모든 플러그인은 파일 저장(YAML/JSON)을 사용하도록 설정되어 있습니다. 각 플러그인의 `config.yml`에서 다음 설정을 확인하세요:
- `storage-method: yaml` (또는 `h2`, `sqlite`)
- MySQL/MariaDB 관련 설정이 비활성화되어 있는지 확인

### 메모리 부족 오류
`start.sh` 또는 실행 명령어에서 메모리 할당을 늘리세요:
```bash
java -Xmx6G -Xms4G -jar paper.jar --nogui
```

## 추가 정보
- **플러그인 목록**: `PLUGIN_LIST.md` 참고
- **테스트 방법**: `TEST_COMMANDS.md` 참고
- **GitHub 저장소**: https://github.com/junggyeol4444/rinijl

## 라이선스
이 프로젝트는 개인 학습 및 비상업적 용도로 제공됩니다.

## 기여
버그 제보 및 개선 제안은 GitHub Issues를 통해 알려주세요.

---

**즐거운 모험 되세요! ⚔️**