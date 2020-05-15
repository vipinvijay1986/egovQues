# egovQuest

**Git** 

* Do you have a Git account?
>  Yes we have account
* Do you know how to clone a repository, pull updates, push updates? Do you know how to give a pull request and merge the pull request?

> Answer : Using Github desktop application we can do this. Apart from this we can use git shall command for the same: 

  - git clone 
  - git push
  - git clean 
  - git commit 
  - git pull
  - git add 


**Microservice Architecture** 

* Do you know when to create a new service?

> In mircroservice architecture a service is single unit of operation which is loosely coupled in other service. So for example if in our requirement   wanter tanker booking related service can be taken as new service.
In existing DIGIT structure logging / persisting  are taken up a microservice. 

* How to access other services?

> Using rest api calls RestTemplate communication is done between service. For a scalable solution again many approaches are taken up like naming service( Eureka) and load balancer, Feign client, Ribbon. 



**ReactJS** 

* How to create react app ?

> using npx create-react-app  project_name
Here create-react-app is a tool which installs all the dependencies needed to build react application

* How to create a Statefull and Stateless Component?


 Stateful component are created using extending Component class  
 
```
class StatefulComponent extends React.Component{
constructor(props){
super(props);
this.state={
status:true
}
}
render(){
return({this.state.status)
}
}

```

Stateless component/Functional component  are like a function,it doesnot have state and it plays with whatever it receives as a props

```
const StatelessComponent =(props)=>{
return(

)
}
```

* How to use HOC as a wrapper?

``` 
const NewComponent = (BaseComponent) => {
  // ... create new component from old one and update
  return UpdatedComponent
} 
```

* Validations at form level using React.js and Redux

Validation done by dipatching redux action such as setValidity,setErrors, and provide constrains for which validation need to be done.
   actions.setValidity(model,validity)/actions.setErrors(model,errors)

**Postgres**

* How to create database and set up privileges?

> Using pgAdmin also we can set it up. For flyway db it can be done in following way. 

```
CREATE DATABASE dataase_name;
Create User user_name;
GRANT SELECT, UPDATE, INSERT ON table_name TO user_name;
```


* How to add index on table?

`CREATE INDEX ON table_name (column_names) ;`



* How to use aggregation functions in psql?
AVG(),COUNT(),MAX(),MIN(),SUM() are some of the aggregate functions

`SELECT count(*) FROM sometable;`


**Postman** 


* SetupCall a REST API from Postman with proper payload and show the response.


```

{
	"info": {
		"_postman_id": "d9597f96-3b0e-4dc9-99dd-d5ad113386de",
		"name": "Quset",
		"schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
	},
	"item": [
		{
			"name": "localhost:8081/kafkaProducer",
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\"studentId\" :\"1\",\r\n \"firstName\" : \"vipin\",\r\n \"lastName\" :\"vijay\",\r\n \"age\" :\"28\"}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "localhost:8081/kafkaProducer",
					"host": [
						"localhost"
					],
					"port": "8081",
					"path": [
						"kafkaProducer"
					]
				}
			},
			"response": []
		}
	],
	"protocolProfileBehavior": {}
}
```

* Setup any service locally(MDMS or user service has least dependencies) and check the API’s using postman
> Not able to make setup locally


**REST APIs** 

* What are the principles to be followed when making a REST API?

  1. Uniform interface :  Uniformity should be maintained across service calls to improve readability
 
  2. Client–server : This improves portabality of user interfaces across multiple platforms and improves scalabality by simplifing server components
 
  3. Stateless : The request form client to server must contain all the necessary information for the execution of the request and should not rely on any stored info on the server.
 
  4. Cacheable : Any responce tagged as cacheable from the server can be re-used by the client for equivalent request.
 
  5. Layered system : REST allows you to use a layered system architecture where you deploy the APIs on server A, and store data on server B and authenticate requests in Server C

  6. Code on demand (optional) : Code-On-Demand means that a server can extend the functionality of a client on runtime, by sending code to it that it should execute (like Java Applets, or JavaScript) s


* When to use POST and GET?
  * GET operations is recomendded if the operation is considered as idempotent. 
  * If any change has to be made then POST request can be used.
  

* How to define the request and response parameters?
  - Using @RequestBody / @PathVariable  we can define request parameter 
  - Using ResponseEntity   or directly exposing the Class object we can send response

**Kafka**	 

* How to push messages on kafka topic?

  ` .\bin\windows\kafka-console-producer.bat --bootstrap-server localhost:9092 --topic myTopic-kafkasender(topic_name)`



* How does consumer group work?
 >In kafka a consumer label itself with group id and whenever topic receives any new message, then the message can be read by only one of consumer of the group. 

* What are partitions?
> In kafka a topic is divided into  number of partitions . Partitions allow you to parallelize a topic by splitting the data in a particular topic across multiple brokers — each partition can be placed on a separate machine to allow for multiple consumers to read from a topic in parallel. Consumers can also be parallelized so that multiple consumers can read from multiple partitions in a topic allowing for very high message processing throughput


**Docker and Kubernetes**
* How to edit deployment configuration?
> kubectl edit -is used to edit yaml file

* How to read logs?
> kubectl logs -f is used to check logs 

* How to go inside a kubernetes pod?
>kubectl exec ${POD_NAME} to go inside kubernetes pod

