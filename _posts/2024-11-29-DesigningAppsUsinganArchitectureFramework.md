---
title: "Designing Apps With Architecture Framework"
author: 2deeens
date: 2024-11-29 09:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, outsystems, architecture]
---

# Why is Architecture Important?
test
## Building Quantity Software
> Why is application architecture important when building quantity software solutions?

### ISO / IEC
ISO, IEC put together statndard on the quality of software solutions.
this standard included several diffrent dimensions.
- Usablility (사용성) : the point of view of the users
- Functionality (기능성) : a set of functions that satify needs
- Efficiency (효율성) : which of relate performance to the amount of resources used.
- Maintainability (유지보수성) : which of relates to the effort needed to make modifications.
- Portability (이식성) :  which defines the ability to move software between environments.
- Reliability (신뢰성) :  which ensures that a software solution can maintain.

Updated
- Security (보안성) : can protect information and data.
- compatibility (호환성) : can work together with other systems.

## Lack of Architectural Concerns
- Poor service abstraction
  * Business concepts not correctly isolated and abstracted.
  * Business rules spread over diffrent systems, and little no code reuse
- Unmanageable dependencies
  * Systems not isolated from each other
  * Updating or replacing a system has a cascade effect on other systems
- Inflexible and slow-moving legacy systems
  * Adapting legacy systems to business changes may be difficult
  * Changes in complex and inflexible systems can take a long time

## Why is Architecture Important?
- Drives Consensus
- Manages Complecity
- Reduces Risk
- Supports Planning
- Facilitates Changes
- Reduces Cots


# Outsystems Architecture Framework
## The Architecture Canvas
> The Architecture Canvas is a framework to support application architecture design in Outsystems.

- It is a multi-layer framework, composed of three layer
  * End-User : should not have any services
    + User Interface and Processes : Provide functionality to end-users (intersection through user interfaces and processes)
  * Core : Reusable Services
    + Include the services around business concepts such as : their dependencies and business rules
    + these core business services should be system agnostic
  * Foundation : Reusable Services
    + Non-Functional Requirements : Services to connect to external systems or to extend your framework
    + In this layer, should not have any business-specific services.

- Why use Architecture Canvas?
  * Promotes abstraction of reusable services and components
  * Optimizes lifecycle independence
  * Minimizeds impact of changes

### Outsystems in an Enterprise Echosystem


## The Architecture Design Process
- 해당 장은 아키텍쳐 설계 프로세스를 소개, 아텍쳐 설계는 3단계로 구성된다.

### 아키텍쳐 설계와 비지니스 목표의 정렬
- 중요성
  * 아키텍쳐는 반드시 비지니스 목표와 정렬되어야 한다.
  * 비지니스 요구사항과 개념이 모듈로 적절히 변환되어야 한다.

- 이점
  * 모듈이 비지니스와 함께 진화하고 확장될 수 있도록 한다.
  * 서로 다른 비지니스 라인 간, 독립적인 라이프사이클을 보장한다.

### 아키텍쳐 설계의 3단계
1. Disclose (개념 도출)
2. Organize (개념 정리)
3. Assemble (모듈 구성)

### 1단계 : Disclose (개념 도출)
- 주요 작업
  * 비지니스 개념, 통합 요구사항, 비기능 요구사항을 도출한다.
  * 사용자 스토리를 식별하여 애플리케이션과의 상호작용 및 역할을 이해한다.

- 질문 및 분석
  * 누가 애플리케이션과 작용하는가?
  * 각 사용자의 역할과 수행 가능한 작업은 무엇인가?
  * 비지니스 이해관계자와의 대화 또는 기존 시스템 분석을 통해 정보 아키텍처를 명확하게 함.

- 통합 요구사항 분석
  * 외부 시스템 또는 소스에서 소비될 정보와 통합에 필요한 사항 (API 유형, 통신 프로토콜 등)을 정의

- 사용자 경험 분석
  * 접근성 요구사항이 있는지, 모바일 앱 또는 웹 앱 필요여부 확인
  * 사용자 역할에 따라 필요한 채널과 사용자 경험이 달라질 수 있음

