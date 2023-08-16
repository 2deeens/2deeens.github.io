---
title: "Modeling Data"
author: 2deeens
date: 2023-08-15 23:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, modelingdata]
---

# Modeling data

- Application은 business와 관련된 정보를 포함하고 있다.
 + 이러한 정보는 일반적으로 저장 / 가공을 필요로 한다.
- Application information 또는 데이터는 다양한 business 컨셉을 표현한다.
- Outsystems에서는 이러한 컨셉들을 Entities로 모델링할 수 있다.
 + Database Entities는 database로부터 데이터를 retrieve하고 저장할 수 있다.

## Modeling data
- Entities는 development environment 내부에 define/create 된다.
 + Attributes
 + Relationships

### Entity to Database Mapping

| Outsystems Entity            | Database Table       | 
|:-----------------------------|:---------------------|
| Attribute (Data types sw)    | Columns Data types   |
| ID (Identifier attributes)   | Primary Key          |
| Reference Attribute          | Foreign Key          |
| Index                        | Index                |
| Record or Instance           | Row or Tuble         |


### Quiz
1. Business concepts that need to be stored and accessed in our applications should be modeled as...

+ [ ] Entities.
+ [ ] Entity diagrams.
+ [ ] Entity relationships.
+ [ ] Database tables.

> Ideally, each business concept will be mapped into a single entity.
{: .prompt-tip }


2. Which of the following mappings between OutSystems and the Database is NOT correct?

+ [ ]Entities - Tables.
+ [ ]Attributes - Column.
+ [ ]Reference attribute - Primary Key.
+ [ ]Index - Index.

> Ooops... Entity identifiers are the ones that are mapped into primary keys.
{: .prompt-tip }


## Database Entities

어떻게 entity들은 attribute를 가지는지, attribute를 위한 기본 데이터 타입에 대해 알아보자.

> * An Entity is an element that allows us to persist and access information that is needed in our applicaionts
> * 엔티티는 application에서 필요한 정보들을 접근할 수 있도록 해주는 요소.
{: .prompt-tip}

### Entity
- 각 Business 컨셉은 entity로 표현되어야 한다.
- Entity data는 database table에서 지속된다.
 + Entity의 새로운 record는 상응하는 table에 row로 삽입된다.
- Entities...
 + store sets of data
 + have attributes
 + have entity actions

### ID Attribute
- 자동으로 생성된다.
- Record에서 유일하게 식벽된다.
- Database table의 primary key로 작동하며
- Enity간의 관계를 설정할 때 사용된다.

### Attributes
- Entity data는 Attribute에 저장된다
- Attribute는 비지니스 컨셉을 표현한다.

### Basic Data Types
basic data type에 따르면 Outsystems에는 몇가지 옵션이 존재한다.

Alphanumeric
: types like text, phone number

Numeric
: integer, Long integer, Decimal, Crrency

Dates and Times
: Date time, date, time

Logic
: Boolean

Large Object
: Binary data, images, for instance

Referential
: Entity Identifier

### Entity Actions
- Automatically created
- CRUD data oprations
- Entity action은 application 비지니스 로직에서 바로 사용할 수 있다.

### QUiz
1. Which of the following statements about Entities is false?

+ [ ] Entities have attributes.
+ [ ] Entities do not require an identifier.
+ [ ] Entities are only stored in memory.
+ [ ] Entities can be created, updated, and deleted.

Entities are persistent and are actually created in the database as tables.

2. If an Entity Attribute named HouseNumber is created, what needs to be done about its Data Type?

+ [ ] It should be set to Integer.
+ [ ] It should be set to Decimal.
+ [ ] Nothing, it will automatically be set to Identifier.
+ [ ] Nothing, it will automatically be set to Integer.

The OutSystems Data Type Inference mechanism handles it.

3. Which of the following is not an Entity Action of the Customer Entity?

+ [ ] CreateCustomer.
+ [ ] RetrieveCustomer.
+ [ ] UpdateCustomer.
+ [ ] DeleteCustomer.

The Entity Action that allows retrieving data is the Get.

## Static Entities

> Static Entities are a special type of Entity that creates a predefined list of values that can be used in our applications
> Static Entity는 미리 정의된 값의 목록을 생성할 수 있는 특별한 타입이다.
{: .prompt-info}

### Static Entities
- Static Entity는 enumerations처럼 작동한다,
 + List of items(Records) in a collectoin
- Static Entity는 Attribute와 Record를 갖는다
 + 디자인과 개발간에 정의된다.
 + runtime떄는 수정/변경 불가능
- Only 1 Entity Action
 + The Get Entity Action

 ### Attributes
 - Static Entity는 4가지 기본 attribute와 함께 생성된다.
  + Id
  + Labe
  + Order
  + Is_Active
- 위 4가지 attribute는 변경할 수 있다 (name)
- 다른 attribute 추가 가능함.

### Records
- Static Entity는 Set of Records를 갖고 있다.

### Quiz
1. Which of the following is a characteristic of a Static Entity?

+ [ ] It can't be changed after the first publish.
+ [ ] It contains a set of Records.
+ [ ] It has two Entity Actions.
+ [ ] It can't be extended with any new attributes.

As many as you want but they need to be defined during development.

2. Regarding the Records of a Static Entity, which of the following options is false?

+ [ ] The values for all 4 default attributes must be defined.
+ [ ] Records can only be added and removed during development.
+ [ ] The record identifier is the identifier of Static Entity.
+ [ ] The Identifier attribute is required for all Static Entities.

Attributes of static entities can be mandatory or not. A value is only required to be set if the attribute is mandatory.

3. Static Entities are most similar to which other programming concept?

+ [ ] Linked lists.
+ [ ] Enumeration.
+ [ ] Hash Maps.
+ [ ] Static variables.

This is the closest one.