* How to create a docker file using a base image? 

```
FROM openjdk:8-jdk-alpine
ARG JAR_FILE=target/*.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar"]
```

* How to port-forward the pod to local port?
`kubectl port-forward TYPE/NAME [options] LOCAL_PORT:REMOTE_PORT`


**JSON**

* How to write filters to extract specific data using jsonPaths?
> As explained in https://github.com/json-path/JsonPath we can define $.store.book[*].author  filter to extract all the author of individual book in store. 

**YAML**
* How to read an API contract using swagger?

> Using swagger we can generate the documentation of API exposed in application. Swagger ui can be used to view the published api. 
Apart from this application_url/swagger-ui.html can be used to view API doc.

**Zuul**

* What does zuul do?
> Zuul works a gateway to application. So all of the request which hits to server can be pointed to zuul and zuul will redirect to particular service. 
Its can be used a intercepter of your application/ authorization of request /logging/ monitoring like this many functionality can be achieved using zuul


**MAVEN** 

* What is POM?

> POM define project information, its dependency and plugin used to build the project and entry point for application

* What is the purpose of maven clean install and how to do it?

> clean plugin clears the previously generated class and properties files 
and install will compile, test & package Java project and even copy your built .jar/.war file into your local Maven repository.

* What is the difference between version and SNAPSHOT?

> version is build release while SNAPSHOT is considered to be development version. 
In case of build version, the maven will not check remote repo in case if jar found in local setup.
But in case of SNAPSHOT even though jar exist in local setup it will try to pull from remote repo.  
Why it do so , because SNAPSHOT version are said to under development which are supposed to update frequently. 

**SpringBoot**

* How does Autowiring work in spring?

> @Autowired using this annotation , spring resolve and inject the bean into some target bean . 
For example We have defined KafkaSender a service component which we want to inject into another bean . 
So it can be defined using below 

```
@RestController
@RequestMapping("/kafkaProducer")
public class KafkaProducerController {

	@Autowired
	private KafkaSender sender;
}
```
 

* How to write a consumer/producer using spring kafka?

```
public class Producer {
    private static final String TOPIC = "topic_1";
    @Autowired
    private KafkaTemplate<String, String> kafkaTemplate;
    public void sendMessage(String message) {
        this.kafkaTemplate.send(TOPIC, message);
    }
}

public class Consumer {
    @KafkaListener(topics = "topic_1")
    public void consume(String message) throws IOException {
        logger.info(message));
    }
}

```
 

 

* How to make a API call to other service using restTemplate?

> RestTemplate API has functionality to call get/post/put/delete. 
To make any post call we need to create an RestTempalte object . Then to call post rest end point. We need to pass URI , request Object and Response object type. 
```
RestTemplate restTemplate = new RestTemplate();
Response result = restTemplate.postForObject( uri, requestObj, Response.class);
```
> For get call 
`restTemplate.getForObject(uri, responseType);`

* How to execute queries using jdbcTemplate?

> JdbcTemplate provide API to do CRUD operation and run named query on database 

`int result = jdbcTemplate.queryForObject("SELECT COUNT(*) FROM TABLE_NAME", Integer.class);`

It will return the result value 


**Elastic search**
* How to write basic queries to fetch data from elastic search index?

For entered record in the format :
{"index":{"_id":"1"}}
{"account_number":1,"balance":39225,"firstname":"Amber","lastname":"Duke","age":32,"gender":"M","address":"880 Holmes Lane","employer":"Pyrami","email":"amberduke@pyrami.com","city":"Brogan","state":"IL"}

Say for 1000 such records inserted and indexed:

Some of the basic queries:

1)Query all the bank records:

GET /bank/_search
{
  "query": { "match_all": {} },
  "sort": [
    { "account_number": "asc" }
  ]
}

2) Query certain number of records (Say for the purpose of pagination):

GET /bank/_search
{
  "query": { "match_all": {} },
  "sort": [
    { "account_number": "asc" }
  ],
  "from": 10,
  "size": 10
}

3) Query  based on a field:

GET /bank/_search
{
  "query": { "match": { "address": "mill lane" } }
}



**DIGIT Architecture**
* What comes as part of core service, business service and municipal services?
  * core service --> backbone service. Which run in background and does not have  any binding to module. Like logging , indexer and are used all digit deployments 
  * Business Service -->  Core modules for any digit platform deployments 
  * municipal services --> Modules which are optional for DIGIT deployment and represent a service for example Water connection, property tax

* How to calls APIs from one service in another service?  
  > digit platform use Kafka to communicate between services 


**DIGIT Core Services**
* Which are the core services in DIGIT framework?
> All infra service  are part of core service like Id Generation,Payment Gateway,AccessCtl,Indexer,Localization,Notification mail,Notification sms,otp,searcher,telemetry   https://github.com/egovernments/core-services

**DIGIT MDMS**

* How to read a master date from MDMS?
> MDMS configuration starts with tenants.json and how these things are persisted in database that flow is not clear

* How to add new data in an existing Master?
* Where is the MDMS data stored?
> Data are stored in json file and to add any data in existing category need to modify module specific json file. For localization data is persisted using python script


**DIGIT UI Framework** 
* How to add a new component in the framework?
* How to use an existing component?
* Link is Not accessible* 

