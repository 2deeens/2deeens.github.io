---
title: "Debugging Apps"
author: 2deeens
date: 2024-01-22 18:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, outsystems, debugging]
---

# Troubleshooting Applications
- Code 는 에러를 발생시킨다.
  * 몇몇은 실행 동안 감지되기도 한다.
- Trobleshooting application은 에러를 찾는 것과 고치는 것에 집중한다.

## What is debugging?
> Debugging is a troblueshooting technique that helps finding errors in code.
{: .prompt-info}

## Debuggin Steps
1) Add Breakpoints
2) Start Debugger
3) Run Application
4) Debug Code

### Debugging Applications (1. Add breakepoints)
- 서버와 클라이언트 엑션에서 BP를 찍을 수 있다. (Server and Client Actions)
- Service Studio는 BP를 등록한다. (Service Studio registers the breakpoints)
- BP는 디버그 패널에 리스트업된다. (Breakpoints are listed in the Debug panel)
  * 일시적으로 비활성화 시킬 수 있다.(Can be temporarily disabled)
  * 아예 제거할 수도 있다.

### Debugging Applicatoins (2. Start Debugger)
- Application will open in web browser

### Debugging Applications (3. Run the Application)
- Debbuger는 Breakpoint 안에서 실행을 일시적으로 중단시킨다.

### Debugging Applications (4. Debug Code)
- 개발자는 step by step으로 코드를 실행시킬 수 있다.
- 변수의 값을 분석한다.

## During Debugging
- Breakpoint로 실행될 때, focus는 Service Stuio로 반환한다.
- 일반적인 디버깅 오퍼레이션은 가능하다.
  * Step Over, Step Into, Step Out
  * Stop, Continue, Suspend, Abort
  * Break on All Exceptions



# Inspecting Variables

- 변수의 값들은 실행이 멈출 때, 추출될 수 있다.
  * In use by the current statement
  * Locals to the scope
  * Screen widgets
  * Client Variables
  * Global to the app (or site)
  * Selected by the developer to always be under Watch ?

# Debugging a Producer Module
- Breakpoint는 모듈이 직접 만든 요청의 실행을 멈춘다.
- 다른 모듈의 Breakpoint안에서 실행을 멈추는 것이 가능하다.
- https://myserver.com/ProductManager/