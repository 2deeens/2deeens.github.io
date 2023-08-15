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

## Entity to Database Mapping
| Outsystems Entity            | Database Table          | 
|:-----------------------------|------------------------:|
| Attribute (Data types sw)    | Columns Data types      |
| ID (Identifier attributes)   | Primary Key             |
| Reference Attribute          | Foreign Key             |
| Index                        | Index                   |
| Record or Instance           | Row or Tuble            |

| Company                      | Contact          |
|:-----------------------------|-----------------:|
| Alfreds Futterkiste          | Maria Anders     |
| Island Trading               | Helen Bennett    |
| Magazzini Alimentari Riuniti | Giovanni Rovelli |

## Quiz
1. Business concepts that need to be stored and accessed in our applications should be modeled as...

- [ ]Entities.
- [ ]Entity diagrams.
- [ ]Entity relationships.
- [ ]Database tables.

> Ideally, each business concept will be mapped into a single entity.
{: .prompt-tip }

2. Which of the following mappings between OutSystems and the Database is NOT correct?

- [ ]Entities - Tables.
- [ ]Attributes - Column.
- [ ]Reference attribute - Primary Key.
- [ ]Index - Index.

> Ooops... Entity identifiers are the ones that are mapped into primary keys.
{: .prompt-tip }


## Database Entities

## Static Entities
