---
title: "Block and Event"
author: 2deeens
date: 2024-01-22 18:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, outsystems, event, block]
---

# What is a Block?
> A Block is a reusable user interface component that can hold widgets, patterns and other blocks.
> Block은 재사용 가능한 요소로 위젯 / 패턴 / 다른 Block을 가질 수 있다.
{: .prompt-info}

## Block
- Block은 Screen처럼 설계된다.
- Blcok은 스스로의 scope를 가진다.
  * Input Parameter
  * Local Variables
  * Screen Actions
  * Placeholders
  * Events
- Block은 Output Parameter를 가질 수 없다.

# Using Blocks
- Block은 Screen이나 다른 Block의 내부에 위치할 수 있다.
  * Block의 부모에 위치할 수 있으나
  * 재귀는 불가능하다. (자기 자신에게 위치하는 건 불가능함
- 부모는 여러개의 Block을 가질 수 있다.
- 부모는 Block의 내부로 접근할 수 없다.
  * Event는 부모에게 통신할 수 있다.

# Placeholder
- 동적 인터페이스 자료를 위한 공간을 예약한다.
  * Instantiated(통합)될 때 정의된다.
- Block의 모든 instance는 placeholder 내부에 다른 content를 가질 수 있다.
- Block 내부에만 placeholder는 위치할 수 있다.


# Why use Blocks?
- Promte reusability
  * 한번의 개발로 여러 block과 screens을 사용할 수 있다.
  * 캡슐화, 독립성, 격리
- Improve maintainablility
  * 변경 시, Block의 모든 instance에 반영된다.
  * Inputs과 Placeholder는 각 instance에서 custom이 가능하다.



  Block Events

  # What is an Event?
  > An Event allows a Block to notify its Parent of an occurrence.
  > 이벤트는 블록이 발생한 사건을 그 부모에게 알리도록 허용한다.

  ## Events
  - Event를 통해 부모개체와 상호작용한다.
    * Block triggers an Event
    * Parent handles it 
  - Event는 Block의 내부에 생성된다.
    * Input Parameter는 부모에게 데이터를 보낸다,
    * 필수로 정의된다.

  ## Why do we need to Trigger Event?
  - Block과 부모는 다른 범위를 가진다.
  - 부모는 Block instance 내부에서 수행된 동작에 종속된 요소를 가질 수 있다.
  - Triggering Event는 Block이 부모에게 notify 하는 것을 허락한다.

  ## Handling Events
  - When a Block triggers an Event
    * Event Handler가 실행될 때
  - An Event Handler
    * Event가 trigger될 때, 실행되는 logic을 정의한다.
    * 이벤트의 input parameter로 접근권한을 가진다.
    * 부모 범위로 접근을 가진다.

  # Execution Flow
  ## Flow
  1) Block 내부의 Event가 발생한다. (Block 내부의 요일이 선택된다)
  2) Event가 trigger 되고, Event Handler로 넘어간다.
  3) Handler 내부의 Logic을 수행하고, Event가 종료된다.


  On Parameters Changed
  # Execution Flow
  - Block 내부에서만 가능하다.
  - Trigger가 자동으로 걸린다.
    * 언제든지 부모는 Block의 Input Parameter 값을 변경한다.
  - Block 내부의 Input Parameter 변경은 이벤트를 발생시키지 않는다.

  
  # Lifecycle
  1) Parameters Changed
  2) Render (Block)
  3) Render (Screen)
  4) Render (Block)
  ?? 모르겠음
  