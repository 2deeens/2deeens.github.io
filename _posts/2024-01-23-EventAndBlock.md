---
title: "Event and Block"
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