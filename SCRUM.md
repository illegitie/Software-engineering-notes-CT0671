[[Introduction]]

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
![[Pasted image 20261106142536.png]]
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
![[Pasted image 20261106142854.png]]
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
![[Pasted image 20261106144144.png]]
**Advantages**
- Customer value can be delivered with each increment so system functionality is available earlier.
- Early increments act as prototypes for future increments
- Lower failure risk
- Highest priority services tend to receive the most testing
**Disadvantages**
- Most systems require basic facility test that are used by diff services of a system
- Essence of iterative processes


[[Agile Software Development]]