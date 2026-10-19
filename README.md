<div align="center">

<!-- 📷 표시된 src="..." 부분을 GitHub에 올린 이미지 주소로 바꿔야함. (Ctrl+F로 "📷" 검색) -->

# <img src="https://github.com/user-attachments/assets/76cfa072-70b9-40ba-a273-e2aa5743b24b" height="40" align="absmiddle" /> 나침발 : AI HAPTIC RUNNING BAND
**AI HAPTIC RUNNING BAND & 앱**

`2026 한이음 드림업 공모전` · `26_HF026` · `Team Axis`

</div>

---

## **💡1. 프로젝트 개요**

**1-1. 프로젝트 소개**
- 프로젝트 명 : 나침발 (AI HAPTIC RUNNING BAND)
- 프로젝트 정의 : 러닝 중 화면을 보지 않고도 경로 안내와 운동 피드백을 받을 수 있는 **좌·우 분리형 햅틱 기반 스마트 러닝 밴드**와 이를 연동하는 모바일 앱
- 스마트폰과 좌·우 손목 밴드를 BLE 통신으로 연결하여 **방향 전환, 경로 이탈, 페이스 조절** 정보를 진동으로 전달하고, 페이스 조절 및 GPS 아트 기능을 함께 제공합니다.

**1-2. 개발 배경 및 필요성**
- **기존 러닝 서비스의 구조적 한계에 따른 필요성**
  - GRONORUN 연구(BMC Musculoskeletal Disorders, 2010)에 따르면 러닝 부상의 60% 이상이 훈련(페이스) 오류에서 비롯됩니다. 그러나 기존 러닝 앱·스마트워치는 수치를 화면에 보여주는 데 그쳐, 목표 페이스를 벗어나도 능동적으로 교정해 주지 않습니다.
- **설문조사를 통한 필요성 검증**
  - 러너 23명을 대상으로 온라인 설문을 진행한 결과

<div align="center">
  
| 설문 항목 | 결과 |
|:---|:---:|
| 러닝 중 페이스 조절에 어려움을 겪은 경험 | **약 87%** |
| 경로 안내를 화면·소리에 의존하는 비율 | **약 80%** |
| 화면 확인·이어폰 사용으로 위험하거나 불편했던 경험 | **약 52%** |
| 나침발 주요 기능에 대한 기대(리커트 5점 척도 평균) | **4.41 / 5.0** |
</div>

→ **손목 진동만으로 경로와 페이스를 안내하는 러닝 보조 시스템**이 필요하다는 것을 확인하고, 설문과 인터뷰 결과를 기능 설계에 직접 반영했습니다.

**1-3. 프로젝트 특장점**
- **좌·우 분리형 햅틱 경로 안내** : 왼손이 울리면 좌회전, 오른손이 울리면 우회전. 단일 기기(스마트워치)로는 어려운 직관적인 방향 구분을 제공합니다.
- **AI 기반 능동적 페이스 교정** : 수치를 보여주는 데 그치지 않고, 실시간 분석한 이상적인 페이스를 진동으로 전달해 능동적으로 부상 위험을 낮추고 러닝 목표 달성에 기여합니다.
- **경유지 기반 맞춤 경로 생성** : 사용자가 지도에서 지정한 경유지를 연결해 운동 가능한 맞춤 경로를 생성합니다. 생성된 경로는 재사용할 수 있으며, GPS 아트와 같은 재미 요소도 제공합니다.
- **실시간 대응 가능성 강화** : 화면 확인이 전제된 기본 서비스와 달리, 나침발은 진동만으로 방향·페이스·경로 이탈 정보를 즉시 전달하여 시선 분산없이 상황에 빠르게 대응할 수 있도록 합니다.

**1-4. 주요 기능**
<div align="center">
  
