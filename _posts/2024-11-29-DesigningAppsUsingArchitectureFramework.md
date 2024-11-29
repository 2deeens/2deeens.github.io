---
title: "Designing Apps Using an Architecture Framework"
author: 2deeens
date: 2024-11-29 18:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, outsystems, architecture, framework]
---

# Why is Architecture Important?

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



### Discolse
  - User Stories, Personas and Roles
  - Information Architecture
  - Integration Technology
  - User Experience Expectations

### Organize
### Assemble
- Join conceptually-related concepts
- Don't join concepts with different lifecycles
- Isolate reusable logic from integration logic

## Designing an Architecture
- The blueprint shows each Module in the corresponding layer
- add dependencies between modules.
- keep iterating the three steps of the process


# Architecture Conventions for Modules
## Naming Conventions for Modules

# Typical Module Elements
## Typical Module Elements
### Foundation Layer
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


## Typical Module Elements: Doctors App

# Application Composition

