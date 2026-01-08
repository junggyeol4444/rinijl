# Mineage Hybrid 서버 테스트 가이드

## 서버 설치 후 전체 테스트 방법

### 1단계: 서버 시작 확인

#### 서버 실행
```bash
java -Xmx4G -Xms2G -jar paper.jar --nogui
```

#### 확인사항
- [ ] 서버가 정상적으로 시작됨
- [ ] 모든 플러그인이 로드됨 (콘솔에서 확인)
- [ ] 에러 메시지가 없음

#### 로그 확인 명령어
```bash
# 서버 로그 보기
tail -f logs/latest.log
```

---

### 2단계: 기본 시스템 테스트

#### 플러그인 로드 확인
서버 콘솔 또는 게임 내 명령어:
```
/plugins
```

**확인할 플러그인 목록:**
- [x] Vault
- [x] LuckPerms
- [x] EssentialsX
- [x] PlaceholderAPI
- [x] MMOCore
- [x] MythicLib
- [x] MythicMobs
- [x] SaberFactions
- [x] WorldGuard
- [x] WorldEdit
- [x] mcMMO
- [x] CombatLogX
- [x] Jobs
- [x] Shopkeepers
- [x] AuctionHouse
- [x] BetonQuest
- [x] EpicBosses
- [x] DeluxeMenus
- [x] Skript

#### 권한 시스템 테스트
```bash
# 서버 콘솔에서
op <당신의_닉네임>

# 또는 LuckPerms 사용
lp user <닉네임> parent set admin
```

---

### 3단계: RPG 클래스 시스템 테스트

#### 클래스 확인
게임 내에서:
```
/mmocore class list
```

**확인할 클래스:**
- [ ] knight (기사)
- [ ] warrior (워리어)
- [ ] mage (마법사)
- [ ] elf (요정)
- [ ] darkelf (다크엘프)

#### 클래스 선택 테스트
```
/mmocore class choose knight
```

#### 레벨업 테스트
```bash
# 관리자 명령어로 경험치 추가
/mmocore admin experience add <플레이어> 1000
```

#### 스탯 확인
```
/mmocore stats
```

---

### 4단계: MythicMobs 커스텀 몹 테스트

#### 몹 목록 확인
```
/mm mobs list
```

**확인할 몹:**
- [ ] orc (오크)
- [ ] troll (트롤)
- [ ] skeleton_soldier (스켈레톤 솔져)
- [ ] werewolf (웨어울프)
- [ ] drake (드레이크)

#### 몹 소환 테스트
```bash
# 각 몹을 소환하여 테스트
/mm mobs spawn orc 1
/mm mobs spawn troll 1
/mm mobs spawn skeleton_soldier 1
/mm mobs spawn werewolf 1
/mm mobs spawn drake 1
```

#### 몹 처치 후 확인사항
- [ ] 아데나(돈) 드랍 확인: `/bal` 또는 `/money`
- [ ] MMOCore 경험치 획득 확인: `/mmocore stats`
- [ ] 아이템 드랍 확인

---

### 5단계: 경제 시스템 테스트

#### 화폐 확인
```bash
# 현재 잔액 확인
/bal
/money
```

#### 아데나 지급 테스트
```bash
# 관리자 명령어
/eco give <플레이어> 10000
```

#### 화폐 단위 확인
- [ ] 화폐 이름이 "아데나"로 표시되는지 확인

---

### 6단계: 혈맹 시스템 테스트

#### 혈맹 생성
```bash
/f create 테스트혈맹
```

#### 혈맹 정보 확인
```bash
/f show
/f list
```

#### 영지 점령
```bash
# 원하는 위치에서
/f claim
```

#### 혈맹 초대
```bash
/f invite <플레이어명>
```

---

### 7단계: Skript 스크립트 테스트

#### 스크립트 목록 확인
```bash
/sk scripts
```

**확인할 스크립트:**
- [ ] afk-hunting.sk (AFK 자동사냥)
- [ ] gacha.sk (가챠 시스템)
- [ ] enchant-system.sk (강화 시스템)
- [ ] ranking.sk (랭킹 시스템)
- [ ] weekly-boss-event.sk (주간 보스 이벤트)
- [ ] pk-system.sk (PK 시스템)
- [ ] bloodalliance-buff.sk (혈맹 버프)

#### 스크립트 리로드
```bash
/sk reload all
```