- 주의사항
  * 프로젝트 초기에 가능한 많은 개념을 도출
  * 주요 개념이 누락되면 향후, 복잡한 리팩토링 필요

### 2단계 : Organize (개념 정리)
- 개념의 계층 배치
  * End-User 계층 : 사용자 인터페이스 및 프로세스 관련 개념
  * Core 계층 : 핵심 비지니스 개념
  * Foundation 계층 : 통합 요구사항 및 비기능 요구사항 -> 공통 느낌?

- 반복과정
  * 개념을 정리하면서 추가적인 개념을 도출할 수 있다.
  * Disclose와 Organize 단계는 반복적으로 진행


### 3단계 : Assemble (모듈 구성)
- 모듈 구성 원칙
  1. 연관된 개념은 함께 묶기
  ex : 고객과 클레임이 관련이 있다면 동일한 모듈에 배치
  2. 라이프사이클이 다른 개념은 분리
  ex : 고객과 계약은 관련이 있지만, 고객이 계약을 반드시 가지는 것은 아니므로 별도 모듈에 배치
  3. 재사용 가능한 로직과 통합로직 분리
  ex : 재사용 로직은 Core 계층, 통합 로직은 Foundation 계층에 배치
  이를 통해 외부 시스템 변경으로부터 핵심 로직을 보호
  4. 디자인 패턴 적용
    * 가능한 경우, 알려진 아키텍처 디자인 패턴을 적용하여 아키텍처를 개선

- 최종 결과
  + 아키텍처 청사진 (Architecture Blueprint)
    * 각 모듈이 적절한 계층에 배치
    모듈 간, 의존성을 추가하여 관계를 명확히 한다.

### 반복과 지속적 개선
- 프로젝트 진행 중, 새로운 개념이 도출되면 이를 정리하고 모듈에 통합
- Disclose, Organize, Assemble 단계를 지속적으로 반복하여 아키텍처를 개선.



## Designing an Architecture (병원 예약 예제)

> 아키텍처 설계 프로세스를 실제 비지니스 사례에 적용해본다. 적용 사례는 병원 예약 시스템.
> 설계 목표 : 설계 프로세스 3단계를 따라 Architecture Canvas를 구성하고, 최종적으로 Architecture Blueprint와 참조 맵 완성한다.
{: .prompt-tip }

### 1단계 : Disclose (개념 도출)
- 요구사항 분석
  + 요구사항 1
    * 의사들이 자신의 일정, 환자 검사 결과를 확인하고 긴급 사례를 선택할 수 있어야 함.
    * 사용자 프로세스 관련 개념으로 End-user 계층에 배치
    * 의사, 검사, 환자 개념은 핵심 비지니스 개념으로 Core 계층에 배치
  + 요구사항 2
    * 의사들은 병원의 다양한 부서에서 근무.
    * 병원 및 부서 개념은 Core 계층에 배치
  + 요구사항 3
    * Google Calender를 통해 예약을 확인하고 의사의 가용시간을 확인해야함.
    * 예약은 핵심 비지니스 개념으로 Core 계층에 배치
    * Google Calender 통합은 외부시스템이므로 Foundation 계층에 배치
  + 요구사항 4
    * 의사는 SMS 또는 알람으로 공지를 확인
    * 알림은 외부 시스템이므로 Foundation 계층에 배치
  + 요구사항 5
    * 웹 애플리케이션은 예약을 관리할 수 있어야 함.
    * 해당 개념은 End-user 계층에 배치

### 2단계 : Organize (개념 정리)
- 계층별 개념 배치
  + End-user Layer : 의사 모바일 앱, 예약 관리 웹 앱
  + Core Layer : 의자, 환자, 검사, 병원 및 부서, 예약
  + Foundation Layer : Google Calender 통합, SMS 및 알림 통합

- 주의사항
  + Disclose (개념 도출) 단계에서 도출된 개념을 계층에 정리하며 필요한 경우 반복적으로 새로운 개념 추가 가능함.

