Sample code for Azure Durable Functions


Pre Requisites :-

--JDK 8+
--Maven 3.0 +
**--Azure Function Tools v4.0.4915**
--Azure Toolkit for IDE
-- Function App should be already created in portal

Azure Function Tools must aleast equal or above the version mentioned. My local version -- 4.0.5198

Earlier it was 4.0.3 and faced lot of weird issues and lastly upgraded it.

1) Durable function can be created by various ways - https://learn.microsoft.com/en-us/azure/azure-functions/durable/quickstart-java?pivots=create-option-vscode&tabs=bash

a) Using IDE
b) Using Maven command
c) Manually creating a quick start maven project and then creating all required files like few updates to pom.xml, creation of local.setting.json, host.json etc

There can be more ways. **I preferred using IDE or Manually.** Using maven I faced some trouble


2)Let's assume you have a sample code like this repo and to test in local follow below steps

Provide AzureWebJobsStorage value in local.setting.json

**mvn clean package or mvn clean install**

**mvn azure-functions:run**

3) if it runs successfully, we can see a localhost url in termial along with Host lock lease acquired logger

4)Go to postman or browser and do a get/post request to the same localhost url and hopefully we get a json response back with id, purgeHistoryDeleteUri, statusQueryGetUri and few other fields.


Go to the statusQueryGetUri value which is a url and perform a get request. The runtime status should be completed without any errors

5) If testing is successful, we can right click on project structure and go to Azure---> Deploy to Azure Functions and wait for deployment to complete.

6) After deployment, we can see 3 functions in portal and we can test as well.



