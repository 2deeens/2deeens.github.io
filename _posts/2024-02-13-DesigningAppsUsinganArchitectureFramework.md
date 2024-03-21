---
title: "Designing Apps Using an Architecture Framework"
author: 2deeens
date: 2024-02-13 18:22:00 +0900
toc: true
categories: [Tech, LCAP]
tags: [lowcode, outsystems, architecture, framework]
---

# Why is Architecture Important?

## Building Quantity Software
> Why is application architecture important when building quantity software solutions?

### ISO / IEC
ISO, IEC put together statndard on the quality of software solutions.
this standard included several diffrent dimensions.
- Usablility (사용성) : the point of view of the users
- Functionality (기능성) : a set of functions that satify needs
- Efficiency (효율성) : which of relate performance to the amount of resources used.
- Maintainability (유지보수성) : which of relates to the effort needed to make modifications.
- Portability (이식성) :  which defines the ability to move software between environments.
- Reliability (신뢰성) :  which ensures that a software solution can maintain.

Updated
- Security (보안성) : can protect information and data.
- compatibility (호환성) : can work together with other systems.

## Lack of Architectural Concerns
- Poor service abstraction
  * Business concepts not correctly isolated and abstracted.
  * Business rules spread over diffrent systems, and little no code reuse
- Unmanageable dependencies
  * Systems not isolated from each other
  * Updating or replacing a system has a cascade effect on other systems
- Inflexible and slow-moving legacy systems
  * Adapting legacy systems to business changes may be difficult
  * Changes in complex and inflexible systems can take a long time

## Why is Architecture Important?
- Drives Consensus
- Manages Complecity
- Reduces Risk
- Supports Planning
- Facilitates Changes
- Reduces Cots


# Outsystems Architecture Framework
## The Architecture Canvas
> The Architecture Canvas is a framework to support application architecture design in Outsystems.

- It is a multi-layer framework, composed of three layer
  * End-User : should not have any services
    + User Interface and Processes : Provide functionality to end-users (intersection through user interfaces and processes)
  * Core : Reusable Services
    + Include the services around business concepts such as : their dependencies and business rules
    + these core business services should be system agnostic
  * Foundation : Reusable Services
    + Non-Functional Requirements : Services to connect to external systems or to extend your framework
    + In this layer, should not have any business-specific services.

- Why use Architecture Canvas?
  * Promotes abstraction of reusable services and components
  * Optimizes lifecycle independence
  * Minimizeds impact of changes

### Outsystems in an Enterprise Echosystem


## The Architecture Design Process
### Discolse
### Organize
### Assemble

## Designing an Architecture

# Architecture Conventions for Modules
## Naming Conventions for Modules

# Typical Module Elements
## Typical Module Elements
## Typical Module Elements: Doctors App

# Application Composition

Breeze
CodeEasier