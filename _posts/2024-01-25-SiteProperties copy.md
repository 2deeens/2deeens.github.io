---
title: "Site Properties"
author: 2deeens
date: 2024-01-25 18:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, outsystems, siteproperties]
---

# What is a Site Property?
Site Property is a server-side configuration variable that allows to store application-wide information.
Site Property는 서버측 설정변수로, 어플리케이션 전체에 걸친 정보를 저장할 수 있다.

## Site Properties
- Basic Data type and Entity Identifier로 제한된다.
- 값들은 런타임때 변경될 수 있다.
  * 개발이 필요하지 않으며
  * 잦은 변화를 피해야 한다/
- Environment-specific
  * 개발 / 운영의 다른 값

# When to use Site Properties?
- 값이 자주변경되면 않되는 경우
- Application Configuration
  * Email addr
  * API Keys
  * Enable/Disable App feautres