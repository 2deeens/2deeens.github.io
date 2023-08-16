---
title: "Logic Atcions"
author: 2deeens
date: 2023-08-16 10:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, logicaction]
---

# Logic Actions
> 어떻게 Logic을 정의하고, 코드 재사용성을 높일 수 있는지
> 코드 재사용성을 높이기 위해 action을 활용해야한다.

> An Action is an element that allows us to define logic flows that run on the server or client-side
> Action은 서버/클라이언트에서 실행되기 위한 logic flow를 정의하기 위한 요소.


## Actions and Flows
- Action Flow는 logic이 어디에 정의된즌지를 나타낸다.
- Start node는 1개만 가질 수 있다.
- 모든 Action은 여러 노드로 종료될 수 있다.

### Actionss
- Screen Actions : Logic specific to a single screen
  + 화면의 버튼을 누를때 실행되는 screen action
  + action의 범위는 screen's level
  + screen sidgets은 screen level과 screen input parameter에 정의된 aggregate도 포함한다.

- Client Actions : Logic to be used on the device
  + Module을 통해서 사용되며, 특정 화면내에서 제한되지 않는다.

- Server Actions : Logic to be used on the server
  + 서버에서 실행되는 actions

### Code Reusability

|-----------------|Screen Actions  |Client Actions  |Server Actions  | 
|:----------------|:---------------|:---------------|:---------------|
|Input Parameters | Y              | N              | Y              |
|Local Variables  | Y              | Y              | Y              | 
|Output Parameters| Y              | Y              | Y              |


|-----------------|Screen Actions    |Client Actions   |Server Actions  | 
|:----------------|:-----------------|:----------------|:---------------|
|same resource    | Y(Same screen)   | Y(Client action)| Y              |
|Other resource   | N                | N               | N              | 
|ETC              | Y(Client,Server) | N               | N              |
|Executed ont the | Device           | Device          | Server         |
|Where Define?    | Interface-Element| Logic           | Logic-Server   | 


### Logic Actions
### Variables
### Quiz
### Quiz2

## Exceptions
###