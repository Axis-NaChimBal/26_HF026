<div align="center">

<!-- 📷 표시된 src="..." 부분을 GitHub에 올린 이미지 주소로 바꿔야함. (Ctrl+F로 "📷" 검색) -->

# 🧭 나침발 : 스마트 러닝 밴드

**화면을 보지 않아도 손목 진동으로 길과 페이스를 알려주는 햅틱 러닝 밴드 & 앱**

`2026 한이음 드림업 공모전` · `26_HF026` · `Team Axis`

</div>

---

## **💡1. 프로젝트 개요**

**1-1. 프로젝트 소개**
- 프로젝트 명 : 나침발 (스마트 러닝 밴드)
- 프로젝트 정의 : 러닝 중 화면을 보지 않고도 경로 안내와 운동 피드백을 받을 수 있는 **좌·우 분리형 햅틱 러닝 밴드**와 이를 연동하는 모바일 앱
- 스마트폰과 좌·우 손목 밴드를 BLE로 연결하여 **방향 전환, 경로 이탈, 도착, 페이스 조절** 정보를 진동으로 전달하고, AI 기반 페이스 조절과 GPS 아트 경로 생성 기능을 함께 제공합니다.

**1-2. 개발 배경 및 필요성**
- **러닝 부상의 상당수는 페이스 오류에서 시작됩니다.** GRONORUN 연구(BMC Musculoskeletal Disorders, 2010)에 따르면 러닝 부상의 60% 이상이 훈련(페이스) 오류에서 비롯됩니다. 그러나 기존 러닝 앱·스마트워치는 수치를 화면에 보여주는 데 그쳐, 목표 페이스를 벗어나도 능동적으로 교정해 주지 않습니다.
- **화면·소리에 의존하는 방식은 위험합니다.** 반복적인 화면 확인은 운동 몰입을 방해하고 전방 주시를 어렵게 만들며, 이어폰 음성 안내는 주변 소리를 가립니다.
- **실제 러너들도 같은 문제를 겪고 있었습니다.** 정기 러너 23명을 대상으로 설문(2026.06.01~06.15)을 진행했습니다.

| 설문 항목 | 결과 |
|:---|:---:|
| 러닝 중 페이스 조절에 어려움을 겪은 경험 | **약 87%** |
| 경로 안내를 화면·소리에 의존하는 비율 | **약 80%** |
| 화면 확인·이어폰 사용으로 위험하거나 불편했던 경험 | **약 52%** |
| 나침발 주요 기능에 대한 기대(리커트 5점 척도 평균) | **4.41 / 5.0** |

→ **손목 진동만으로 경로와 페이스를 안내하는 러닝 보조 시스템**이 필요하다는 것을 확인하고, 설문과 인터뷰 결과를 기능 설계에 직접 반영했습니다.

**1-3. 프로젝트 특장점**

| 서비스 | 방향 안내 방식 | 경로 설계 | GPS 아트 | 페이스 조절 |
|:---:|:---:|:---:|:---:|:---:|
| 나이키런클럽 · 런데이 | 화면 · 음성 | 자동 생성 | ✕ | 음성 코칭 |
| 아웃라인 (GPS 아트 앱) | 화면 | 아트 경로 추천 | O | ✕ |
| 애플워치 · 가민 | 화면 + 제한적 진동 | 직접 생성 가능 | ✕ | 워치 화면 기반 |
| WearWorks Wayband | 순수 햅틱(진동) | ✕ (내비게이션 전용) | ✕ | ✕ |
| **나침발** | **순수 햅틱(양손)** | **직접 설계 + 아카이빙** | **O** | **햅틱 케이던스** |

- **좌·우 분리형 햅틱 안내** : 왼손이 울리면 좌회전, 오른손이 울리면 우회전. 단일 기기(스마트워치)로는 어려운 직관적인 방향 구분을 제공합니다.
- **AI 기반 능동적 페이스 교정** : 수치를 보여주는 데 그치지 않고, TCN 모델이 오버/언더페이스를 판단하면 목표 케이던스에 맞춘 리듬 진동으로 페이스를 직접 교정합니다.
- **실제 도로 위에서 그리는 GPS 아트** : 생성형 AI가 임의로 좌표를 만드는 방식이 아니라, 실제 보행자 도로망 그래프에서 목표 도형과 가장 비슷한 순환 경로를 찾는 알고리즘을 직접 구현했습니다.
- **나만의 경로 설계 & 아카이빙** : 지도에서 경유지를 찍어 경로를 만들고, 저장해 두었다가 다시 달릴 수 있습니다.
- **저비용 웨어러블** : 기성 부품과 맞춤 외관 설계로 고가의 스마트워치 없이도 러닝 보조 서비스를 제공합니다.

