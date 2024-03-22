---
title: "Designing Apps Using an Architecture Framework"
author: 2deeens
date: 2024-02-13 18:22:00 +0900
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

