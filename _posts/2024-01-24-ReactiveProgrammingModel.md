---
title: "Reactive Programming Model"
author: 2deeens
date: 2024-01-24 18:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, outsystems, event, Screen]
---

# Screen Events

## Screen Lifecycle
- 하나의 화면에서 다른 화면으로의 화면 전환은 여러 단계를 포함하고 있다.
  * 서버는 오직 데이터베이스 쿼리 또는 Server side code 실행 목적으로만 필요하다.
    + 서버 / 클라이언트 역할이 나누어져 있다.
  * 화면의 전환동안 이벤트는 application logic에 통합할 수 있다.
    + 화면 전환 중에 발생하는 이벤트들을 어플리케이션의 전반적인 동작에 통합/설계할 수 있다.
- 상태의 변경을 알리기 위해 Application은 이벤트를 발생시킨다.
  * 변화에 대한 데이터 공유
  * 변경에 대응하기 위한 Handler



## Opening the App
- DOM : DOM은 프로그래머와 사용자가 문서를 더 쉽게 탐색할 수 있도록 구조화된 계층적 방식으로 웹페이지를 표현하는 방법입니다. 
  DOM을 사용하면 Document 개체에서 제공하는 명령이나 메서드를 사용하여 HTML의 태그, ID, 클래스, 속성 또는 요소에 쉽게 액세스하고 조작할 수 있습니다.

1) Initialize
- Initialize가 시작되고, DOM이 Loading 된다.
- 동시에 필요한 Aggregate가 호출된다.
2) Ready
- DOM loading이 끝나면 Ready 상태로 넘어간다
3) Render
- Ready가 끝나면 Render가 시작된다.
4) After Fetch
- Aggregate를 가져온다
5) Render
- After Fetch된 값들을 화면에 그린다 (Render 한다)

## Navigating Between Screens
- Current Screen
  1) On Click
  ... 화면 유지
  Destination Screens의 4) Render가 끝나면
  2) Screen transition
  3) Destory

- Destination Screen
  1) Iniitialize
  2) DOM Loading
  3) Ready
  4) Render
  > Current Screen : Screen transition
  5) After Fetch
  6) Redner

  ## When to use each Event?
  - Initialize
    * Screen variables를 초기값으로 설정한다.
    * 조건에 기반하여 다른 화면으로 사용자를 전달한다.
  - Ready
    * DOM element에 javascript listener를 추가한다.
    * input widget에 초점을 맞춘다.
  - Render
    * 데이터 변화에 따른 동작을 수행
  - Destory
    * Javascript listener를 제거한다.
    * DOM을 초기화 한다.
  - After Fetch
    * 쿼리 실행
    * 쿼리 결과에 대한 유효성 검증


Fetching Data On Demend
  # Screen Lifecycle Overview
  1) Initialize
  2) Ready
  3) Render
  4) After Fetch
  5) Render

  ## Screen Aggregate
  - Aggregate는 Screen Level에서 정의될 수 있다.
    * Widget은 Aggregate의 출력 데이터에 접근권한을 가진다.
  - 기본적으로 어떤 Aggregate가 먼저 종료될디 보증할 수 없다.
  - Aggregate는 Fetch 속성을 가진다.
    * At start
    * Fetch Only On Demand

  ### At start
  - 기본적으로 'At start'가 Fetch 속성으로 설정되어 있다.
  - At start 옵션은 스크린이 초기화 될 때, 자동으로 발생하도록 하는 설정이다.

  ### Fetch Only On Demand
  - Aggregatesms 필요한 경우에만 데이터를 자겨오도록 설정할 수 있다.
  - Fetch Only On Demand로 설정된 Aggregate는 스크린 초기화때 수행되지 않는다.
    * 프로그램적으로 트리거될 필요가 있다.

  ### Manualyy Trigger Aggregate
  - 필요할때 수행되는 Aggregate는 'Refresh Data'에 사용된다
    * Action Flow에서 사용
  - Aggregate는 비동기적으로 수행한다.
    * On After Fetch event also applies
