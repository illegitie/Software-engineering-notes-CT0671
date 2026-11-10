#req-engineering 
### Functional Requirements
Define system capabilities, behaviors, and services. They should be hierarchically numbered (e.g., F1, F1.2) to track implementation status and testing coverage.

| Req ID | Description                |
| ------ | -------------------------- |
| F1     | Handle sale transaction    |
| F1.2   | Start sale transaction     |
| F1.3   | End sale transaction       |
| F2     | Authorize and authenticate |
| F2.1   | Log in                     |
| F2.2   | Log out                    |
| F2.3   | Define account             

### Non-functional Requirements
Define quality attributes and constraints applied to the system as a whole.
- According to ISO 9126 / ISO 25010, key properties include functionality, reliability, usability, efficiency, maintainability, and portability.
- NFRs _must_ be testable and measurable (e.g., "function execution in less than 1msec" instead of "fast").
- Conflicting NFRs (e.g., minimizing physical weight vs. minimizing power consumption) require negotiation to determine priority.
![[non_func.png]]
### Domain Requirements
Application-specific characteristics and rules (e.g., physics formulas for train deceleration) that are mandatory for the system to function correctly.
- Understandability
	- Requirements are expressed in the language of the application domain;
	- This is often not understood by software engineers developing the system.
- Implicitness
	- Domain specialists understand the area so well that they do not think of making the domain requirements explicit.
	