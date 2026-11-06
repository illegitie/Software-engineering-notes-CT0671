[[UML]]
# **Behavioral & Event-Driven Modeling**
Behavioral models depict the dynamic behavior of a system as it executes, showing what happens when the system responds to stimuli from its environment.
- **Event-Driven Systems:** Many real-time systems are event-driven, operating on the assumption that a system has a finite number of states, and events cause transitions between these states.
- **Types of Stimuli:**
    - **Data:** Information arriving that requires processing.
    - **Events:** Triggers for system processing (may or may not have associated data).
- **Key Diagrams:** Sequence, Collaboration, State (Statecharts), and Activity Diagrams.
# **Sequence Diagrams**
Sequence diagrams model the interactions between actors and objects within a system over time, typically corresponding to a specific Use Case.
- **Structure:** Read from left to right and top to bottom.
    - **Actors/Objects:** Listed horizontally at the top.
    - **Lifelines:** Dotted vertical lines descending from objects representing the passage of time.
    - **Messages:** Annotated arrows passed between lifelines.
- **System Integration:**
    - All objects in a sequence diagram must be defined in the Class Diagram.
    - All messages sent to an object must correspond to an operation/method in the receiving class.
- **Usage:** Usually models key functions, difficult scenarios, nominal cases, and key exceptions derived from Use Cases.
- **Example Class Diagram**
![[Pasted image 20261106192216.png]]
# **Collaboration Diagrams**
Collaboration diagrams (often called Communication Diagrams in modern UML) convey the same information as sequence diagrams but with a different structural focus.
- **Focus:** They emphasize object roles and relationships rather than the explicit chronological sequence of messages.
- **Structure:** Objects are linked by relationship lines, and messages are numbered (e.g., `1: selectCourse()`, `2: print()`) to indicate the order of execution.
- ![[collaboration diagram.png]]
# **State Diagrams**
State diagrams document the sequences of states an object goes through during its life cycle in response to external or internal events.
- **Usage Rule:** Only use state diagrams for classes that have state-dependent behavior (e.g., a complex controller). Simple data-collection classes do not need them.
- **Core Elements:**
    - **State:** An abstraction of an object's attribute values over a time interval (represented by rounded rectangles). Includes a unique Initial State and Final State(s).
    - **Event:** A point in time that triggers a transition.
    - **Transition:** A move from one state to another (represented by arrows).
    - **Guard Condition:** A boolean function evaluated when an event occurs, written in brackets (e.g., `[valid subscriber]`). The transition only happens if true.
- **Operations (Actions vs. Activities):**
    - **Action:** An instantaneous operation (no time passes). Used for transitions, state entry, or state exit. Syntax: `Event [Condition] / Action`.
    - **Activity:** An operation that takes time to complete (continuous or sequential). Represented inside a state with `do: activity_name`.
- **Nested States:** Complex state diagrams can expand a single state into a lower-level sub-machine to manage complexity and inherit transitions.
![[state diagram.png]]
# **Activity Diagrams**
Activity diagrams are extensions of state diagrams used to represent workflow processes, data flows, or the inner logic of an algorithm.
- **Purpose:** Highly effective for mapping out business processes or complex sequential logic (similar to advanced flowcharts).
- **Key Components:**
    - **Activity States:** Rounded rectangles representing tasks.
    - **Transitions/Control Flow:** Arrows moving the process forward.
    - **Decision Points:** Diamonds indicating branching paths based on guard conditions (e.g., `[too hot]`, `[too cold]`).
    - **Synchronization Bars:** Heavy solid lines used for parallelism.
        - **Fork:** Splits a single thread into multiple concurrent threads.
        - **Join:** Merges multiple concurrent threads back into a single thread (waits for all incoming threads to complete).
    - **Swimlanes:** Vertical columns used to allocate groups of activities to specific roles, departments, or systems (e.g., "Teacher", "Student", "Board").
![[Pasted image 20261106192559.png]]
