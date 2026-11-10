#req-engineering 
[[UML]]

![[reqdoc.png]]
A complete requirements specification provides the baseline for design, implementation, and testing. The standard document structure includes:
1. **Overall Description:** The high-level context and basic functions of the system.    
2. **Stakeholders:** The roles (users, administrators, buyers, secondary systems) directly or indirectly affected by the project.
3. **Context Diagram and Interfaces:** Defines the system boundary, external actors, and the physical/logical interfaces (e.g., GUI sketches, XML/JSON data exchange, procedural PDL) connecting them. (Use Case Diagrams)
![[context.png]]
4. **Requirements:** The itemized list of functional, non-functional, and domain requirements.
5. **Use Case Diagram:** Maps primary actors to the functional goals they want to achieve within the system.
![[usecase.png]]
6. **Scenarios:** Step-by-step sequences of interactions (including nominal and exception paths) constrained by defined pre-conditions and post-conditions.
7. **Glossary:** Explicit definitions of terms (often formalized using UML Class Diagrams) to prevent misinterpretation of domain language.
![[glossary.png]]
8. **System Design:** The internal hardware and software subsystems that live strictly _inside_ the context diagram boundaries.
![[system design.png]]
 