**1-4. 주요 기능**

| 기능 | 설명 |
|:---|:---|
| 🔗 **햅틱 밴드 연동 및 상태 관리** | `NaChimBal_L`, `NaChimBal_R` 좌/우 밴드 동시 탐색·연결, 연결 상태 및 배터리 확인, 진동 패턴 학습(온보딩), 안정 심박수 측정 |
| 🧭 **햅틱 러닝 경로 안내** | 회전 지점에서 해당 방향 손목에 진동, 경로 이탈 3회 누적 시 양손 경고 진동, 도착 시 완료 진동 |
| 🤖 **AI 페이스 조절** | 심박수·속도·고도 시계열을 5초 주기로 분석해 오버/정상/언더페이스를 판단하고, 이탈 시 목표 케이던스 리듬 진동을 정상 페이스로 돌아올 때까지 전송 |
| ⏱️ **목표 페이스 메이커** | 목표를 입력하면 워밍업·러닝·쿨다운 구간별 속도에 맞춰 진동, 박자에 맞춰 뛰면 페이스 메이커와 함께 달리는 효과 |
| 🗺️ **경로 생성 및 MY 경로 아카이빙** | 지도에서 경유지(Waypoint)를 지정하면 T-map 보행자 API로 경로 생성, MY 경로 저장·즐겨찾기, GPS 아트 명소 조회 |
| 🎨 **GPS 아트 경로 자동 생성** | 원하는 위치에서 버튼 하나로 하트, 다각형 등 모양의 GPS 아트 경로를 자동 생성 |
| 📊 **운동 데이터 기록 및 시각화** | 러닝 결과(거리·시간·속도·심박수·칼로리·페이스 조절 횟수) 및 SNS 공유, 평균 기록·최고 기록, 러닝 스트릭, 주간/월간 목표 진행률 |
| 💬 **AI 러닝 코치 챗봇** | 누적 러닝 데이터를 주/월 단위 통계로 요약해 OpenAI API에 전달, 분석·훈련 계획 등 사용자 질문에 맞춤 응답 |

**🔔 진동 패턴**

| 상황 | 왼손 | 오른손 | 패턴 |
|:---:|:---:|:---:|:---|
| ⬅️ 좌회전 | ● | | 3회 진동 |
| ➡️ 우회전 | | ● | 3회 진동 |
| ⚠️ 경로 이탈 | ● | ● | 양손 2회 진동 |
| 🏁 도착 | ● | ● | 양손 길게 1회 진동 |
| 🏃 페이스 조절 | ● | ● | 목표 케이던스(SPM)에 맞춘 리듬 진동 |

**📱 앱 화면**

<p align="center">
  <img src="📷앱-홈_이미지주소" width="160" alt="홈" />
  <img src="📷앱-경로 생성_이미지주소" width="160" alt="경로 생성" />
  <img src="📷앱-러닝 안내_이미지주소" width="160" alt="러닝 안내" />
  <img src="📷앱-러닝 결과_이미지주소" width="160" alt="러닝 결과" />
  <img src="📷앱-운동 기록_이미지주소" width="160" alt="운동 기록" />
</p>
<p align="center"><sub>홈 · 경로 생성 · 러닝 안내 · 러닝 결과 · 운동 기록</sub></p>

<p align="center">
  <img src="📷앱-GPS 아트 생성_이미지주소" width="160" alt="GPS 아트 생성" />
  <img src="📷앱-GPS 아트 결과_이미지주소" width="160" alt="GPS 아트 결과" />
  <img src="📷앱-아카이브_이미지주소" width="160" alt="아카이브" />
  <img src="📷앱-챌린지_이미지주소" width="160" alt="챌린지" />
  <img src="📷앱-AI 코치_이미지주소" width="160" alt="AI 코치" />
</p>
<p align="center"><sub>GPS 아트 생성 · GPS 아트 결과 · 아카이브 · 챌린지 · AI 코치</sub></p>

**1-5. 기대 효과 및 활용 분야**
- 기대 효과
  - **몰입감 있는 러닝** : 햅틱 기반의 즉각적인 경로 안내와 페이스 피드백으로 화면 확인 없이 달릴 수 있습니다.
  - **안전성 향상** : 화면을 보지 않아도 방향을 알 수 있어 전방 주시가 쉬워지고, 야간·우천·이어폰 착용 등 다양한 환경에서도 경로를 인지할 수 있습니다.
  - **부상 예방** : 오버페이스를 실시간으로 감지하고 진동으로 교정을 유도해 훈련 오류로 인한 부상 위험을 줄입니다.
  - **개인 맞춤형 가이드** : 개인의 안정 심박수, 나이, 운동 목표를 반영해 획일적이지 않은 러닝 가이드를 제공합니다.
  - **지속적인 동기부여** : 러닝 스트릭, 마일스톤, MY 경로, GPS 아트로 러닝을 꾸준한 습관으로 이어가도록 돕습니다.