#### 가챠 시스템 테스트
```bash
/가챠
```
- [ ] GUI 메뉴가 열리는지 확인
- [ ] 가챠 아이템이 나오는지 확인

#### 랭킹 시스템 테스트
```bash
/랭킹
```
- [ ] 킬수 랭킹 표시
- [ ] 레벨 랭킹 표시

#### 강화 시스템 테스트
```bash
# 손에 아이템을 들고
/강화
```
- [ ] 강화 성공/실패 메시지 확인
- [ ] 강화 수치가 아이템에 표시되는지 확인

---

### 8단계: 월드 가드 지역 설정 테스트

#### 지역 생성
```bash
# WorldEdit으로 영역 선택
//wand
# 두 지점 선택 후

# 지역 정의
/rg define spawn
/rg define pvp_zone
/rg define afk_zone
```

#### 지역 플래그 설정

##### 안전존 (스폰)
```bash
/rg flag spawn pvp deny
/rg flag spawn mob-spawning deny
```

##### PvP 존
```bash
/rg flag pvp_zone pvp allow
```

##### AFK 존
```bash
/rg flag afk_zone pvp deny
```

---

### 9단계: mcMMO 스킬 테스트

#### mcMMO 상태 확인
```bash
/mcstats
```

#### 스킬 레벨업 테스트
- [ ] 나무 캐기 → 나무꾼 스킬 증가
- [ ] 광석 캐기 → 채광 스킬 증가
- [ ] 몹 처치 → 검술 스킬 증가

---

### 10단계: Jobs Reborn 직업 테스트

#### 직업 목록 확인
```bash
/jobs browse
```

#### 직업 가입
```bash
/jobs join Miner
/jobs join Hunter
/jobs join Fisherman
```

#### 직업 진행도 확인
```bash
/jobs stats
```

---

### 11단계: 상점 시스템 테스트

#### Shopkeepers 테스트
```bash
# NPC 상점 생성
/shopkeeper
```

#### AuctionHouse 테스트
```bash
# 경매 GUI 열기
/ah
/auctionhouse

# 아이템 등록
/ah sell <가격>
```

---

### 12단계: 퀘스트 시스템 테스트

#### BetonQuest 확인
```bash
# 퀘스트 목록 (설정에 따라 다름)
/quests
/journal
```

---

### 13단계: 전투 시스템 테스트

#### CombatLogX 테스트
1. 몹 또는 플레이어와 전투 시작
2. 전투 태그 메시지 확인
3. 전투 중 로그아웃 시도
   - [ ] 로그아웃 방지 메시지 확인

#### PK 시스템 테스트
1. 다른 플레이어 공격 (PvP 존에서)
2. 플레이어 처치
   - [ ] 강화 아이템 드랍 확률 확인
   - [ ] PK 기록 확인

---

### 14단계: 이벤트 시스템 테스트

#### EpicBosses 월드 보스
```bash
# 보스 스폰 (관리자)
/boss spawn <보스명>
```

#### 주간 보스 이벤트 (Skript)
- [ ] 스크립트가 정해진 시간에 실행되는지 확인
- [ ] 보스 소환 메시지 확인

---

### 15단계: 통합 기능 테스트

#### MythicMobs → MMOCore 경험치 연동
1. MythicMobs 몹 처치
2. MMOCore 경험치 획득 확인
   ```
   /mmocore stats
   ```

#### 혈맹 랭킹 버프 테스트
1. 혈맹 랭킹 1위 확인
   ```
   /f top
   ```
2. AFK 존에서 몹 처치
3. 경험치 2배 획득 확인

#### AFK 자동사냥 테스트
1. AFK 존으로 이동
2. 5분간 AFK 상태 유지
3. 자동으로 몹 스폰 확인
4. 24시간 제한 확인

---

### 16단계: 가챠 & 강화 통합 테스트

#### 가챠로 아이템 획득
```bash
/가챠
```

#### 획득한 아이템 강화
```bash
/강화
```

#### 강화 확률 검증
- [ ] +1~+7: 여러 번 시도하여 약 80% 성공률 체감
- [ ] +8~+10: 30% 성공률 체감
- [ ] +11 이상: 5% 성공률 체감

---

### 17단계: 성능 테스트

#### 서버 TPS 확인
```bash
/tps
```
- [ ] TPS가 20 근처인지 확인 (정상)

