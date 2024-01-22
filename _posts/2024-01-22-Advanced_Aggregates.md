---
title: "Advanced Aggregates"
author: 2deeens
date: 2024-01-22 16:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, aggregate]
---

### What is an Aggregates?
> An Aggregate is a visual element that allows to define a query to fetch data from entities with sources, filters, and sorting.
> Aggregates는 덴티티로부터 데이터를 질의할(sources, filters, sorting) 수 있도록 시각화해주는 요소임
{: .prompt-info}

### Advanced Queries with Agregates
- 데이터베이스로부터의 정확한 데이터의 retrieving은 종종 복잡해질 수 있다.
- Aggregates는 advanced option을 갖고 있으며, 이를 편하게 사용할 수 있다.
  * Multiple Sources
  * Canculated attributes
  * Aggregation functions

### Multiple Souces
- Aggregates는 여러개의 소스를 가질 수 있다.
- Aggregates는 하나 또는 여러 소스의 엔티티를 지원한다.
- Outsystems는 Entity들이 관계를 가질 떄, 자동으로 Join을 생성한다.

### Join Examples
- Aggregatesms 3가지 타입의 Join을 지원한다.
  * Only With
    + Returns only records where there is a match between Entities
  * With or Without
    + Returns all rows from the left Entity even if there is no match in the right Entity
  * With
    + Returns all rows from both Entities

### Aggregate Joins in SQL
- FROM : Source
- INNER JOIN : Only With
- LEFT JOIN : With or Without
- FULL OUTER JOIN : With

### Hiding Columns
- 숨김 컬럼의 목적은 미리보기임.
  * 이는 Aggregate의 output에 영향을 미치지 않는다.

### Calculated Attributes
- Custom Value는 동일한 Aggregate 내부의 다른 Attribute로부터 계산한다.
- 쿼리 출력부의 일부가 된다.
- 표현식은 아래와 함께 접근할 수 있다.
  * Aggregate 내부의 Source Entity Attribute
  * Built-in Functions (CurrDate, DiffDays...)
  * Variables

### Aggregating Records
- Group multiple rows together
- 값들의 그룹별로 함수를 지원한다 : Sum, Aver, Min, Max, Count
- Only 출력부의 컬럼으로 aggregated 된다.