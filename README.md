# CLIPPED

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

## 📌 CLIPPED – Timeline-based Portfolio App

## 0. 담당한 기능 개발 및 구현 기술
- **개발 프레임워크:** Flutter
- **역할:** 프론트엔드 개발
- **구현 기술:** 메인 UI 개발, 태그 시스템, 사용자 인터페이스 구성

---

## 1. 제목
**CLIPPED**

---

## 2. 배경 및 문제

현대의 포트폴리오 앱은 대부분 리스트 중심으로 구성되어 있어, 사용자의 성장 과정이나 시기별 맥락을 담기 어렵다. 이에 따라 다음과 같은 문제의식을 바탕으로 기획되었다:

- 포트폴리오를 정리하고 싶은데, 단순히 파일이나 게시글 형식이 아닌 **시간의 흐름을 따라 정리할 수는 없을까?**
- 프로젝트나 경험들을 **연대기적 흐름(Lifeline)** 으로 볼 수 있다면 좋을 것 같다.
- 각 작업을 **태그로 쉽게 분류**하고, 특정 주제의 작업만 모아보고 싶다.
- **다른 사람의 포트폴리오도 탐색**하면서, 어떤 식으로 성장하고 구성했는지를 참고할 수 있으면 좋겠다.
- 이러한 포트폴리오 열람이 **네트워킹이나 협업으로 확장**될 수 있다면 의미 있을 것이다.

---

## 3. 목표

- 사용자의 생애를 세로선 형태로 시각화한 **Lifeline UI** 위에 포트폴리오를 Clip 단위로 저장하고 관리
- 각 Clip은 **하나 이상의 태그**를 가지며, 이를 통해 유사한 작업을 모아보거나 검색 가능
- **공개된 포트폴리오**는 다른 유저가 자유롭게 열람 가능
- 사용자 간 **네트워킹 기능** 제공

---

## 4. 팀 구성

| 역할             | 팀원                 |
|------------------|----------------------|
| 기획             | 박정현               |
| 디자인           | 최서진, 류나정       |
| 프론트엔드 개발  | 김정환, 김호재, 박제현 |
| 백엔드 개발      | 김현승, 김주헌       |

---

## 5. 기대 효과

- 포트폴리오를 **시간의 흐름에 따라 구성**함으로써 사용자의 성장과 경험을 자연스럽게 전달할 수 있음
- **태그 기반 탐색 기능**으로 관심 있는 주제나 분야의 사례를 빠르게 확인 가능
- 타인의 공개 포트폴리오를 통해 **진로 탐색 및 자기계발의 참고자료**로 활용 가능
- 포트폴리오를 매개로 **사용자 간 연결 및 네트워킹 기회 제공**
- 장기적으로는 **개인 브랜딩과 채용 플랫폼으로의 확장 가능성**

---

## 6. 구현 내용

- **Lifeline 메인 화면:** 포트폴리오를 시계열로 시각화한 타임라인 UI
- **태그 버블 시스템:** 유저가 지정한 태그로 Clip들을 그룹화하거나 필터링
- **사용자 프로필:** 자기소개, 활동 태그, Clip 목록 등을 포함
- **둘러보기(Browse) 화면:** 공개된 다른 사용자들의 포트폴리오 탐색
- **노트 위젯:** 각 Clip에 간단한 설명, 회고, 관련 링크 등을 추가 가능

### Directory Structure ###
```
.
├── assets/
│   ├── icons
│   └── images
└── lib/
    ├── pages
    ├── screens/
    │   │
    │   ├── login/
    │   │   ├── login_member       : 이메일 로그인 페이지
    │   │   ├── login_membership   : 회원가입 시작 ~ 비밀번호 입력 폼
    │   │   ├── login_membership2  : 약관동의 및 가입완료 폼
    │   │   └── login_screen       : 카카오톡/이메일/회원가입 선택 페이지(시작)
    │   ├── mypage/
    │   │   ├── clipedit           : 마이페이지 클립 수정 페이지
    │   │   └── climain            : 마이페이지 라이프로그 페이지
    │   │
    │   ├── home/
    │   │   ├── detailpaper        : 메인 홈 게시글 폼
    │   │   └── home               : 메인 홈 페이지
    │   │
    │   ├── publish/
    │   │   └── publish_paper      : 돋보기 통해 게시글 작성
    │   │
    ├── widgets/
    │   │
    │   ├── clip/
    │   │   ├── hashtagbubble      : 게시글 작성 폼 해시태
    │   │   └── tagbubble          : 클립만드는 도구(색, 태그명)
    │   │
    │   ├── home/
    │   │   ├── clip                : 메인페이지 추천클립 위젯
    │   │   ├── clipline            : 상단 클릅라인 위젯
    │   │   ├── findlinker          : 추천 링커 위젯
    │   │   └── paper               : 메인페이지 게시글(페이퍼) 위젯
    │   │
    │   └── login/
    │       ├── checkbox            : 회원가입 체크박스
    │       ├── login_box           : 회원가입 이동 버튼
    │       ├── login_textbox       : 회원가입 입력 폼
    │       └── terms               : 이용약관 텍스트 입력
    └── main.dart
```
