# build-application
## module
### application
### domain
### infra
### ui
# build-core
## application
## assert
## configuration

# Hexagonal Research
```
src/main/java/com/example/
├── application
│   ├── port
│   │   ├── in
│   │   └── out
│   └── service
├── domain
│   ├── model
│   └── service
├── infrastructure
│   ├── adapter
│   │   ├── in
│   │   │   └── web
│   │   └── out
│   │       ├── persistence
│   │       └── rest
│   └── config
└── SpringBootApplication.java
```
Core domain, Adapter, Port
Port: interface, app interact with external service-db-UI
Adapter: impl of port, controller-repo-service
Domain: entity,dto,request,response
# Ask
![[Pasted image 20240801110131.png]]
Port & Adapter what for?
**Port: interface for foreign actor talk to app** -> like **USB port** let multiple devices to connect as long as they have **USB adapter**
**Adapter: Controller**
**Application: Core of the system**, contains service, domain model, receive request through port and send request out through port (send to db, for exp)