## Business Data Model API

- Find by attribute
http://localhost:8080/bonita/API/bdm/businessData/com.company.model.Student?q=findByBatch&p=0&c=3&f=Batch=E14

- Find by perrsistence Id
http://localhost:8080/bonita/API/bdm/businessData/com.company.model.Student/findByIds?ids=1,2,3,4

- call an attribute of JSON object
productDetail--> {product: tea, country: Sri Lanka} attribute of productDetail object can be called in UI as productDetail.country
productDetail--> [{product: tea, country: Sri Lanka}] attribute of productDetail object can be called in UI as productDetail[0].country

- h2 database update
create a text file and export the table as a CSV format
	
	for example:
	CREATE TABLE UPDATE AS 
	select * from csvread('D:/Bonita/Course.txt',null,'charset=UTF-8 fieldSeparator=|')

	INSERT INTO COURSEMODULE
	SELECT * FROM UPDATE 

	DROP TABLE IF EXISTS UPDATE

- Retrieve lazy reference

	retrieve lazy references of a business data field using lazyRef filter in an External API variable:
API URL: {{myBusinessData | lazyRef : 'relationName'}} where myBusinessData is an External API variable retrieving a business data from the context like in the above example and relationName the name of the lazy relation field to retrieve.

## bonita Platform(Process Deployment)
	As in the documentation, follow the instruction as below to install the tomcat bundle,
1. Create the database
2. Customize it so it works with Bonita
3. Modify the database.properties file: Set the right db vendor and change connection url, user credentials, database name and so on.

	next run the tomcat server which automatically directs to the bonita portal and do the procedure as in
link https://www.youtube.com/watch?v=YekoVEj1NDE. Don't forget to create administrative user wwhen we are login as a technical user.

## Some good readings
https://www.evoketechnologies.com/blog/custom-page-integration-bonita-bpm/
https://bonitatraining.com/bonita-bpm-7-developer-friendly-engaging-applications/