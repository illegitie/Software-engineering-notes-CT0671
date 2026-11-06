#version-control

Versioning means to manage multiple version of the same content.
When the software becomes complex and the code-base large, you need to
use some Version Control instrument.
# Pros of version control
- It will track the history of your software, so you can always go back in time and find out who did something and when it was done.
- It enables collaborative work, it helps you solve situations in which developers made modifications to source code that introduced conflicts
- It helps you to fix mistakes
- It helps you to manage different and potentially parallel versions of the code
# Version Control Models\
Version control is normally done with three models:
- Local
- Centralized
- Distributed
### Local versioning control
![[local vc.png]]
- Local VC means that you have a program in your PC that handles the versions of your software
- This is rarely used today for source code
### Centralized Versioning Control
![[centralized vc.png]]
- In a centralized VC, there is a server that is used to contain the data and the meta-data
- This means that all the source code is in the server and in each developer’s PC, but the meta-data (like the history of the development) resides in the server only.
- If the server is unavailable developers can’t access meta-data, if it or becomes corrupt all the meta-data are lost 
### Distributed Versioning Control
![[distributed vc.png]]
- In a distributed VC every developer has an exact copy of the data and the meta-data
- There is still one server that is used by all developers to synchronize their data, but every developer can:
	- Work on the local copy as if the remote copy was accessible, and later on push changes to the remote.
	- Restore a full copy of the server from a local copy if the server becomes corrupt.
# [[Git]]
# [[Github]]