#### 메모리 사용량 확인
```bash
# 서버 콘솔에서
/spark profiler start
# 1분 대기
/spark profiler stop
```

---

## 자동화 테스트 스크립트

### 기본 테스트 스크립트 (test-server.sh)
```bash
#!/bin/bash

echo "=== Mineage Hybrid 서버 테스트 시작 ==="

# 1. 서버 시작 확인
echo "[1/5] 서버 프로세스 확인..."
if pgrep -f "paper.jar" > /dev/null; then
    echo "✓ 서버 실행 중"
else
    echo "✗ 서버가 실행되지 않음"
    exit 1
fi

# 2. 플러그인 폴더 확인
echo "[2/5] 플러그인 폴더 확인..."
if [ -d "plugins/MMOCore" ] && [ -d "plugins/MythicMobs" ]; then
    echo "✓ 핵심 플러그인 폴더 존재"
else
    echo "✗ 플러그인 폴더 누락"
    exit 1
fi

# 3. 설정 파일 확인
echo "[3/5] 설정 파일 확인..."
if [ -f "plugins/LuckPerms/config.yml" ] && [ -f "plugins/Essentials/config.yml" ]; then
    echo "✓ 기본 설정 파일 존재"
else
    echo "✗ 설정 파일 누락"
    exit 1
fi

# 4. Skript 스크립트 확인
echo "[4/5] Skript 스크립트 확인..."
SCRIPT_COUNT=$(find plugins/Skript/scripts -name "*.sk" 2>/dev/null | wc -l)
if [ "$SCRIPT_COUNT" -ge 5 ]; then
    echo "✓ Skript 파일 $SCRIPT_COUNT 개 발견"
else
    echo "⚠ Skript 파일이 예상보다 적음: $SCRIPT_COUNT 개"
fi

# 5. 로그 오류 확인
echo "[5/5] 최근 로그 오류 확인..."
if [ -f "logs/latest.log" ]; then
    ERROR_COUNT=$(grep -i "error\|exception" logs/latest.log | wc -l)
    if [ "$ERROR_COUNT" -eq 0 ]; then
        echo "✓ 오류 없음"
    else
        echo "⚠ $ERROR_COUNT 개의 오류 발견"
        echo "최근 오류:"
        grep -i "error\|exception" logs/latest.log | tail -5
    fi
else
    echo "⚠ 로그 파일 없음"
fi

echo ""
echo "=== 테스트 완료 ==="
```

### 권한 부여 및 실행
```bash
chmod +x test-server.sh
./test-server.sh
```

---

## 문제 해결

### 플러그인이 로드되지 않는 경우
```bash
# 로그 확인
tail -100 logs/latest.log | grep -i "error\|exception"
```

### 명령어가 작동하지 않는 경우
1. 권한 확인: `/lp user <닉네임> permission check <권한>`
2. 플러그인 활성화 확인: `/plugins`
3. 스크립트 오류 확인: `/sk reload all`

### 경험치/돈이 획득되지 않는 경우
1. Vault 연동 확인
2. MMOCore 설정 확인: `plugins/MMOCore/config.yml`
3. MythicMobs 드랍 설정 확인: `plugins/MythicMobs/Mobs/*.yml`

---

## 최종 체크리스트

### 관리자 확인사항
- [ ] 모든 플러그인이 정상 로드됨
- [ ] 5개 클래스가 모두 사용 가능
- [ ] 5개 커스텀 몹이 소환 가능
- [ ] 혈맹 생성 및 관리 가능
- [ ] 가챠 시스템 작동
- [ ] 강화 시스템 작동
- [ ] 랭킹 시스템 표시
- [ ] AFK 자동사냥 작동
- [ ] PK 시스템 작동
- [ ] 혈맹 버프 시스템 작동
- [ ] 경제 시스템(아데나) 정상 작동
- [ ] WorldGuard 지역 설정 완료
- [ ] 서버 TPS 20 유지

### 플레이어 확인사항
- [ ] 회원가입 및 로그인 가능
- [ ] 클래스 선택 가능
- [ ] 몹 사냥 시 경험치 및 돈 획득
- [ ] 혈맹 가입/생성 가능
- [ ] 상점 이용 가능
- [ ] PvP 참여 가능
- [ ] 가챠 이용 가능
- [ ] 강화 이용 가능

---

**테스트 완료 후 서버를 공개할 준비가 되었습니다! 🎮**
