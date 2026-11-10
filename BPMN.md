#uml 
[[UML]]
# **Introduction: Relevance and Uses of BPMN**
Before diving into the elements, it is important to understand why BPMN is used.
- **Relevance:** BPMN provides a graphical notation that is readily understandable by all business users—from the business analysts that create the initial drafts of the processes, to the technical developers responsible for implementing the technology that will perform those processes, and finally, to the business people who will manage and monitor those processes.
- **Core Uses:**
    - Visualizing business processes and workflows.
    - Standardizing communication between stakeholders (bridging the gap between business and IT).
    - Providing a basis for process automation and simulation.
# **Basic Element Categories**
BPMN diagrams are built using a small set of core graphical elements, categorized into:
1. Tasks
2. Events
3. Gateways
4. Connecting Objects
5. Swimlanes
6. Artifacts
# Tasks
A Task is a generic term for work that a company performs. Generally, an end-user or an application executes the task.
- **Task Types:**
    - **Manual Task:** Work performed without software.
    - **Human/User Task:** Work performed by a human with the assistance of a software application.
    - **Message Task:** Task triggered by or sending a message.
    - **Service Task:** Automated task performed by a web service or automated application.
    - **Script Task:** Automated script executed by the business process engine.
    - **Rule Task:** Task evaluated by a business rules engine.
![[task types.png]]
# **Events**

An Event is something that happens during the course of a Business Process. They affect the flow and usually have a trigger or a result.
- **Start Event:** Indicates where a process will start (instantiated). _E.g., Message Start (receives an order), Timer Start (starts every Monday at 8 AM)._
- **Intermediate Event:** Occurs between a start and end event. It affects the flow but does not start or directly terminate the process.
- **End Event:** Indicates where a process will end. Note: End events do _not_ consume tokens if other parallel paths are still active (they terminate their specific thread, or the whole process if it's a Terminate End Event).
![[event types.png|455]]
# **Gateways**

Gateways are convergence and divergence points for Sequence Flows. They control the branching and merging of process paths.
- **Exclusive Gateway (XOR - "X" or blank diamond):**
    - _Split:_ Only ONE of the outgoing paths will be chosen based on conditions (Data-based or Event-based).
    - _Join (Exclusive Merge):_ Passes on each arriving token individually. "Join without a gateway is an exclusive merge."
- **Parallel Gateway (AND - "+" diamond):**
    - _Split (Fork):_ Divides a path into two or more parallel paths. Activities are performed concurrently. A split without a gateway defaults to a fork.
    - _Join:_ Synchronizes multiple parallel paths. It waits for _all_ incoming sequence flows to arrive before continuing.
- **Inclusive Gateway (OR - "O" diamond):**
    - _Split:_ Evaluates conditions on all outgoing paths. Any combination of paths (one, multiple, or all) may be taken. Usually requires a default path.
    - _Join:_ Synchronizing merge that waits for all _active/enabled_ upstream paths, but does not wait for paths that were never activated.
![[gateways types.png]]
# **Connecting Objects**
- **Sequence Flow (Solid line, solid arrow):** Shows the order in which activities will be performed _within_ a Process (or Pool).
- **Message Flow (Dashed line, open arrow):** Shows the flow of messages between two separate Process Participants (e.g., between two different Pools).
- **Association (Dotted line):** Associates data, text, and other Artifacts with Flow Objects.

# **BPMN - example**
![[bpmn example.png]]
# **Pools and Lanes (Swimlanes)**
Swimlanes organize and categorize activities.
- **Pool:** Represents a Participant (a major business entity or external party) in a process (e.g., Customer, Enterprise).
    - _CRITICAL RULE:_ A Sequence Flow may **not** cross the boundaries of a Pool. Interactions between pools must use Message Flows.
- **Lane:** A sub-partition of a Pool, often representing a specific role, department, or system within that entity (e.g., Accounting Lane and Manufacturing Lane inside the Enterprise Pool).
 ![[lanes.png]]
# **Artifacts**

Artifacts provide additional information about the process without strictly affecting the sequence flow.
- **Data Object:** Shows data required or produced by Activities (connected via Association).
- **Group:** A visual grouping of elements for documentation purposes; it has no effect on the process flow.
- **Text Annotation:** A text comment connected to an element via an Association to provide clarity.
![[artifacts.png]]
# BPMN diagram of Loan Request
![[loan request.png]]