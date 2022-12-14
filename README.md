# Spring Boot Eureka Service Discovery Driven Microservice Architecture
Netflix Eureka Service discovery microservice consists of several services of react-JS as a front-end and spring boot as a back-end and functionality is information and management system for an organization. Every fron-end is dockerize with nginx config file. 

# Eureka Service
Accroding to design, eureka is a service discovery module and don't need to register itself but all back-end services should be registered with this eureka discovery service. It holds details information of all registered services becuase fron-end communicates to back-end through gateway service. 
# Gateway Service
Gateway service should be register with eureka which is responsible to establish communicaiton between front-end and back-end. Gateway holds respective api pattern information and routes fron-end request means incoming api request that should match with api pattern defined in gateway and forward that request to back-end after getting details about the respective service from eureka and gateway also acts as load balancer. 
# Spring Config service
Config service also should register with eureka and it holds a git repo where has centralize YAML content based on profile. These YAML files are configured with DB information, gateway information and eureka instance information and others authentication information. Every back-end has a bootstrap YAML file is for conecting to config server to load the respective YAML file's content. 

# MinIO
MinIO is for object storage like AWS S3 bucket and deploy as deployment in kubernetes cluster which is used for the file storage server. MinIO volume is NFS share and file server storage container is using that volume.  

# Logging and monitoring
ELK Stack is used to get container logs and visualize with kibana. Here, filebeat is used as a log shipper and forwording log data to logstash. Elasticsearch is deployed as a DB where index is created. Kibana is used to visualize the index data. 

# Configmap and Secret
I create configmap and secret kubernetes objects for application. Secret is used for sensitive data and configmap is used for other configuration data. 

# Justification (On-prem|public cloud|hybrid)
The software application which has requirements client request may increase day-by-day and in that case scalable and distributed system is required. Public cloud has scope to increase the resources as per need like autoscalling policy. We also concern about data security and durability. If we have requirements such a that we need archive data for long period of time then in that case we can use public cloud. Also application nature is like that when increasing trrafic need more resources to provision and when traffic goes down then decrease the reousrces in that case public cloud is the best option. If there has requirements that meets for the on-prem or hybrid we can choose it. Actually based on requirements we can choose the option. 

# Design for described microservice deployed in K8s cluster
All services are deployed with jenkins CI/CD pipeline. 

Note: You have a better look clicking the image. 



![microserce-architecture](https://user-images.githubusercontent.com/25055579/182891218-3af9de88-4f23-428d-b865-7f2631b21d71.png)
