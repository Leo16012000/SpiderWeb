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