| 기능 | 설명 |
|:---|:---|
| 🔗 **햅틱 밴드 연동 및 상태 관리** |좌/우 밴드 동시 탐색·연결 및 연결 상태 실시간 확인. 런타임 안정성 관리 수행 |
| 🧭 **햅틱 러닝 경로 안내** | 러닝 경로를 생성하고, 회전 지점 전 좌/우 손목 진동으로 방향 안내. 경로 이탈 시 양손 진동 경고, 도착 시 완료 진동 및 운동 기록 표시 |
| 🤖 **AI 페이스 조절** | 운동 중 심박수·속도 등 운동 데이터를 주기적으로 수집하여 오버페이스·언더페이스 상태를 판단 후 현재 이상적인 페이스 산출. 페이스 이탈 시 케이던스 기반 햅틱 피드백을 정상 페이스 복귀 전까지 지속 전송. |
| ⏱️ **목표 페이스 메이커** | 입력 목표 페이스 기준 페이스 이탈 시 워밍업, 러닝, 쿨다운 구간에 맞는 햅틱 전송. |
| 📊 **운동 데이터 기록 및 시각화** | 러닝 결과(거리·시간·속도·심박수·칼로리·페이스 조절 횟수) 및 SNS 공유, 러닝 완료 후 평균 운동 시간·거리·속도·최대/최저 심박수와 최고 기록을 누적 집계하여 시각화. 주간·월간 목표 및 달성 진행률, 러닝 스트릭 확인 가능.  |
| 💬 **AI 러닝 코치 챗봇** | 누적 러닝 데이터를 주/월 단위 통계로 요약해 OpenAI API에 전달, 분석·훈련 계획 등 사용자 질문에 맞춤 응답 |
| 🗺️ **경로 생성 및 MY 경로 아카이빙** | 지도에서 경유지(Waypoint)를 지정하면 T-map 보행자 API로 경로 생성, MY 경로 저장·즐겨찾기, GPS 아트 명소 조회 |
| 🎨 **GPS 아트 경로 자동 생성** | 알고리즘을 통해 하트, 다각형 등 모양을 가진 GPS 아트 경로를 자동으로 생성. |
</div>

**🔔 진동 패턴**
<div align="center">
  
| 상황 | 왼손 | 오른손 | 패턴 |
|:---:|:---:|:---:|:---|
| ⬅️ 좌회전 | ● | | 3회 진동 |
| ➡️ 우회전 | | ● | 3회 진동 |
| ⚠️ 경로 이탈 | ● | ● | 양손 2회 진동 |
| 🏁 도착 | ● | ● | 양손 길게 1회 진동 |
| 🏃 페이스 조절 | ● | ● | 목표 케이던스(SPM)에 맞춘 리듬 진동 |
</div>

**📱 앱 화면**

<p align="center">
  <img src="https://github.com/user-attachments/assets/df38c314-0f97-42e5-bbcc-4af526684171" height="270" alt="스캔연동" />
  <img src="https://github.com/user-attachments/assets/6fb4f74b-a55a-400e-9057-d46b25cd5835" height="270" alt="진동패턴" />
  <img src="https://github.com/user-attachments/assets/e2023b7e-2f5f-48c7-a8e8-839896ce6e4b" height="270" alt="로그인" />
  <img src="https://github.com/user-attachments/assets/80c2f7d0-52db-4d73-abf8-9ecc5f2a69b3" height="270" alt="홈" />
  <img src="https://github.com/user-attachments/assets/e88fecd7-b36e-4bfb-b95b-a997a3d7a8df" height="270" alt="경로 생성" />
</p>
<p align="center"><sub>밴드스캔 ·  진동패턴 · 로그인 · 홈 · 경로 생성</sub></p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/b25fc93d-85bb-4636-b00f-95a7a1d8aabe" height="270" alt="러닝 안내" />
  <img src="https://github.com/user-attachments/assets/b8dcee1a-67b6-48a2-b120-8ccea10aee02" height="270" alt="러닝 결과" />
  <img src="https://github.com/user-attachments/assets/09e33738-f729-4fcf-bd48-466254b384f6" height="270" alt="GPS 아트 생성" />
  <img src="https://github.com/user-attachments/assets/482eb9ab-4d98-4063-a2ff-1214afc1f632" height="270" alt="GPS 아트 명소" />
  <img src="https://github.com/user-attachments/assets/88e64d46-70f0-4a14-b10b-66ff6eaec8de" height="270" alt="아카이브" />
