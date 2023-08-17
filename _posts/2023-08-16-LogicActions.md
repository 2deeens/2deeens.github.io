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



## Variables
> 변수 : 다양한 타입의 변수 (Input parameter, output parameter), local 변수등이 존재한다,
> Data types : 크게 두가지의 데이터 타입 (혼합된) 이 존재한다. (Structures and list)

### Variables
Variables는 in memory 형태로 저장되어 데이터를 저장한다.
* hold data of a particular data type
* 데이터 타입 제한 없음

Variables는 특정 범위 안에서 존재하며 정의된다. (defined and existed in a particular scope)
* Values는 해당 범위에서 수정/접근가능하다,
* 만약 범위 밖에서 실행된다면, variables는 파괴된다.

### Variables can be ...
Variables는 아래 3가지 형태로 존재된다.    
아래 모든 변수들은 BookRoom 이라는 ServerAction 내부에서 상호작용/동작한다.
1. Input Parameter
  - Server action(BookRoom)에서의 CheckIndDate, CheckOutDate로 사용된다.
2. Local Variable
  - Server action(BookRoom)에서의 RoomType. (로컬에만 존재)
3. Output Parameter
  - Server action(BookRoom)에서의 RoomNumber, RoomType.

### Input Parameter
-  외부에서 값을 가져와서 사용한다.
- 필수로 설정되어야 한다.
  + parameter가 vaule를 할당받도록 요구된다.
- variable은 부모 elemenet의 범위를 떠나서 실행될 때 파괴된다.

### Output Parameter
- outside scope로 값을 반환한다.
- valuesms 해당 범위 내부의 output parameter로 할당되어야 한다.
- The variable은 부모 element의 scope를 떠나도 outside scope 안에서 계속해서 존재한다.

### Local Parameter
- 해당 scope 내부에서만 존재한다.
- locally한 범위안에 할당되고 사용가능하다.
- parent element 범위 밖에서 실행될 때 variable이 파괴된다. (input parmeter와 유사함)

### Outsystems Data type
- OutSystems 언어는 강력한 타입을 제공한다.
  + 모든 변수는 데이터 타입으로 선언되어야 한다.
  + 데이터 타입은 변화하지 않는다.
- OutSystems가 제공하는 타입
  + Basic Type : Integer, Text, Date ...
  + Compound Type : Entities, Structures 
  + Lists : 동일 데이터 타입들로 이뤄짐.


#### Structures
- Strucres는 custom compound data type임.
  + 모든 데이터 타입의 Attributes로 정의된다.
  + 다른 Structures를 포함한다. (Entity, List)
  + compound data type의 Collection은 함꼐 Grouped 된다.

- In Memory 로 데이터가 저장된다.
  + Structure는 데이터 타입의 정의임.
  + Structures는 어떤 값도 스스로 저장할 수 없음
    * Structres are not variables


#### List
- List는 동알한 데이터 타입의 collection 요소이다.
- OutSystems 에서 제공하는 List 요소가 될 수 있는 것은
  + Basic Types (e.g. Ingeger)
  + Compound types (e.g. Entities or Structures)
  + A union record between different types
    * e.g. Integer + Text
    * e.g. Booking + GuestName


## Quiz
1. Which of the following options is correct?

Screen Actions can call other Screen Actions from a different screen.
Client Actions can call Screen Actions.
Server Actions can call Client Actions.
Client Actions can call Server Actions.

Similarly, Screen Actions can also call Server Actions.

2. Client Actions and Server Actions can have the following variables:

Input and Output Parameters, but no Local variables.
Input Parameters and Local Variables, but no Output Parameters.
Input and Output Parameters, as well as Local Variables.
Output Parameters and Local Variables, but no Input Parameters.

They can have multiple input, output and local variables.

3. The flow of an action can have...

... multiple Start and End nodes.
... one or more Start nodes but only one End node.
... only one Start node but multiple End nodes.
... only one Start node and one End node.

Action Flows can only have one Start node and can end in different End nodes.


## Quiz2
1. Regarding the If statement, which of the following options is false?

Both True and False branches are mandatory.
Only one of the branches is executed, depending on the If condition's outcome.
If statements can also be used to implement ad-hoc loops.
More branches may be added if needed.

Not to an If. Although in Switch statements that is possible.

2. Regarding the Switch statement, which of the following options is false?

The first branch that the condition evaluates to True is executed.
Every branch that evaluates to True is executed.
If no branch evaluates to True, the Otherwise branch is executed.
The Otherwise branch must exist.

Only one branch of the Switch is executed: the first one that evaluates to True. If none, then the Otherwise is executed.


## Exceptions

> Exception이 어떻게 시작되고 어떻게 thorwn되는지 (자동 / 수동으로)),
> 또 이를 어떻게 핸들링하는지 알아봅시다.

### Rasing Exception

- Exception thrown (예외처리) 은 런타임 도중 예기치 못한 operation 실패가 발생했을 떄 발생한다.
- Exception은 Flow의 실행에서 interruption으로부터 발생한다
  * Execution은 Exception Handler flow로 이동한다.
  * Execution은 기존 flow로 돌아가지 않는다.

- Exceptoin은 
  * 플랫폼에 의해 자동으로 일어날 수 있다.
    + e.g. Database Exception
  * flow에 정의돈 어떠한 이유에 의해서 명시적으로 (explicitly) 발생할 수 있다.


### Exception Handler

- Exception이 발생할 때
  * 실행은 예외가 발생할 때마다, 특정 exection handler로 이동한다.
  * 그리고 handler flow를 따라 진행된다.

- Action은 몇가지의 exception handler flow를 가질 수 있다.
  * Database Exceptions
  * Security Exceptions
  * Communication Exceptions
  * Custom User Exceptions

### Global Exception Handler
Action flow에서 exception handler가 필수요소는 아니다.
Action내에 해당하는 exeption handler가 없는 경우, 예외가 발생한 곳에서 실행이 outer context로 이동.
즉, 일치하는 handler를 찾을 떄까지 계속 상위로 올라간다.
이것이 전역 예외처리기 (Global Exception Handler)를 정의하는 이유임.

- 만약 handler가 현재 실행 context에 존재하지 않으면
  * 해당되는 handler를 찾을 떄까지 계속 상위로 올라간다.

- Module Golbal Exception Handler
  * 기본적으로 UI FloW에 하나의 Exception Handler가 존재한다.
  * 하지만 이는 필요에 따라 수정될 수 있으며
  * 가장 상위에 존재하기 때문에, 모든 얘외를 처리할 수 있어야 한다.

### Quiz
1. Inside an Action flow...

... only one Exception Handler may exist.
... it's mandatory to have at least one Exception Handler.
... the Exception Handler flow can't intersect other flows.

Each flow must be independent from the others.

2. If we have multiple Exception Handlers in an Action flow and an Exception is raised...

... the execution is always moved to the Global Exception Handler.
... the execution is moved to the Exception Handler that is most specific to the Exception.
... the execution is moved to all Exception Handlers of the Action.
... a Switch statement is needed to select which Exception Handler will continue the execution.

Different Exceptions are handled by different specific Handlers.