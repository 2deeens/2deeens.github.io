---
title: "Outsystems Overview"
author:
  name: 2deeens
date: 2023-08-10 10:22:00 +0900
toc: true
categories: [Tech, lowcode]
tags: [lowcode, event]
---

# OutSystems Overview

## What is Outsystems?
Outsystmes enables the development and delivery of enterprise web and mobile app

* low-code development environment
* Enterprise guide, full stack system
* Intergrates with other systems

## Platform capabilities
1) Integration everything : 존재하는 모든 데이터와 코드와 통합이 가능하다.
2) Visual design and development : 시각화된 개발환경을 제공
3) Standard and Optimized : 표준을 사용할 수 있으며 커스텀이 가능하다 (.NET, HTML, CSS, Javascript 등)
4) CI / CD : 지속적인 통합 및 지속적인 배포가 가능하다.
5) Flexible Infrastructure : 클라우드/온프레미스 환경 모두 사용이 가능하다


# Outsystems compoments and Tools
Administration을 위한 Service Studio, Integration Studio 같은 Tool과
Opertation을 위한 Service Center, Lifetime Tool
그리고 Forge와 Community에 대해 알아보자.

## The Platform Server
플랫폼 서버는 컴파일, 배포, 관리, 런, 모니터를 제공하는 서버 세트임.
* Compile
* Deploy
* Manages
* Run
* Monitors 

## Service Studio
Serivce Studio를 통해 Platform Server로 접속할 수 있다.
Service Studio는 웹/모바일 앱 개발환경을 제공한다.
한번의 접속으로 Create와 Publish가 가능하다.
각 버전의 Application은 Platform Database Server에 저장된다.
Application Server : 전통적인 DB를 사용하며, 외부 시스템과 통신할 수 있다. 
* Visual Design and Development

## Integration Studio
Integration Studio는 플랫폼을 확장하여 개발하는 것을 지원한다.
C# 같은 코드를 지원한다.

## Service Center
* Manage the server
Service Center는 management와 administration console을 제공하는 서버임.
웹 브라우저틀 통해 접속가능하며, 기본적인 설정이 가능하다

### Service Center - Factory
Application 현황을 볼 수 있다.

### Service Center - Monitoring
각 application 환경과 로그를 모니터랑 할 수 있다. (running appliation 포함)

### Service Center - Administration
Server를 관리하고 configure environment settings.


## Lifetime
* Manage Application Life Cycle

### Lifetime - Applications
웹에서 접속가능하며, Service Center의 기능을 확장한 것이다.
각 Application의 LifeCylcle을 확인할 수 있다.

### Lifetime - User Management
각 사용자의 권한을 설정/관리 할 수 있다.

### Lifetime - Analytics
Application들의 퍼포먼스 현황을 확인할 수 있다.
특정 포인트를 쉽게 모니터링할 수 있고, 병목현상을 확인할 수 있다.


# Capablities
Outsystems가 제공하는 capabilities에 대해 알아보자.

## Outsystmes capabilities
* Integration with everything : Application(SAP, Salseforce), Code (.Net), DB (Oracle, SQL)
* Visual Design and Development : Data Entities, Process Logic, UI
* Standard and Optimized : HTML, CSS, .Net, JS
* CI / CD : Deploy, Integrity, Governance, Monitoring
 - 이기종 환경간 배포가 가능하다.
 - 배포간, Integrity 체크를 실행하며 의존성을 확인한다.
* Flexible Infrastructure