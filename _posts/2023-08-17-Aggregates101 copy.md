---
title: "Aggregates 101"
author: 2deeens
date: 2023-08-17 16:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, aggregate]
---

# Aggregates 101
> Aggregates는 Aggregates의 source를 다룬다.
> filtering data, sorting data, testing aggregates during development를 포함한다.

## Aggregates 101

### What is an Aggregates?
> An Aggregate is a visual element that allows to define a query to fetch data from entities with sources, filters, and sorting.
> Aggregates는 덴티티로부터 데이터를 질의할(sources, filters, sorting) 수 있도록 시각화해주는 요소임
{: .prompt-info}

### Aggregates
- 대부분 applicationdms database로부터 데이터를 가져와야 한다.
- Aggregates는 시각화된 방법으로 데이터베이스 질의를 정의한다.
  * Add sources
  * Creste Filters
  * Define Sorting
  * Test
- Aggregates는 쉽게 유지보수가 가능하다.
  * 실제 데이터가 엑셀과 유사하게 출력된다.
  * SQL의 디테일한 지식이 필요하지 않음.

### Sources
- Entity로부터 데이터를 보여준다.
- Aggregates는 하나 또는 여러 소스의 엔티티를 지원한다.
- Aggregate의 source는 데이터가 어디서 검색되는지를 결정한다.

### Filters
- 하나 또는 여러 조건의 쿼리를 필터할 수 있으며, 출력된다.
  * support for multiple filters
  * support logical operators
  * Support for some built-in functions
    + CurrDateTime()
    + If(Condition, True, False)

### Sorting
- 어느 방향으로 Entitiy attributes를 정렬할지 정의한다.
  * Ascending
  * Descending
- 여러가지 조건으로 정렬시, 출력 결과는 변경된다.

### Test Values
- 외부 변수를 위한 특정 값을 필터 또는 정렬로 출력한다.
  * 모든 변수들이 입력 필드로 나타단다.
  * 입력 필드에 값을 입력하면, 쿼리를 확인하고 미리보기를 새로고침 한다.
  * 해당 테스트 결과는 실제 값을 가지지 않는 무관한 값이다.

## Aggregates Outputs and Properties

### Outputs
첫번째로, Aggregate는 record 목록을 반환한다.
이 record 목록은 Iterator관련 설정, length, empty와 같은 몇가지 중요 설정을 갖고 있다.

- List of Records returned
  * Iterator: Current, CurrentRowNumber
    + Iterator를 통해서 반환된 레코드 목록을 반복할 수 있게 한다.
    + Current : 소스 탭 내의 엔티티 속성과 일치한다. 0부터 시작해서 전체 레코드 - 1 까지 범위로 설정된다.
    + Current는 기본적으로 첫번째 레코드를 가리키며
    + 레코드 반환이 없는 경우에는 해당 데이터 유형의 기본값을 가지게 된다.
  * Length
    + 반환된 레코드 수를 나타낸다.
  * Empty
    + 집계에서 정의한 조건과 일치하는 레코드가 없는 경우 true가 되며,
    + 레코드가 있는 경우 false가 된다.
- Count
  * 쿼리 조건과 일치하는 레코드의 전체 수를 나타낸다.
  * 이 값은 목록의 length와 다를 수 있다.
  * query 조건과 일치하는 레코드 수를 나타낸다.


### Properties
source, filter처럼 정의된 속성들이 존재한다.
- Max Records : Aggregate로 반환되는 레코드 수를 제한할 수 있다. (Count 출력 값에는 영향을 주지 않음)
- Excuted SQL : Read-Only 속성으로 Aggregate로부터 생성된 SQL 상태를 나타낸다.

### Aggregates as SQL
Aggregate 생성에는 SQL 지식이 필요하지 않음.
SELECT SQL 쿼리로 번역되며, 이는 모듈이 publish 되는 컴파일 단계에서 진행된다.
* FROM : Source
* WHERE : Filter
* ORDER BY : Sroging

## Quiz
1. In an Aggregate, the Sources section is used for...

Defining values for testing the Aggregate's output records.
Defining the Entities we want to retrieve records from.
Defining conditions to get specific subsets of records.
Defining the order of the Aggregate's output records.

Yes! Aggregates support one or more source Entities and with relationships defined between them.

2. Considering that we can add several filters to an Aggregate, which of the following options is false?

A record is included in the output if it matches at least one of the filters.
Filters are concatenated with the AND operator.
All filters are translated to SQL and included in the WHERE clause.
Logical operators and some built-in functions can be used inside filters.

For a record to be included in the output result it must be true for all filters defined.

3. Regarding Sorting in Aggregates, which of the following options is correct?

Aggregates only support one sorting criterion.
If more than one sorting criterion is defined, all of them must have the same direction (ascending or descending).
It is mandatory to set the direction for all sorting criteria (ascending or descending).
It is only possible to set multiple sorting criteria if duplicate records exist in the entity.

Sorting criteria direction has to be either Ascending or Descending.

4. In an Aggregate, the purpose of the Test Values section is…

To define values for testing the preview of the Aggregate's output.
To set the conditions to get specific records, not all the records.
To define the order of its output records.
To define the Entities we want to get records from.

The Test Values section is used for testing the Aggregate and preview the output records.