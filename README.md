# Spring Boot Eureka Service Discovery Driven Microservice Architecture
Here, Netflix Eureka Service discovery microservice consists of several modules of react front-end and java spring boot back-end and functionality is information and management system for an organization. 

# Eureka Service
Accroding to design, eureka is a service discovery module and don't need to register itself but all back-end module or services should be registered with this eureka.
# Gateway Service
Gateway service should be register with eureka which is responsible to establish communicaiton between fornted and backend. Gateway holds respective api pattern information and route information means incoming api request should match with api pattern and forward that request to back-end after getting details about the respective service from eureka and gateway also acts as load balancer. 
# Spring Config service
Config service also should register with eureka and it holds a git repo where has centralize YAML content. These YAML files are configured with DB information, gateway information and eureka instance information and others authentication iformation. Every back-end has a bootstrap YAML file is for conecting to config server to load the respective YAML details. 








![microserce-architecture](https://user-images.githubusercontent.com/25055579/182891218-3af9de88-4f23-428d-b865-7f2631b21d71.png)
