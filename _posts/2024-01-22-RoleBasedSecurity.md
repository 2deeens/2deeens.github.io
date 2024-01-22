---
title: "Role Based Security"
author: 2deeens
date: 2024-01-22 17:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, outsystems]
---

### What is Access Contol?
> Access control determines and enforces who can do what
> who : Business Users Roles
> what : Access Screens Add Data to the database
{: .prompt-info}


### Authentication and Authorization
- Access control은 Authentication과 Authorization으로 구성된다.
  * Authentication (인증)
    + 누구인지 식별하는 절차
    + 사용자 유효성 검증 (Username and password...)
  * Authorization (허가)
    + 해당 사용자가 실행가능한 task 인지 여부를 확인하는 절차
    + 필요한 권한이 부여되었는지를 확인한다.

    
### Usres
- End-users는 built-in Users Application에서 생성되고 관리된다.
  * Defulat Outsystems end-user provider에서 가능함.
  * https://<your_server>/USers
- 사용자의 주요 정보(Core Information)는 username and passworddla
- Can be Created programmatically
  * Actions from the Users module

### Roles
- Authorization(허가)는 Roles를 통해 부여된다.
- Built-in Roles
  * Anonymous
  * Registered
- 로그인한 모든 End-users들은 Registrered Role을 갖고 있다.
- Application-specific Role은 생성될 수 있다.
  * 각 Role은 Check, Grant, Revoke Action을 갖고 있다.

### Granting Authorization
- 허가는 Role을 통해 부여된다. (Authorization is granted via Roles)
  * Role은 사용자에게 할당될 수 있다.
- Authorization은 관리될 수 있다.
  * Programatically
    + Grant and Revoke Actions
    + Can be used in Server Actions
  * Manually in the Users app

### Checking Permissions
> Roles can be checked in Screens and Actions

### Checing Permissions on Screens
- Screen Roles Property
  * 사용자에게 스크린 접근 권한중 하나를 부여하도록 강제한다.
- Check<RoleName>Role(UserId) Action
  * 사용자가 Role을 가지고 있는지 여부를 확인
  * 서버액션에서 상태가 사용가능한지를 확인

### Access Contol in Outsystems
- Define the user
- Grant a Role to a User
- Define / Check Permissions