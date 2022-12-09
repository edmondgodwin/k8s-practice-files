**TIPS FOR DEPLOYING AN APPLICATION**
-------------------------------------


1. Understand and test the app logic. Understand and test how the app works so you can know if the app works as    expected when deployed in kubernetes.

2. Understand the app architecture. 

3. Deploy application on Docker Host. This includes:
	Writing Dockerfile for each microservices to generate docker images and bring up the entire application 	containers
4. Dockerfile Requirements are the information about each microservices, like:
	1. Environment variables
	2. Configs
	3. Port Information
	4. Command to build and start application each microservice
	5. Healthcheck part information
	6. Any other settings

5.  



> [NB] - Every organisation has a standard dockerfile that is adopted by every devops engineer to build images and  microservices.

````
ASSIGNMENT
Write standard dockerfile for every language and store in github
````