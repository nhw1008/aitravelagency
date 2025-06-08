✈️ AI 여행 플래너 프로젝트

📝 프로젝트 개요
  - Flutter 웹앱에서 사용자가 여행지, 날짜, 예산, 각 날짜별 가용시간을 입력하면
  - 🤖 Perplexity AI API로 맞춤 여행 일정을 자동 생성
  - 🛡️ Node.js(Express) 프록시 서버로 CORS 문제 해결 및 API 키 보안

🚀 주요 기능
  - 🗺️ 여행 정보 입력(목적지, 날짜, 예산, 각 날짜별 시작/종료시간)
  - 🤖 AI 여행 일정 자동 생성(실제 장소, 시간, 활동 타입, 좌표 등)
  - 🔒 Node.js 프록시 서버로 CORS 문제 해결 및 API 키 보안 강화
  - 📅 생성된 일정 리스트/지도 기반 시각화(확장 가능)

🏗️ 시스템 아키텍처

  👤 사용자
    ↓
  💻 Flutter 웹앱 (home_screen.dart, planner_screen.dart)
    ↓
  🛡️ Node.js 프록시 서버 (proxy_server.js, Express)
    ↓
  🤖 Perplexity AI API
  
📁 주요 파일 역할
-  lib/screens/home_screen.dart
🏠 여행 정보 입력 및 일정 생성 요청 화면

-  lib/screens/planner_screen.dart
📅 AI가 생성한 여행 일정 표시 화면

-  lib/models/travel_plan.dart
🗂️ DayPlan, Activity 등 데이터 모델 정의

-  lib/services/ai_service.dart
🤖 Perplexity API 호출 및 응답 파싱

-  node_proxy_server/proxy_server.js
🛡️ Node.js(Express) 프록시 서버, API 중계
