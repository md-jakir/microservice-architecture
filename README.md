# Spring Boot Eureka Service Discovery Driven Microservice Architecture
Here, Netflix Eureka Service discovery microservice consists of several modules of react fronted and java spring boot backend and functionality is information and management system for an organization. 

# Eureka Service
Accroding to design, eureka is a service discovery module and don't need to register itself but all backend module or services should be registered with this eureka.
# Gateway Service
Gateway service should be register with eureka which is responsible to establish communicaiton between fornted and backend. Gateway holds respective api pattern information and route information means incoming api request should match with api pattern and forward that request to eureka service to get details information about the respective service becasue all backend services are registerd with eureka. 






![microserce-architecture](https://user-images.githubusercontent.com/25055579/182891218-3af9de88-4f23-428d-b865-7f2631b21d71.png)
