#uml 
### Core Components
- **Actor:** Someone (user) or something (external system) that exchanges info with the system (triggers inputs or receives outputs).
- **Use Case:** A discrete task or functional unit within the system representing a set of scenarios tied to a user goal.
### Relationships in Use Case Diagrams
- **Interacts:** Standard association between an Actor and a Use Case.
- **`<<include>>`:** Use Case A is used to implement Use Case B. It is a mandatory dependency.
- **`<<extend>>`:** An optional extension. Use Case B _may_ be augmented by the behavior of Use Case A under specific conditions (inserted at an "Extension Point").
- **Generalization:**
    - _Between Actors:_ Actor B inherits from Actor A (can communicate with the same use cases).
    - _Between Use Cases:_ Use Case B is a specialized version of Use Case A.