### 3단계 : Assemble (모듈 구성)
- 모듈화 전략
  1. 공통 생명주기 모듈
    + 관련 개념을 하나의 모듈에 결합
    + 예시 : 병원과 부서는 병원 모듈로 결합
  2. 독립된 생명주기 모듈
    + 서로 다른 생명주기를 가진 개념은 별도 모듈로 분리
    + 예시 : 의사와 환자는 별도 모듈로 구성
  3. 재사용 로직 분리
    + 재사용 가능한 로직은 Core Layer, 통합 로직은 Foundation Layer에 배치
    + 예시 : Google Calender, SMS는 서버측 통합 모듈로 구성
  4. 디자인 패턴 적용
    + 모바일 앱의 경우 로컬 저장소 및 동기화를 처리하는 모듈을 추가

- 최종 구성
  + End-user Layer : 의사 모바일 앱, 예약 관리 앱
    * 각각에 맞는 위젯/블록 및 테마를 별도 모듈로 분리
  + Core Layer : 의사, 환자, 검사, 병원, 예약
    * 예약 모듈은 병원, 의사, 검사, 환자 모듈을 조율
  + Foundation Layer : Google Calender, SMS

## Architecrue Blueprint 및 참조 맵
아키텍처 청사진 : 각 모듈이 계층에 배치된 상태를 보여준다
참조맵 : 모듈간 의존성을 화살표로 표시하여 관계를 시각화


# Architecture Conventions for Modules
> 모듈 네이밍 규칙의 중요성과 이를 사용하는 방법에 대한 내용.

## Naming Conventions for Modules

### 네이밍 규칙의 중요성
- 왜 네이밍 규칙이 필요한가?
  + 모듈 및 내부 요소의 성격을 드러냄
  + 참조 아키텍처를 강화하고, 모듈을 일관성 있게 관리할 수 있음
  + 설계 패턴을 표준화하고 팀 간 커뮤니케이션을 개선

- 네이밍 규칙의 이점
  + 모듈의 목적을 명확히 함
  + 복잡한 아키텍처 디자인에서도 패턴을 일관되게 유지
  + 모듈 관리 용이성

### 각 계층별 네이밍 규칙
1. Foundation Layer
  + _Lib: 재사용 가능한 일반 라이브러리 모듈
  + _IS: 외부시스템 통합 및 데이터 정규화를 위한 통합 서비스 모듈
  + _Drv: 특정 통합 서비스 드라이버 모듈
  + _Th: 앱의 테마 및 전체적인 외형요소
  + _Pat: 재사용 가능한 UI 패턴 및 블록
  + _Plug: 재사용 가능한 모바일 플러그인 모듈
  + 모바일 전용 모듈은 이름 앞에 "M"을 추가 (_MTh, _MIs..)
2. Core Layer
  + _CS: 비지니스와 관련된 재사용 가능한 코어 서비스 모듈 (공개 엔터티 및 비지니스 관련 작업 포함)
  + _BL: 비지니스 로직을 캡슐화하는 모듈
  + _CW: UI를 구성하는 코어 위젯 및 블록 모듈
  + _Eng: 복잡한 비지니스 규칙을 계산하는 기술적인 로직 모듈
  + _Sync: 데이터 동기화 로직을 처리하는 모듈
  + _API: 외부 소비자를 위한 API 제공 모듈
  + 모바일 정용 모듈은 이름 앞에 "M"을 추가
3. End-user Layer
  + URL에 사용되므로 짧고 직관적인 이름을 사용하는 것이 중요
  + 공백은 제거, 사용자 친화적 이름으로 설정


# Typical Module Elements
각 계층의 모듈에 포함된 일반적인 요소를 살펴봄.
아키텍처 캔버스와 함께 각 계층별 요소를 구체적으로 이해.
## Typical Module Elements
### Foundation Layer
Foundation Layer는 통합 서비스와 비기능 요구사항을 처리하며, 재사용 가능한 요소들이 정의된다.

