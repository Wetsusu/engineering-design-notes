# Domain Design Notes

## 🎯 Overview
This directory focuses on **domain-level design and business logic structuring**. The diagrams aim to clarify complex rules and concepts, especially where specifications tend to become ambiguous or tightly coupled to implementation.

## 📂 Subdirectories

### Attendance
Focuses on work-time calculation and attendance policies based on labor regulations.
- **Key Challenge:** Complex rules and edge cases derived from real operational constraints
- **Contents:**
  - `attendance-worktime-calculation.png` - Work-time calculation logic and business rules

## 🎯 Design Intent

The primary purpose of these materials is to:
1. **Reduce cognitive load** - Externalize complex logic to support implementation
2. **Create shared understanding** - Make domain rules explicit and discussable
3. **Prevent implicit coupling** - Keep logic visible rather than buried in code
4. **Enable validation** - Facilitate conversation about edge cases and requirements

## 💡 Design Philosophy

These diagrams are intentionally **kept close to the problem domain** rather than optimized for any specific technical architecture. This approach:
- Makes business rules easier to understand and discuss
- Reduces dependency on implementation details
- Facilitates cross-functional collaboration
- Creates stable references as systems evolve

## 🔄 Workflow
All diagrams are maintained in editable `.drawio` format. This allows:
- Easy iteration as domain understanding evolves
- Visual representation of complex rule sets
- Preservation of design rationale through diagram annotations