</p>
<p align="center"><sub>러닝 안내 · 러닝 결과 · GPS 아트 생성 · GPS 아트 명소 · 아카이브</sub></p>

**1-5. 기대 효과 및 활용 분야**
- 기대 효과
  - 직관적이고 몰입감 있는 러닝 경험 지원
  - 비시각적 인터페이스 기반 안전성 향상
  - AI 기반 페이스 조절을 통한 부상 예방 효과
  - 개인 맞춤형 러닝 가이드 제공
  - 기록·시각화·GPS 아트를 통한 지속적인 운동 동기부여
  - 저비용 실용화 가능성
- 활용 분야
  - 스마트 퍼스널 러닝 코칭 서비스
  - 비시각 인터페이스 기반 안전 러닝 서비스
  - 러닝 콘텐츠 및 커뮤니티 플랫폼 서비스
  - 러닝 특화 웨어러블 디바이스 산업 활용

**1-6. 기술 스택**

| 분야 | 기술 |
|:---:|:---|
| **Frontend** | ![React Native](https://img.shields.io/badge/React_Native-61DAFB?style=flat-square&logo=react&logoColor=black) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![Android](https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=android&logoColor=white) |
| **Backend** | ![Spring Boot](https://img.shields.io/badge/Spring_Boot_3.5-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![Java](https://img.shields.io/badge/Java_21-007396?style=flat-square&logo=openjdk&logoColor=white) ![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white) |
| **AI** | ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white) ![OpenAI](https://img.shields.io/badge/OpenAI_API-412991?style=flat-square&logo=openai&logoColor=white) |
| **Database / Cloud** | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![Amazon RDS](https://img.shields.io/badge/Amazon_RDS-527FFF?style=flat-square&logo=amazonrds&logoColor=white) ![Amazon S3](https://img.shields.io/badge/Amazon_S3-569A31?style=flat-square&logo=amazons3&logoColor=white) ![Amazon EC2](https://img.shields.io/badge/Amazon_EC2-FF9900?style=flat-square&logo=amazonec2&logoColor=white) |
| **Hardware** | ![ESP32](https://img.shields.io/badge/ESP32--C3-E7352C?style=flat-square&logo=espressif&logoColor=white) ![Arduino](https://img.shields.io/badge/Arduino_IDE-00878F?style=flat-square&logo=arduino&logoColor=white) ![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white) ![Bluetooth](https://img.shields.io/badge/BLE-0082FC?style=flat-square&logo=bluetooth&logoColor=white) |
| **외부 API** | T-map Pedestrian API, 네이버 지도 SDK, NCP Maps API(Reverse Geocoding), OpenStreetMap(Overpass API), OpenAI API(GPT-5.5), 기상청 초단기실황 API |
| **협업** | ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white) ![Jira](https://img.shields.io/badge/Jira-0052CC?style=flat-square&logo=jira&logoColor=white) ![Notion](https://img.shields.io/badge/Notion-000000?style=flat-square&logo=notion&logoColor=white) ![Figma](https://img.shields.io/badge/Figma-F24E1E?style=flat-square&logo=figma&logoColor=white) ![Discord](https://img.shields.io/badge/Discord-5865F2?style=flat-square&logo=discord&logoColor=white) |

---

## **💡2. 팀원 소개(이름 기재X)**

<div align="center">

| <img width="80" height="80" src="https://github.com/mj12130.png" > | <img width="80" height="80" src="https://github.com/dalpaeng6.png" > | <img width="80" height="80" src="https://github.com/jujukim00.png" > | <img width="80" height="80" src="https://github.com/ssxbin.png" > | <img width="80" height="80" src="https://github.com/Jiae.png" > |
|:---:|:---:|:---:|:---:|:---:|
| **멘티1** | **멘티2** | **멘티3** | **멘티4** | **멘티5** |
| PM · FE · BE <br> HW <br> UI/UX 기획 | FE · BE <br> UI/UX 기획 | FE · BE <br> UI/UX 기획 | FE · BE <br> UI/UX 기획 | AI <br> 3D 모델링 <br> UI/UX 기획 |
</div>

## **💡3. 시스템 구성도**

**3-1. 서비스 구성도**

<p align="center"><img src="https://github.com/user-attachments/assets/ec86a517-315b-4863-956e-bb94db79ec66" width="560" alt="S/W 구성도" /></p>

**3-2. H/W 구성도**

<p align="center"><img src="https://github.com/user-attachments/assets/f69105c4-f0f6-4d08-b9fc-4a48e8a9aa1a" width="600" alt="H/W 회로 구성도" /></p>

> 좌·우 밴드 ESP32-C3, DRV2605L, MAX30102를 하나의 회로로 통합해 독립적으로 구동하며, 러닝 중 착용 부담이 없도록 **경량화·소형화**에 중점을 두었습니다.

**3-3. 서비스 흐름도**

<p align="center"><img src="https://github.com/user-attachments/assets/2e5d5ee3-39c4-4a80-8922-8a5c73c0bdca" width="760" alt="서비스 흐름도" /></p>

**3-4. AI 페이스 조절 알고리즘**

```
[러닝 시작] BE 서버 → AI 서버 : 세션 아이디 · 안정 심박수 · 나이 · 예상 운동 시간 전달
     │
     ▼  (러닝 중 5초 간격)
BE 서버 → AI 서버 : 최근 120초치 심박수 · 속도 · 경과 시간 · 고도 배열 전송
     │
     ▼
AI : 파생 피처 5개(hrr_pct, delta_hrr_pct, time_ratio, speed_trend, fatigue_index) 계산
     + 원본 피처(speed, heart_rate) → 총 7개 피처(FEATURE_COLUMNS) 구성
     │
     ▼
TCN 모델 → 현재 러닝 상태를 OVER / NORMAL / UNDER 중 하나로 분류
     │
     ▼  (5초 간격)
AI 서버 → BE 서버 : 라벨과 이상적인 페이스 값 반환
     │
     ├─ NORMAL ─────────► 피드백 없이 다음 주기 대기
     └─ OVER / UNDER ───► 규칙 기반 레이어가 이상적인 페이스 수치를 산출해 조정 방향과 강도 결정
                          → 결정된 방향에 따라 디바이스로 햅틱 피드백 전송
     │
     ▼
러닝 종료 전까지 반복 → 종료 시 평균 운동 기록과 페이스 조절 결과를 서버에 저장
```

**3-5. GPS 아트 경로 자동 생성 알고리즘**
1. **도로망 그래프 구성** : OpenStreetMap(Overpass API)의 실제 보행자 도로망 데이터를 OSMnx로 그래프 구조로 변환합니다.
2. **폐곡선 후보 탐색** : 그래프 안에 실제로 존재하는 순환 경로(폐곡선) 후보를 탐색합니다.
3. **형태 유사도 매칭** : 각 후보의 회전각·변 길이 비율 시퀀스를 목표 도형의 시퀀스와 **DTW(Dynamic Time Warping)** 로 비교해 가장 유사한 경로를 자동 선정합니다.
4. **재현성·응답 속도 확보** : 노드와 엣지를 항상 정렬된 순서로 삽입해 같은 입력에 같은 결과가 나오도록 하고, 자주 요청되는 지역의 그래프를 미리 캐싱해 응답 지연을 줄였습니다.

**3-6. 엔티티 관계도 (ERD)**

<p align="center"><img src="https://github.com/user-attachments/assets/ee58c485-d105-4bc9-a81c-55d53ed9c469" width="760" alt="ERD" /></p>

`users` · `routes` · `route_favorites` · `waypoints` · `exercise_sessions` · `exercise_results` · `running_streaks` · `challenge_goals`

---

## **💡4. 작품 소개영상**

> 🎬 작품 소개영상입니다

<p align="center">
  <a href="https://www.youtube.com/watch?v=2wY3_pB0_G4">
    <img src="https://img.youtube.com/vi/2wY3_pB0_G4/0.jpg" width="640" alt="나침발 : 스마트 러닝 밴드 소개" />
  </a>
</p>
<p align="center"><sub>▶ 이미지를 누르면 유튜브에서 작품 소개영상을 볼 수 있습니다</sub></p>

---

## **💡5. 핵심 소스코드**

**5-1. 햅틱 경로 안내 로직 (Frontend · JavaScript)**
  - **도착 판정** : 마지막 구간에서 목적지 반경 안에 들어오면 이탈 판정보다 먼저 도착 처리합니다.
  - **다음 회전 포인트(구간) 진입** : 단순히 반경 안에 들어왔는지만 보지 않고, 현재 지점보다 다음 지점이 더 가까워졌는지(방향성)까지 함께 확인해 오탐을 막습니다.
  - **이탈 확정** : 경로와의 최소 거리가 기준치를 **연속 3회** 넘을 때만 이탈로 확정해, 순간적인 GPS 오차에도 안내가 끊기지 않도록 했습니다.

```javascript
// 1. 도착 판정 : 목적지 반경 이내 진입 시 이탈 판정 없이 최우선으로 도착 처리
const lastStep      = this.steps[this.steps.length - 1];
const isLastSegment = this.segmentIndex >= this.steps.length - 2;
const distToArrival = haversine(lat, lng, lastStep.pointY, lastStep.pointX);

if (isLastSegment && distToArrival < this.noticeRadius) {
  return { isDeviated: false, currentSegmentIndex: this.segmentIndex, isArrived: true };
}

// 2. 다음 회전 포인트(구간) 진입 : "반경 진입 + 가까워지는 방향성"을 함께 확인
const currentStep = this.steps[this.segmentIndex];
const nextStep    = this.steps[this.segmentIndex + 1];

if (nextStep) {
  const distToNext = haversine(lat, lng, nextStep.pointY, nextStep.pointX);

  // 다음 포인트 진입 체크 -> prevDistToNext와 비교해 "이전보다 가까워지고 있는가"로 판단
  const approaching =
    this.prevDistToNext === null || distToNext < this.prevDistToNext;

  const distToCurrent = haversine(lat, lng, currentStep.pointY, currentStep.pointX);

  if (distToNext < this.noticeRadius && distToCurrent > distToNext) {
    this.segmentIndex += 1;
    this.deviationCount = 0;
    this.prevDistToNext = null;
    this.distanceIncreaseCount = 0;
    // ...
  }
}

// 3. 이탈 확정 : 경로와의 최소 거리가 기준치를 연속 3회 초과할 때만 이탈로 확정
if (minDist > this.deviationThreshold) {
  this.deviationCount += 1;
  if (this.deviationCount >= this.consecutiveRequired) { // 3회 이상 감지 시 이탈 확정
    this.isCurrentlyDeviated = true;
    // deviationCount 리셋 안 함 → 이탈 상태 유지
    return { isDeviated: true, currentSegmentIndex: this.segmentIndex, isArrived: false };
  }
} else {
  this.deviationCount = 0;
  this.isCurrentlyDeviated = false; // 복귀
}
```

**5-2. BLE 통신 및 명령 처리 (Hardware · ESP32-C3 / C++)**
- 소스코드 설명 : **WRITE(명령 수신)** 와 **NOTIFY(심박 전송)** 두 개의 Characteristic으로 스마트폰과 밴드 간 양방향 통신을 구성했습니다. 1바이트 command 값에 따라 방향 안내, 역할 설정(심박 측정 활성/비활성), 페이스 조절, 보폭 설정 명령을 처리하며, 연결이 끊기면 진동을 자동으로 멈추고 광고를 재시작해 자동 재연결되도록 했습니다.

```cpp
// [BLE 초기화 및 Characteristic 등록]
BLEDevice::init(DEVICE_NAME);
BLEServer* pServer = BLEDevice::createServer();
pServer->setCallbacks(new ServerCallbacks());
BLEService* pService = pServer->createService(SERVICE_UUID);

// WRITE: 방향 안내 + 역할 설정 + 페이스 조절 명령 수신
pCommandChar = pService->createCharacteristic(
  COMMAND_CHAR_UUID,
  BLECharacteristic::PROPERTY_WRITE | BLECharacteristic::PROPERTY_WRITE_NR
);
pCommandChar->setCallbacks(new CommandCallbacks());

// NOTIFY: 심박 데이터 전송
pHeartRateChar = pService->createCharacteristic(
  HEARTRATE_CHAR_UUID,
  BLECharacteristic::PROPERTY_NOTIFY
);

// [커맨드 수신 및 제어 분기]
switch (command) {
  case COMMAND_VIBRATE:     // 0x01: 방향 안내 햅틱
    handlePattern(param1, param2, param3);
    break;
  case COMMAND_SET_ROLE:    // 0x02: 심박 활성/비활성 지정
    hrRole = param1;
    break;
  case COMMAND_PACE:        // 0x03: 페이스 조절 햅틱
    handlePace(param1, idealPace);
    break;
  case COMMAND_SET_STRIDE:  // 0x05: 보폭 설정
    STRIDE_LENGTH = strideMm / 1000.0f;
    break;
}
```

**5-3. 심박 수집 및 햅틱 진동 제어 (Hardware · ESP32-C3 / C++)**
- 소스코드 설명 : MAX30102 센서 값 중 정상 범위만 걸러 최근 5개 값의 이동평균을 5초마다 전송해 노이즈를 줄입니다. 방향 안내는 DRV2605L 햅틱 드라이버의 패턴으로 구분하고, 페이스 조절은 AI가 산출한 이상적인 페이스를 **사용자 보폭 기반 케이던스(SPM)** 로 환산해 진동 간격을 계산합니다. 정상 페이스일 때는 진동을 멈추고, OVER/UNDER 상태에서만 진동합니다.

```cpp
// [심박 데이터 수집] 정상 범위 값만 버퍼에 저장
if (now - lastSensorRead >= SENSOR_READ_INTERVAL) {
  lastSensorRead = now;
  MAX30102.getHeartbeatSPO2();
  int hr   = MAX30102._sHeartbeatSPO2.Heartbeat;
  int spo2 = MAX30102._sHeartbeatSPO2.SPO2;

  if (hr > 50 && hr < 120 && spo2 > 50 && spo2 <= 100) { // 유효값 필터링
    hrBuffer[hrBufIndex] = hr;
    hrBufIndex = (hrBufIndex + 1) % HR_BUFFER_SIZE;
    if (hrValidCount < HR_BUFFER_SIZE) hrValidCount++;
  }
}

if (now - lastReport >= REPORT_INTERVAL) {  // 5초마다 이동평균 계산 후 전송
  lastReport = now;
  long sum = 0;
  for (int i = 0; i < hrValidCount; i++) sum += hrBuffer[i];
  finalHR = sum / hrValidCount;
  pHeartRateChar->setValue(hrPacket, 2);
  pHeartRateChar->notify();
}

// [방향 안내 패턴 처리]
void handlePattern(uint8_t patternId, uint8_t intensity, uint8_t repeat) {
  switch (patternId) {
    case PATTERN_TURN_LEFT:
    case PATTERN_TURN_RIGHT:
      playEffect(EFFECT_TRIPLE_CLICK, repeat, 300);  // Triple Click ×3
      break;
    case PATTERN_DEVIATED:
      playEffect(EFFECT_DOUBLE_CLICK, repeat, 300);  // Double Click ×2
      break;
    case PATTERN_ARRIVED:
      playEffect(EFFECT_LONG_ALERT, repeat, 1200);   // 1000ms Alert
      break;
  }
}

// [페이스 조절 → 케이던스 진동 간격 계산]
void handlePace(uint8_t label, float idealPace) {
  if (label == LABEL_NORMAL) { stopPaceHaptic(); return; }

  float speedMps = 1000.0f / (idealPace * 60.0f);  
  float spm = (speedMps / STRIDE_LENGTH) * 60.0f;
  hapticPaceInterval = (int)(120000.0f / spm);
  hapticPaceActive = true;
}
```

---

<div align="center">

**<img src="https://github.com/user-attachments/assets/76cfa072-70b9-40ba-a273-e2aa5743b24b" height="24" align="absmiddle" /> 나침발** — "Feel the Way, Find Your Pace."
</div>
