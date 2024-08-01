# Ask
![[Pasted image 20240801110131.png]]
Port & Adapter what for?
**Port: interface for foreign actor talk to app** -> like **USB port** let multiple devices to connect as long as they have **USB adapter**
**Adapter: Controller**
**Application: Core of the system**, contains service, domain model, receive request through port and send request out through port (send to db, for exp)
![[Pasted image 20240801110536.png]]
UI and Infra will be outside
Driving vs driven? **trigger & kicked into behavior**
- Driving Adapters will use a Port and an Application Service will implement the Interface defined by the Port, in this case both the Port’s interface and implementation are inside the Hexagon.
- Driven adapters will implement the Port and an Application Service will use it, in this case the Port is inside the Hexagon, but the implementation is in the Adapter, therefore outside of the Hexagon.
![[Pasted image 20240801114340.png]]
Dependency Inversion in the architecture??
what we achieve when apply this? 
**Seperation of concern:** seperate business from technical detail
**Flexbility:** easy swapping components (db or external services)
**Testability:** Easy to write unit tests, intergration tests, regard of seperate business