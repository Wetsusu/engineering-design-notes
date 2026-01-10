# Index of Engineering Design Notes

This index provides a guided tour of the key design documents and architectural diagrams within this repository.

## 1. Domain Design

Focuses on business rules, domain concepts, and complex calculation logic.

- **Attendance & Work Time**
  - **Diagram**: [`domain/attendance/attendance-worktime-calculation.drawio`](./domain/attendance/attendance-worktime-calculation.drawio)
  - **Description**: A detailed diagram modeling the complex logic for calculating work hours based on Japanese labor regulations, including overtime, night shifts, and holidays.

## 2. System Architecture

Focuses on system design, scalability, and stream-based processing patterns.

- **Frontend Architecture**
  - **Document**: [`architecture/frontend/dom-overlay-iframe-interaction.md`](./architecture/frontend/dom-overlay-iframe-interaction.md)
  - **Description**: A pattern for synchronizing DOM elements (scroll, clicks) between a parent window and an iframe, especially in environments with limited framework documentation.

- **Scalability**
  - **Document**: [`architecture/scalability/company-sharding-strategy.md`](./architecture/scalability/company-sharding-strategy.md)
  - **Description**: An analysis of a hybrid database sharding strategy to ensure tenant isolation and resource allocation.
  - **Diagram**: [`architecture/scalability/sharding-and-throughput.drawio`](./architecture/scalability/sharding-and-throughput.drawio)
  - **Description**: A visual exploration of the relationship between sharding configuration and system throughput.

- **Streaming Architecture**
  - **Diagram**: [`architecture/streaming/lambda-stream-architecture.drawio`](./architecture/streaming/lambda-stream-architecture.drawio)
  - **Description**: A design for an event-driven, stream-based processing system using a Lambda architecture.
  - **Diagram**: [`architecture/streaming/stream-options-notes.drawio`](./architecture/streaming/stream-options-notes.drawio)
  - **Description**: Comparative notes on different options and trade-offs for implementing stream processing.
