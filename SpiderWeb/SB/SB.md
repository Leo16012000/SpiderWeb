[[Spring vs Spring Boot]]
[[Structure]]
[[Dependency Injection]]
[[Application Context]]
[[Annotation]]
[[Inversion of Control]]
[[Garbage Collector]]
[[Best practices SB]]
# I. Customizing Configuration
# 1. Configuration properties
application.properties || application.yml
yml hierachy cao, dễ manage 
## 2. Profiles
application-dev.yml,
application-staging.yml
...
define which enviroment with spring.profiles.active
Dùng @Profile có thể quyết định Bean nào được khởi tạo với profile nào
# External resource
Command line > Environment variables > properties file
Can use spring.config.location -> define config file location

