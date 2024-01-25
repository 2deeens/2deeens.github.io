---
title: "Client Variables"
author: 2deeens
date: 2024-01-25 18:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, outsystems, clientvariables]
---

# What is Client Variable?
> A Client Variable is a configuration variable that allows to store long-lived and user-specific information
> Client Variable은 사용자 특정정보를 저장할 수 있게 하는 구성변수임.

# Client Variables
- Basic Data Type과 Entity Identifiers로만 설정하도록 제한된다.
- 값들은 브라우저에 저장된다.
  * 로그인 동안 유지되며
  * 로그아웃 시, default 값으로 리셋된다.
- 민감 정보를 저장하는 것은 피해야 한다.

# When to use Client Varilables?
- 캐시가 빈번하게 발생하는 값
 * Username
- 사용자 설정값 (User configuration/settings)
  * 검색 키워드
  * 페이지 당 아이템
  * Selected Layout (Grid, Table)