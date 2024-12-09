---
title: "Validating Modules Architecture"
author: 2deeens
date: 2024-11-29 09:22:00 +0900
toc: true
categories: [Tech, LCAP, ArchitectureSpecialist]
tags: [lowcode, outsystems, architecture]
---
# Validating modules' Architecture
## Why?
Build applications fast, build them right, build them for the future.

1) Promotes the correct abstraction of reusable services and components
2) Optimized lifecycle independence
3) Minimizes impact of changes
4) Avoid poor service abstraction
5) Stop unmanageable dependencies
6) Prevent slow deployments, inflexible legacy systems

## Validation Rules for Modules

Rule 1 : No Upward References
- we should not have upward references across layers
- An upward reference can create a cluster, where any two modules directly or indirectly have a circular dependency.
- The circular dependency can cause any module that references an element inside the cluster to be dependent on the entire cluster
순환참조는 클러스터 내부에 있는 요소를 참조하는 모든 모듈들이 전체 클러스터에 의존하도록 할 수 있다.

Rule 2 : No Side References between end-user modules
- but, the rule has exception. screen references between end-user modules are allowed. (Weak screen reference)

Rule 3 : No circular References
- if you follow the first rule, you should not have circular references between modules in different layers.
- Following the second rule prevents cycles between end-users modules.
- however we still to avoid circular references in the core and foundation layers.
- Cylcles are always undesirable, since they bring unexpected impacts.

## Extra Recommendations
- Recommendation 1 : No Front-end Screens in Core Modules
- Recommendation 2 : Read-only entities
- Recommendation 3 : No business logic in Foundation Layer
- Recommendation 4 : No Core Entities in Foundation Layer
 -> Foundation Layer에 Entities가 불가하다는 뜻이 아님. Audit 같은 경우는 가능함. (Non-Functional Requirment)


# Validating Apps' Architecture

## Why
1) Promotes abstraction of reusable services
2) Optimizes lifecycle independence
3) Minimizes impact of changes

Benefits


## Validation Rules for Application Composition
1) Layer Modules Correctly
2) Layer Applications Correctly
3) Don't Mix Owner
4) Don't Mix Sponsors