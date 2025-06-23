# ✈️ AI 여행 플래너 프로젝트

## 📝 프로젝트 개요
Flutter 웹앱에서 사용자가 여행지, 날짜, 예산, 각 날짜별 가용시간을 입력하면 **Perplexity AI API**로 맞춤 여행 일정을 자동 생성하는 스마트 여행 계획 서비스입니다. Node.js 프록시 서버를 통해 CORS 문제 해결 및 API 키 보안을 강화했습니다.

## 🎯 타겟 사용자
**20-30대 즉흥 여행자**를 위한 AI 기반 여행 계획 서비스로, 복잡한 여행 계획 수립 과정을 **1분 내**에 자동화합니다.

## 🌏 지원 도시
현재 **아시아 주요 4개 도시**를 지원합니다:
- 🇯🇵 **도쿄/오사카** (일본)
- 🇭🇰 **홍콩** (중국)
- 🇹🇼 **타이페이** (대만)

## 🚀 주요 기능

### 핵심 기능 (완료)
- 🗺️ **여행 정보 입력**: 목적지, 날짜, 예산, 각 날짜별 시작/종료시간
- 🤖 **AI 일정 자동 생성**: 실제 장소, 시간, 활동 타입, 좌표 포함
- 🔒 **보안 강화**: Node.js 프록시 서버로 CORS 해결 및 API 키 보안
- 📅 **일정 시각화**: 생성된 일정 리스트 및 지도 기반 표시
- 🍽️ **맛집 추천**: Google Places API 연동으로 실제 맛집 정보 제공
- 🗺️ **Google Maps 통합**: 마커 표시 및 실제 도로 기반 경로 계산

### 고급 기능 (부분 완료)
- 🛣️ **실제 이동 경로**: Routes API로 도로 기반 경로 (간헐적 작동)
- 🎨 **일차별 색상 구분**: 여러 일차 여행 시 색상으로 구분
- 📱 **반응형 UI**: 모바일/웹 크로스 플랫폼 지원

## 🏗️ 시스템 아키텍처

![image](https://github.com/user-attachments/assets/714823cd-f050-4466-91ad-ab263c406ccd)



## 📁 프로젝트 구조

![image](https://github.com/user-attachments/assets/8f7c46b3-2f7e-448c-a4f1-7763af682c25)



## 🔧 기술 스택

### Frontend
- **Flutter 3.x**: 크로스 플랫폼 UI 프레임워크
- **google_maps_flutter**: Google Maps 통합
- **http**: API 통신
- **Provider**: 상태 관리

### Backend
- **Node.js + Express**: 프록시 서버
- **cors**: CORS 문제 해결
- **dotenv**: 환경변수 관리

### External APIs
- **Perplexity API**: Llama 3.1 기반 AI 일정 생성
- **Google Maps API**: 지도 표시 및 상호작용
- **Google Places API**: 주변 맛집/관광지 검색
- **Google Routes API**: 실제 도로 기반 경로 계산

## 📊 7주차별 개발 진행 및 문제 기록

| 주차 | 개발 내용 | 상태 | 주요 문제점 | 해결 상태 |
|------|----------|------|------------|----------|
| **1주차** | 여행지/날짜/예산 입력 | ✅ 완료 | 입력 검증 로직 미흡, 초기 API 연동 오류 | ✅ 해결 |
| **2주차** | 1분 내 완성된 일정 확인 | ✅ 완료 | API 호출 지연, Perplexity 응답 시간 초과 | ✅ 해결 |
| **3주차** | 구체적인 맛집 정보 제공 | ⚠️ 부분 완료 | **중복 식당 문제** (이치란 라멘 5번 반복) | 🔄 진행중 |
| **4주차** | 지도에서 일정 확인 | ✅ 완료 | Google Maps API 연동 오류, 마커 표시 불안정 | ✅ 해결 |
| **5주차** | 실제 이동 경로 확인 | ⚠️ 부분 완료 | **비현실적 이동시간** (2시간 59분으로 12km) | 🔄 진행중 |
| **6주차** | 일차별 구분 + 장소별 상세 정보 | ❌ 미완성 | **터치 이벤트 무반응**, BottomSheet 표시 안됨 | ❌ 미해결 |
| **7주차** | 교통수단별 경로 + 반응형 UI + 개인화 | ❌ 거의 미완성 | **개인화 알고리즘 미구현**, 교통수단별 실제 차이 없음 | ❌ 미해결 |

### 🔴 주요 미해결 문제
1. **중복 식당 문제**: "이치란 라멘 시부야점"이 여러 일차에 반복 출현
2. **지도 상호작용**: 마커 클릭 시 BottomSheet 무반응
3. **이동시간 비현실성**: 12km를 2시간 59분으로 계산하는 Routes API 문제
4. **일정 불균형**: 3-4일차가 1-2일차보다 활동 수가 현저히 적음

## 🚀 설치 및 실행

### 1. 저장소 클론
git clone https://github.com/your-username/ai_travel_agency_verx.git
cd ai_travel_agency_verx

### 2. Flutter 의존성 설치
flutter pub get

### 3. Node.js 프록시 서버 설정
cd node_proxy_server
npm install


### 4. 환경변수 설정
`node_proxy_server/.env` 파일 생성:
PERPLEXITY_API_KEY=your_perplexity_api_key
GOOGLE_MAPS_API_KEY=your_google_maps_api_key


### 5. 서버 실행
Node.js 프록시 서버 실행
cd node_proxy_server
node proxy_server.js

Flutter 앱 실행 (새 터미널)
flutter run -d chrome


## 📈 Flutter 활용 평가 및 향후 계획

### **Flutter 활용 평가**
Flutter로 기본적인 크로스 플랫폼 앱은 만들었지만, 지도 상호작용, AI 프롬프트 등 핵심 기능의 완성도가 낮음.

### **향후 계획**
단기적으로는 중복 식당 문제, 지도 터치 무반응 등 핵심 버그 해결을 최우선으로 하고, 장기적으로는 개인화 기능 추가와 아시아 도시 확장을 통해 완성도 높은 AI 여행 플래너로 발전시킬 계획.


### 기존 perplexity & google API는 폐기기