- Data
  * Structures for inputs and outputs
  * Non-core entities
데이터 관점에서 외부 시스템의 데이터 변화를 핸들링하기 위한 input/output structure가 필요할 수 있다.
그러나 Core Entity를 가지고 있을거라 예상하지 않을 것이다.
왜냐하면 이는 integration과 non-business 기능을 위한 것이기 때문이다.

- Logic
  * Normalized APIs : Logic을 고려하면 해당 Layer는 정규화된 API 형태로 다른 모듈에 action을 제공한다.
  * Exception handling (avoid error codes) : 만약 외부 시스템과 통신이 필요하다면, 어떤 형태의 예외처리가 필요할 수 있다. 이러한 예외처리를 올바르게 처리되는 것을 보장할 수 있다.
  * (Single) sign-on and session logic : 인증 흐름이 필요한 경우 (중앙화된 SSO) 이러한 것도 Foundation Layer에서 제공된다.
  * Common Roles to a domain of users(e.g. intranet)
  : 특정 사용자 도메인에 공통적인 역할을 저장할 수 있다. 
  메니저나 직원과 같은 Role은 재사용 가능하므로, 이런 Role도 foundation moduledp 둘 필요가 있다.

- Interface
  * UI patterns or blocks (e.g. calender. accordion)
  : Foundation Layer 에서는 재사용 가능한 UI패턴 또는 Block을 정의하는 Moudle이 존재.
  * Themes, Layouts and exception flows
  :   Theme, Layout, Exception Flow는 재사용되는 요소의 예시가 될 수 있다.
  이 모든 것들은 재사용가능하며, Foundation Layer에 저장하는 일부가 될 수 있다.

  이제 Core Layer로 넘어가면, 핵심 비지니스 개념들이 나타난다.
  해당 요소들은 End-user Layer의 모듈들에 의해 소비될 것이다.

### Core Layer
Core 계층은 핵심 비지니스 개념과 관련된 데이터를 처리하고 End-user Layer에서 소비된다.

- Data
  + 핵심비지니스 엔터티는 이 계층에 위치
    *  엔터티는 읽기 전용으로 노출
    * 데이터 조작은 모듈 내 로직에 의해 제어
  + 서버 액션을 통해 데이터 변경 작업 노출
    * 기본값 설정, 감사 수행 용이

- Logic
  + Foundatoin Layer의 통합 서비스 래핑
  + 역할 : 모듈 내 기능에 대한 접근 권한 정의

- Interface
  + 재사용 가능한 비지니스 UI Block : 특정 비지니스 요구를 충족하는 UI요소

- Process
  + 비동기 데이터 처리 : 분류/동기화/집계 등 작업 수행, 비지니스 프로세스 및 타이머 활용

- 주의사항
  + 화면은 정의하지 않음
  + End-user Layer에서만 화면이 정의된다.

### End-user Layer
End-user Layer는 사용자 화면과 보조요소가 정의되는 계층
- Data
  + UI상태를 저장하는 엔터티 및 보조구조
  
- Logic
  + 폼 검증과 같은 특정 UI 사용 사례를 지원하는 비지니스 로직 포함
    * 재사용 가능한 로직은 Core Layer로 이동
  + 역할 기반 UI : 특정 사용자 사례를 지원하는 UIelwkdls
  + Work Flow 로 정의된 비지니스 프로세스 : 사용자 프로세스를 지원


### 핵심 요약
1. Foundation Layer
  + 통합 및 비기능 요구사항
  + 예시 : API, 인증, 예외처리, 테마, 재사용 가능한 UI 패턴
2. Core Layer
  + 핵심 비지니스 데이터와 로직
  + 예시 : 핵심 엔터티, 비지니스 로직, 비동기 데이터 처리
3. End-user Layer
  + 사용자 화면 및 UI 보조 요소
  + 예시: 폼 검증, 역할 기반 UI, 비지니스 프로세스


## Typical Module Elements: Doctors App

# Application Composition

