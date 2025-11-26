# Cointel App - 암호화폐 시장 분석 및 알림 서비스

![Flutter](https://img.shields.io/badge/Flutter-3.29.3-02569B?logo=flutter)
![Dart](https://img.shields.io/badge/Dart-3.7.2-0175C2?logo=dart)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?logo=firebase&logoColor=black)
![Platform](https://img.shields.io/badge/Platform-iOS%20%7C%20Android-lightgrey)

> 실시간 암호화폐 시장 데이터 조회, AI 기반 차트 분석, 가격 변동 알림 기능을 제공하는 크로스 플랫폼 모바일 앱

**프로젝트 기간**: 2024.11 ~ 2025.11 (1년)
**담당 역할**: 주 개발자 (전체 코드의 93% 기여)
**배포 상태**: ✅ Google Play Store / Apple App Store 배포 완료
**현재 버전**: v1.2.3 (Build 107)

---

## 📱 주요 기능

### 🔥 실시간 암호화폐 시세
- 15개 거래소(Binance, Upbit, Coinbase 등) 실시간 가격 조회
- WebSocket 기반 실시간 데이터 스트리밍
- 거래소별 호가창 및 체결 내역 확인
- TradingView 차트 통합

### 🤖 AI 기반 분석 (Cointel)
- 차트 패턴 자동 인식 및 예측
- 암호화폐 관련 뉴스 실시간 집계
- 소셜 미디어 감정 분석
- 스캠 코인 탐지 및 경고

### 🔔 가격 알림 시스템
- 사용자 맞춤형 가격 변동 알림 설정
- Firebase Cloud Messaging 기반 푸시 알림
- 백그라운드에서도 동작하는 알림 서비스

### 🔐 소셜 로그인
- Google Sign-In
- Apple Sign-In
- Firebase Authentication 기반 보안 인증

### 💼 지갑 관리 (이전 버전)
- 다중 암호화폐 지갑 지원
- QR 코드 기반 주소 스캔
- 송금 및 수신 기능

---

## 🛠️ 기술 스택

### Frontend
- **Framework**: Flutter 3.29.3 (Dart 3.7.2)
- **State Management**: Provider 패턴 (34개 Provider)
- **Navigation**: go_router
- **UI**: Material Design 3

### Backend & Services
- **API Communication**: Dio + Interceptors
- **Real-time Data**: WebSocket, Server-Sent Events (SSE)
- **Authentication**: Firebase Auth
- **Push Notifications**: Firebase Cloud Messaging (FCM)
- **Analytics**: Firebase Analytics
- **Local Storage**: flutter_secure_storage, shared_preferences

### Architecture
- **Pattern**: MVVM + Provider
- **DI**: GetIt (Dependency Injection)
- **Services**: 24개 서비스 레이어
- **Screens**: 95개 화면

### Build & Deploy
- **Android**: Gradle 8.7, AGP 8.6.1, Min SDK 28, Target SDK 35
- **iOS**: Xcode, CocoaPods
- **CI/CD**: 수동 빌드 및 배포

---

## 📊 개발 성과

### 코드 기여도
```
총 커밋 수: 310개 중 288개 담당 (93%)
코드 추가: 8,614줄
코드 삭제: 4,633줄
순 증가량: 3,981줄
```

### 버전 관리
- **총 배포 버전**: 16개 이상 (v1.0.4 → v1.2.3)
- **지속적인 유지보수**: 1년간 주기적 업데이트
- **플랫폼**: Android & iOS 동시 지원

---

## 🚀 핵심 기술 구현

### 1. WebSocket 기반 실시간 데이터 처리
```dart
// 15개 거래소의 실시간 시세 데이터를 효율적으로 관리
- 다중 WebSocket 연결 관리
- RxDart를 활용한 데이터 스트림 최적화
- 메모리 누수 방지를 위한 구독 관리
```

### 2. Provider 패턴 기반 상태 관리
```
- 34개 Provider를 활용한 전역 상태 관리
- 화면별 독립적인 상태 관리로 성능 최적화
- ChangeNotifier를 통한 효율적인 리빌드 제어
```

### 3. Firebase 전체 통합
```
- FCM을 통한 백그라운드 푸시 알림
- Google/Apple 소셜 로그인 연동
- Firebase Analytics를 통한 사용자 행동 분석
```

### 4. 크로스 플랫폼 대응
```
- iOS/Android 플랫폼별 네이티브 기능 통합
- 플랫폼별 UI/UX 최적화
- Android 16KB 메모리 페이지 크기 대응 (AGP 8.6.1)
```

---

## 🔧 기술적 문제 해결 사례

### 1. Android 16KB 메모리 페이지 지원 (2025년 Google Play 필수 요구사항)
**문제**: Android 15부터 16KB 메모리 페이지 크기 지원 필수
**해결**:
- AGP 8.6.1 업그레이드
- Core Library Desugaring 활성화
- Gradle 8.7로 마이그레이션

### 2. iOS WebView 리다이렉트 버그
**문제**: iOS에서 WebView 리다이렉트 시 특정 호출이 차단됨
**해결**: 플랫폼 조건부 처리 및 관련 코드 최적화

### 3. 마크다운 패키지 지원 종료
**문제**: 기존 사용 중이던 마크다운 패키지가 deprecated
**해결**: flutter_markdown_plus로 마이그레이션

### 4. 차트 로딩 성능 최적화
**문제**: TradingView 차트 로딩 시 화면 멈춤 현상
**해결**: 콜백 기반 비동기 로딩 및 캐싱 전략 적용

### 5. 컨텐츠 중복 렌더링 (Android)
**문제**: 마켓 리스트가 2번 중복 표시되는 버그
**해결**: Provider 상태 관리 로직 개선 및 위젯 리빌드 최적화

---

## 📸 스크린샷

### 주요 화면
> 실제 앱 스크린샷 추가 예정

| 메인 화면 | 차트 상세 | AI 분석 | 알림 설정 |
|----------|---------|---------|----------|
| ![main] | ![chart] | ![ai] | ![alert] |

---

## 🏗️ 프로젝트 구조

```
lib/
├── main.dart                 # 앱 진입점 (Firebase 초기화, DI 설정)
├── routes/                   # 라우팅 (go_router, 31개 경로)
├── providers/                # 상태 관리 (34개 Provider)
├── services/                 # 비즈니스 로직 (24개 Service)
│   ├── api_service.dart      # 메인 REST API
│   ├── cointel_api_service.dart  # AI 분석 API
│   ├── order_book_api_service.dart  # 거래소 호가 API
│   └── fcm_service.dart      # 푸시 알림
├── screens/                  # UI 화면 (95개)
├── widgets/                  # 재사용 컴포넌트
├── models/                   # 데이터 모델 (39개)
└── utils/                    # 헬퍼 함수
```

---

## 💡 배운 점 & 성장

### 기술적 성장
- Flutter 프레임워크의 깊은 이해와 실무 적용 능력 향상
- Provider 패턴을 활용한 대규모 앱 상태 관리 경험
- WebSocket 실시간 통신 구현 및 최적화
- Firebase 전체 생태계 통합 경험
- 크로스 플랫폼 개발 및 플랫폼별 이슈 대응 능력

### 프로젝트 관리
- 1년간 장기 프로젝트 유지보수 경험
- 지속적인 버전 업데이트 및 배포 프로세스 경험
- Google Play / App Store 실제 배포 및 운영 경험
- 사용자 피드백 기반 개선 작업

---

## 🔗 링크

- **Google Play**: [링크 추가 예정]
- **App Store**: [링크 추가 예정]
- **GitHub**: [이 저장소]
- **상세 포트폴리오**: [PORTFOLIO.md 참고](./PORTFOLIO.md)

---

## 👨‍💻 개발자

**송현수 (hyeonsoo)**

- 전체 커밋의 93% 담당
- 1년간 지속적인 개발 및 유지보수
- 16개 버전 배포 및 운영

---

## 📄 라이선스

Private Project

---

## 📝 버전 히스토리

최신 주요 업데이트:
- **v1.2.3** (2025.11): 백그라운드 복귀 시 리로드 기능 추가
- **v1.2.0**: 지갑 기능 제거 (nowallet 브랜치)
- **v1.1.0**: AI 분석 기능 고도화
- **v1.0.4**: 초기 안정화 버전

자세한 변경 사항은 [CHANGELOG.md](./CHANGELOG.md) 참고

---

**Made with Flutter** 🚀
