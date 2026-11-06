**[[Introduction]]**
# Software process models
### Software processes involve:
- Specification: defining what the system should do
- Design and implementation: defining the organisation of the system and implementing the system
- Validation: the system does what the customer wants
- Evolution: responding to changing customer needs
## Waterfall model
**Plain-driven model: distinct phases**
Good for:
- Well understood requirements
- Limited changed during design
- Businesses with stable requirements
![[waterfall.png]]
## Incremental Development
### Benefits:
- Cost of accommodating changes is reduced 
	 - Amount of analysis and documentation is reduced
- Easier to get customer feedback
- Rapid delivery and development
### Disadvantages
- Process is not visible
	Managers need regular deliverables to measure progress. If systems are developed quickly,
	it is not cost-effective to produce documents that reflect every version of the system.
	System structure tends to degrade as new increments are added
	Unless time and money is spent on refactoring to improve the software, regular change
	tends to corrupt its structure.
![[incremental dev.png]]
## Integration and Configuration
Based on software reuse where systems are **integrated** form existing components or application systems (**COTS**).
Reused elements may be **configured** to adapt their behavior and functionality to a user’s
requirements. **e.g, web services**
## Incremental delivery
**Incremental development
- Develop the system in increments and evaluate each increment before proceeding to the next one.
- Earlier increments include the highest priority requirements.
- Evaluation done by user/customer proxy.
- Freeze increment requirement once development started.
**Incremental delivery
- Deploy an increment for use by end-users;
- More realistic evaluation about practical use of software;
- Difficult to implement for replacement systems as increments have less functionality than the system being replaced.
![[integration dev.png]]
**Advantages**
- Customer value can be delivered with each increment so system functionality is available earlier.
- Early increments act as prototypes for future increments
- Lower failure risk
- Highest priority services tend to receive the most testing
**Disadvantages**
- Most systems require basic facility test that are used by diff services of a system
- Essence of iterative processes

## [[Agile Software Development]]

Agile is software development principle that is geared for rapid software delivery

# SCRUM
A team-based framework to develop complex systems and products.

Scrum is an agile method with focus on *iterative development* rather than specific agile practices.
**Scrum phases:**
- Initial phase is an *outline planning* phase where you establish the general objectives for the project and design software architecture.
- Followed by a series of sprint cycles, which each cycle develops an increment of the system
- Closure phase wraps up the project, completes required docs, e.g. user manuals etc.
**Benefits:**
- Project is broken down into small chunks. Unstable reqs do not hold up progress
- Good visibility
- On-time delivery and trust between customers and devs
**Terminology**

| Scrum term                              | Definition                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Dev team                                | Team of software devs, no more than 7 people                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Potentially shippable product increment | Software increment that is delivered from a sprint. It is in a finished state and no additional work is no needed for integrating it in final project. in practice, it is not always achivable                                                                                                                                                                                                                                                                                |
| Product Backlog                         | List of 'todo' items which Scrum team must tackle.                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Product owner                           | Individual (or a small group) who identifies product features or reqs, prioritize these for dev and continuously review product's backlog.                                                                                                                                                                                                                                                                                                                                    |
| Scrum                                   | Daily meeting of a Scrum team that reviews progress etc.                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ScrumMaster                             | The ScrumMaster is responsible for ensuring that the Scrum process is followed and<br>guides the team in the effective use of Scrum. He or she is responsible for interfacing with<br>the rest of the company and for ensuring that the Scrum team is not diverted by outside<br>interference. The Scrum developers are adamant that the ScrumMaster should not be<br>thought of as a project manager. Others, however, may not always find it easy to see the<br>difference. |
| Sprint                                  | A dev iteration. Sprints are usually 2-4 weeks long                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Velocity                                | An estimate of how much product backlog effort a team can cover in a single sprint.                                                                                                                                                                                                                                                                                                                                                                                           |
**Scrum process**
![[scrum process.png]]
**Scrum sprint cycle**
![[scrum sprint cycle.png]]
