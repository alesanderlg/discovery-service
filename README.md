## **Building your Spring Eureka Service**

### **Properties to tet up the Eureka configuration**

```
spring:
  application:
    name: discovery-service # name of the service that will be registered with Eureka
```

```
eureka:
  instance:
    hostname: localhost 
  client:
    registerWithEureka: false # register the service with eureka
    fetchRegistry: false # cache the registry information locally
    serviceUrl: 
      defaultZone: http://${eureka.instance.hostname}:${server.port}/eureka/  # location of eureka service
  server: 
    wait-time-in-ms-when-sync-empty: 0 # initial time to wait before server takes requests
```

### **Annotating the bootstrap class to enable the Eureka Server**

This annotation `@EnableEurekaServer` tells the Spring Boot to enable the Eureka Server

```
@SpringBootApplication
@EnableEurekaServer
public class DiscoveryServiceApplication {
	public static void main(String[] args) {
		SpringApplication.run(DiscoveryServiceApplication.class, args);
	}
}
```