- 활용 분야 : 스마트 퍼스널 러닝 코칭 및 헬스케어, 비시각 인터페이스 기반 안전 러닝 서비스, 러닝 코스·챌린지 공유 커뮤니티 플랫폼, 러닝 특화 웨어러블 및 스포츠 테크

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

<!-- TODO: 프로필 이미지와 역할 수정 필요 -->

| <img width="80" height="100" src="https://github.com/dalpaeng6.png" > | <img width="80" height="100" src="https://github.com/멘티2아이디.png" > | <img width="80" height="100" src="https://github.com/멘티3아이디.png" > | <img width="80" height="100" src="https://github.com/멘티4아이디.png" > | <img width="80" height="100" src="https://github.com/멘티5아이디.png" > | <img width="80" height="100" src="https://github.com/멘토아이디.png" > |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **멘티1** | **멘티2** | **멘티3** | **멘티4** | **멘티5** | **멘토** |
| • 역할1 <br> • 역할2 | • 역할1 <br> • 역할2 | • 역할1 <br> • 역할2 | • 역할1 <br> • 역할2 | • 역할1 <br> • 역할2 | • 프로젝트 멘토 <br> • 자문 |

---

## **💡3. 시스템 구성도**

**3-1. S/W 구성도**

<p align="center"><img src="📷S/W 구성도_이미지주소" width="560" alt="S/W 구성도" /></p>

**3-2. H/W 구성도**

<p align="center"><img src="📷H/W 회로 구성도_이미지주소" width="600" alt="H/W 회로 구성도" /></p>

> 좌·우 밴드 각각에 위 회로를 하나로 통합해 독립적으로 구동하며, 러닝 중 착용 부담이 없도록 **경량화·소형화**에 중점을 두었습니다.

<p align="center"><img src="📷밴드 내부 회로 사진_이미지주소" width="420" alt="밴드 내부 회로" /></p>

**3-3. 서비스 흐름도 (러닝 기능)**

<p align="center"><img src="📷서비스 흐름도_이미지주소" width="760" alt="서비스 흐름도" /></p>

**3-4. AI 페이스 조절 알고리즘**

```
[러닝 시작] BE 서버 → AI 서버 : 세션 아이디 · 안정 심박수 · 나이 · 예상 운동 시간 전달
     │
     ▼  (러닝 중 5초 간격)
BE 서버 → AI 서버 : 최근 120초치 심박수 · 속도 · 경과 시간 · 고도 배열 전송
     │
     ▼
AI : 파생 피처 5개(hrr_pct, delta_hrr_pct, time_ratio, speed_trend, fatigue_index) 계산
     + 원본 피처(speed, hear_rate) → 총 7개 피처(FEATURE_COLUMNS) 구성
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

<p align="center"><img src="📷ERD_이미지주소" width="760" alt="ERD" /></p>

`users` · `devices` · `routes` · `waypoints` · `exercise_sessions` · `exercise_results` · `pace_logs` · `route_deviation_logs` · `running_streaks` · `challenge_goals`

---

## **💡4. 작품 소개영상**

> 🎬 작품 소개영상입니다

<p align="center">
  <a href="https://www.youtube.com/watch?v=2wY3_pB0_G4">
    <img src="https://img.youtube.com/vi/2wY3_pB0_G4/0.jpg" width="640" alt="나침발 : 스마트 러닝 밴드 소개" />
  </a>
</p>
<p align="center"><sub>▶ 이미지를 누르면 유튜브에서 작품 소개영상을 볼 수 있어요</sub></p>

---

## **💡5. 핵심 소스코드**

**5-1. 햅틱 경로 안내 로직 (Frontend · JavaScript)**
- 소스코드 설명 : GPS 위치가 들어올 때마다 **도착 → 다음 회전 지점 진입 → 경로 이탈** 순서로 판정하는 경로 안내 로직입니다.
  - **도착 판정** : 마지막 구간에서 목적지 반경 안에 들어오면 이탈 판정보다 먼저 도착 처리합니다.
  - **회전 지점 진입** : 단순히 반경 안에 들어왔는지만 보지 않고, 현재 지점보다 다음 지점이 더 가까워졌는지(방향성)까지 함께 확인해 오탐을 막습니다.
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

**🧭 나침발** — 화면 대신 손목으로, 더 안전하고 몰입감 있는 러닝

</div>
