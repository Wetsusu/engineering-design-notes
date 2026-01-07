# Engineering Design Notes

## 📋 Overview
This repository contains design notes and diagrams created during real-world development projects. It serves as a reference for structuring complex business logic and system architecture through visual modeling and iterative design exploration.

**Purpose:**
- Clarify complex domain rules and system architecture through diagrams
- Validate design decisions and explore trade-offs
- Support implementation in uncertain or high-complexity situations
- Create a shared understanding across technical details

## 🏗️ Repository Structure

This repository is intentionally organized by **design perspective**, moving from domain understanding to system architecture:

### [`domain/`](domain/README.md) - Domain Design
Focuses on business rules, domain concepts, and complex calculation logic.
- **Audience:** Anyone needing to understand business requirements and domain-specific rules
- **Examples:** Work-time calculation based on labor regulations, attendance policies
- **Goal:** Reduce cognitive load during implementation by externalizing domain logic

### [`architecture/`](architecture/README.md) - System Architecture
Focuses on system design, scalability, and stream-based processing patterns.
- **Audience:** System designers, engineers making architectural decisions
- **Examples:** Stream processing architectures, throughput optimization, distributed system design
- **Goal:** Reason about trade-offs, constraints, and feasibility before implementation

## 📊 Quick Navigation

| Section | Description | Key Diagrams |
|---------|-------------|---------------|
| **Scalability** | Throughput and sharding strategies | [`sharding-and-throughput.png`](architecture/scalability/sharding-and-throughput.png) |
| **Streaming** | Event-driven and stream processing architectures | [`lambda-stream-architecture.png`](architecture/streaming/lambda-stream-architecture.png), [`stream-options-notes.png`](architecture/streaming/stream-options-notes.png) |
| **Attendance** | Work-time calculation and business rules | [`attendance-worktime-calculation.png`](domain/attendance/attendance-worktime-calculation.png) |

## 🔄 Workflow

All diagrams are managed in editable `.drawio` format to:
- Preserve design intent and reasoning
- Allow iteration and refinement
- Support collaborative design discussions

**PNG exports are automatically generated** when `.drawio` files are updated via GitHub Actions, making diagrams easily viewable in the repository.

## 📝 Notes
- All materials are generalized and extracted to avoid confidential or proprietary information
- Diagrams serve as thinking tools, not necessarily as final specifications
- The focus is on clarifying understanding rather than creating prescriptive documentation