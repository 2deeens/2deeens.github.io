이 세션에서는 Aggregates를 사용하여 구현할 수 있는 고급 데이터 쿼리 기능을 소개합니다. 
Aggregates가 여러 개의 소스 엔터티를 지원하고 데이터 간에 가능한 다양한 조인 방식을 다룰 것이다.
속성과 Aggregate 내에서 어떻게 작동하는지 설명하며 마지막으로 레코드를 집계하는 방법에 대해 이야기하겠습니다.

## What is an Aggregate?

An Aggregate is a `visual element`{: .filepath} that allows you to define a `query to fetch data`{: .filepath} from
entities with sources, filters, and sorting.

> Aggregate는 필터링/정렬된 엔티티로부터 가져온 데이터를 쿼리할 수 있는 시각적인 요소
{: .prompt-tip }

## Advanced Queries with Arrgregates

데이터베이스에서 정확한 데이터를 가져오는 것은 복잡할 수 있다. 
때로는 데이터베이스에서 정확한 정보를 가져오기 위해서는 다양한 기능이 요구될 수 있다. 
Aggregates에는 여러 옵션을 지원하여 이를 쉽게 해준다.
* Multiple sorces
* Calculated attributes
* Aggregation functions

## Multiple source

Aggregates는 여러 소스를 지원하여 하나의 소스 엔터티보다 더 많은 소스 엔터티로 Aggregate를 정의할 수 있다.
엔티티가 여러 relationship이 맺어져있으면 자동으로 Join을 생성한다.

## Join Examples
Aggregates는 3가지 타입의 Join을 지원한다,
* Only With : Returns only records where there is a match between Entities.
* With or Without : 왼쪽 엔터티의 모든 행이 반환되며 오른쪽 엔터티의 행과 일치 여부와 상관없이 반환된다.
* With : Returns all rows from both entities

## Aggregate Joins in SQL

## Hiding Columns
* Hide columns for previewing purposes (Aggregate's output에 영향을 미치치 않음)
* attributes는 Aggregate 외부에서 사용된다

## Calculated Attributes
Custom value는 동일 aggregate의 다른 attribute로부터 계산된다.
쿼리 출력의 일부가 된다.
계산된 속성은 표현식으로 생성할 수 있으며 내장함수, 변수로 접근가능하다.

## Aggregating records

## Quiz
1. Consider an Aggregate with a "With or Without" join between two entities. What is the expected output of the Aggregate?

1) All records from both Entities (FULL OUTER JOIN).
2) Only records where there is a match between the two Entities (INNER JOIN).
3) All records from the left entity even if there is no match in the right entity (LEFT JOIN).
4) All records from the right entity even if there is no match in the left entity (RIGHT JOIN).

The With Or Without Join is equivalent to a LEFT JOIN, so the order of the Entities in the join matter!

2. Considering that Aggregates can have hidden columns, which of the following options is correct?

1) Hiding columns in the Aggregate only affects the preview of the output.
2) Columns that are empty in the database are automatically hidden.
3) The hidden columns help optimizing the Aggregate.
4) The hidden columns are not part of the output.

The hidden columns will still be available in the output.

3. Which of the following elements can't be used to create calculated attributes in an Aggregate?

1) Value of the attributes of the Source Entities.
2) Built-in Functions that can be translated to SQL (e.g. Length(), Power()).
3) Variables.
4) Server Actions using Entity Attributes.

We can't do that! Would it be possible to translate all Server Actions into SQL?

4. Consider that we want to apply aggregation functions in an Aggregate. Which of the following options is false?

1) We can apply multiple aggregation functions inside an Aggregate.
2) The output of the Aggregate will contain all attributes from the Source Entities plus the aggregation columns.
3) We can apply the following functions on attributes of integer data type: sum, max, min, count and average.
4) The output of the Aggregate will not include the columns at grey.

this is false. Only the aggregation columns are returned.
