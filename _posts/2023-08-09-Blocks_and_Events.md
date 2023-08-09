Block이 무엇인지, 사용법에 대해 알아본다.
그리고 Placeholders, Block 사용의 이점을 알아보자

## What is a Block?
A Block is a reusable user interface component that can hold widgets, patterns and other block
블록은 재사용 가능한 UI 구성요서임.

## Block
* Block은 Screens 처럼 설계된다
* Block은 각 영역을 보유한다 (Input Parameters, Local variable..)
* Block은 Output Parameter를 가지지 않는다.

Screen 내부 또는 부모 Block 같은 다른 Block에 위치할 수 있다.
* Parent of the Block
* Recursion not allowed
Parent는 Block 내부에 접근할 수 없다.
* Event는 Parent를 통해서 통신할 수 있다.

## Placeholder
Block 생성될 때, placeholder를 사용한다.
* 정의된 interface 내에서 공간을 예약한다.
* 모든 Block은 placeholder의 다른 content를 가질 수 있다.
* 이러한 요소는 Block 내부에서만 사용될 수 있다.

## Why use Block?
Block 없이도 UI 개발이 가능하지만, 몇몇 장점과 기본적인 이유가 있다.
Promote reusability : 한번 구성해놓으면 재사용 가능하며, 독립적이고 캡슐화 가능함.
Improve maintainability : Block의 모든 Instance에 변경내용 적용이 가능하다.


## Quiz
1. In OutSystems, a Block is a reusable UI component. Which of the following is NOT correct?

1) A Block promotes reusability, i.e. develop once, reuse many times.
2) A Block encapsulates its own logic.
3) A Block improves maintainability, i.e., change the design or functionality, affect all usages.
4) A Block can only be reused once.

If it's used once, maybe it doesn't need to be a Block.

2. A Block can be used...

1) Only inside other Screens.
2) Inside Screens and Blocks, including itself.
3) Inside Screens and Blocks, except on itself.
4) Only inside other Blocks.

Although Blocks can be used inside other Blocks, they cannot be used inside themselves as recursion is not allowed.

3. Regarding Placeholders, which of the following options is correct?

1) A Placeholder reserves space in the interface to be allocated when the block is instantiated.
2) When a Block with Placeholders is instantiated, it is mandatory to place at least one widget inside the placeholders.
3) Placeholders can be added to Screens and Blocks.
4) Only one placeholder may be added per Block.

And the content inside the Placeholder may be different for each instance.