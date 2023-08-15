---
title: "Service Studio Overview"
author:
  name: 2deeens
date: 2023-08-15 20:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, servicestudio]
---

# Service Studio Overview
Studio는 outsystems low-code 개발환경.
* Create applications and modules
* Define the data model
* Create user interfaces for web/mobile apps
* Define 비지니스 프로세스 (batch process)
* Debug apps

## Platform server
Outsystmes server는 스스로 생성하고 코드를 컴파일하며 배포하며 IIS처럼 실행된다.
Client to Server로 실행되며, 실제 로컬에서 실행되지 않는다.

## Environment tab
* List of applications in ther server
* Create new apps
* Install components from Forge

# Service Studio Walkthrough
Service Studio는 다양한 요소에 접근할 수 있게 도와준다.
* from business proccesses and timers
* to user interface elements, logic flows and data-related elements.

## Layers
우측 상단에 4개의 탭이 존재, 각 탭은 다음 레이어들을 표현한다.
* Processes
* Interfaces
* Logic
* Data

## True change
True change is a capability of Service Studio that validates application module.



# Application Layer
각 레이어의 기능에 대해 알아보자.

## Process
Process 는 크게 두개의 그룹으로 구성된다
1) Processes : 비지니스 프로세스, human task, automated task등을 포함한다.
* Business Processes
* Human Tasks
* Automated Tasks
* Desisions
* Events
* Waits

2) Timers : 타이머는 Task를 스케쥴러할 수 있게 도와준다.
복수의 Events가 동시에 실행될때 Timers의 중요성은 배가된다.
* Scheduled Actions (daily, weekly, etc.)
* Priorities
* Timeouts

## Interface
If focuses one the different compoenents that will make up the UI
1) UI Flows : 
* Screens
* Patterns / Blocks
2) Themes
* Base look and feel
3) Images : 두 가지의 다른 타입을 제공함
* Graphics
* Icons
4) Scripts
* JavaScript Resources

## Logic
1) Client Actions : run on the client-side (mobile device or web browser)
2) Server Actions : run on the server
3) Integrations : integrate with external systems
* SOAP Web Services
* RESTful Services
4) Roles : secure and limit who has access, can define roles and assign them to users
* Anonymous
* Registered
* Custom Roles
5) Exceptions
* Database Exception
* Security Exception
* User Exceptions

## Data
Inside the data layer, we can define the 다른 entities
Database와 locally stroage를 사용가능하게 한다.

1) Entity Diagrams : Entities를 시각화해서 볼 수 있다.
* Visual Data Model
2) Entities
* Database
* Local Storage
3) Structures : 데이터의 In-memory 표현을 structures로 표기함.
* Compound data types
* In-memory data
4) Client Variables : client-side에 user-specific data를 저장할 수 있게 해준다. (mobile device or browser)
* User-specific data
* Client-side
5) Site Properties
* Cross app data
6) Resources
* Other files


# 1-click publish

## Publication to server
Outsystems server는 Platform Server에 연결된 Platform Data의 데이터베이스의 새로운 버전을 저장한다.
그 후에 generates / compile / deploy 를 진행한다.
코드는 Application Server로 이동한다.
이 과정 동안, logic과 data model의 sync를 맞추기 위한 데이터베이스로의 업데이트가 필요하다.

## 1-Click Pulish Log
Publishing 동안 servcie studio는 publish log를 출력한다.
publishing process가 한번 끝나면 서버에서의 application 상태를 알려준다.

## Module menu : Open other Version
각 버전을 저장하고 있으며, 다른 버전으로의 롤백이 필요하다면 돌아갈 수 있다.

## Compare & Merge
여러 사람의 협업을 진행하게 되면 동일 모듈의 여러 수정이 발생한다.
Service studio가 이를 감지하고 사용자게에 merge 여부를 확인하도록 한다.
Merge도 가능하며 Overwirte도 가능하다.
Compare 기능으로 각 다른 버전을 비교할 수 있다.



# Quiz
1. In which Service Studio layer can Screens and Blocks be found?

Processes
Interface
Logic
Data

You can also find Images and Themes in this layer.

2. In which Service Studio layer can Entities be found?

Processes
Interface
Logic
Data

This is where you can find data-related elements, such as Entity diagrams and structures.
