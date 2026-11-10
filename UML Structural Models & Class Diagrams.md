#uml 
### Classes vs. Objects
- **Class:** A general definition or descriptor of objects with similar properties (identity, attributes, operations, messages). Represented as a rectangle with Name, Attributes, and Operations.
- **Object:** A specific instance of a class. The attribute _names_ are the same as the class, but the _values_ are unique to the object.
### Multiplicity
Constraints on the maximum/minimum number of links that can exit from an object:
- `1` : No more than one (Exactly one)
- `0..1` : Zero or one
- `*` or `0..*` : Zero to many
- `1..*` : One to many
### Core Relationships in Class Diagrams
Relationships between classes define how objects interact or are structured together.
- **Reflexive Relationship:** A class has a relationship with itself (e.g., a `Person` class where one person is the parent of another `Person`).
- **Aggregation:** A "is-part-of" relationship where the lifecycle of the parent is **independent** of the child. (e.g., A `Car` has an `Engine`. If the car is destroyed, the engine can still exist).
- **Composition:** A stricter "is-part-of" aggregation. The parent and child share the **same lifecycle**. If the parent object is destroyed, the child objects are destroyed. (e.g., A `Person` and a `Head`).
- **Generalization (Inheritance):** An "is-a" or specialization relationship. The child class inherits all attributes and associations of the parent class but can add its own properties. (e.g., `Student` is-a `Person`).
### Association Classes
Allows you to attach attributes directly to a relationship (association) between two classes.
- _Alternative:_ You can use an intermediate class (Role).
- _Difference:_ An intermediate class allows _more than one_ value for a pair, while an Association Class allows _only one_ value for a pair.
### Object Constraint Language (OCL)
Used to express complex constraints textually when visual multiplicity isn't enough (e.g., `Invariant: Exam.grade >= 0 && Exam.grade <= 100`).