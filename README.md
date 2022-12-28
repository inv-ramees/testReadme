# JSTO Secondary 

## JSTO Description

 LBI Secondary is Japan’s first system that utilizes blockchain technology to buy and sell investment interests in financial products. According to the transaction rules, it is possible to carry out bilateral transactions related to transfer using digital tokens. In order to use the application, the user must create an LBI account using the application. A valid LBI account is needed to view the secondary tokens available with the Levias Secondary application. Secondary tokens are the tokens, which the app users can buy and sell through the application.

## JSTO Requirement

* Java（OpenJDK 15）
* Spring Boot
* MyBatis 
* Editors (VSCode, Intellij, eclipse, etc)
* Gradle
* MySQL client tools
* Git

## Setup Configuration (for Intellij)

#### Git branch

Switch to the develop branch using the following command.

    checkout develop

Open the project in the IntelliJ IDEA Editor 

 #### MySQL Configuration
  
Use configurations in application-env_dev.properties file for setting up database.

Credentials to Connect with Primary Database in application-primary_db.properties

    spring.primary.driver-class-name=com.mysql.cj.jdbc.Driver
    spring.primary.url=${env.primary.url}
    spring.primary.username=${env.primary.user}
    spring.primary.password=${env.primary.pass}
    
Credentials to Connect with Secondary Database in application-trade_db.properties
    
    spring.trade.driver-class-name=com.mysql.cj.jdbc.Driver
    spring.trade.url=${env.trade.url}
    spring.trade.username=${env.trade.user}
    spring.trade.password=${env.trade.pass}

Create MySQL structure of jsto_primary and jsto_secondary Database.Add the configuration file inorder to access remote server for database. Need to use the access file details for adding configuration file such as IP, username, password, passphrase, Endpoint, URL, user, password.

  #### Starting Spring Boot

     Open project from the module jsto_root.
    
  #### S3 Amazon

Credentials for Accessing S3
    
    jsto.s3.bucket.name = sample_name
        
  #### IDMS 

Url for Accessing IDMS in application-common.properties
    
    jsto.idms.url=${jsto.idms.base_url}/api/v${jsto.idms.version} 
    
  #### BlockChain

 Url for blockchain call in application-common.properties

    baseurl.blockchain.origin=${baseurl.blockchain.value}
    
  #### Docusign

Login credentials for docusign in application-common.properties

    application.docusign.auth.base-url=${env.docusign.auth.base.url}
    application.docusign.auth.user-id=${env.docusign.auth.user.id}
    application.docusign.auth.user-password=${env.docusign.auth.user.password}
    
  ####  Primary api call from secondary
  
For Calling Primary Database Related API's in application-common.properties

    primary.base.url = ${env.primary.base.url}
    api.key = ${env.api.key}key 
    
## Build procedure 

Build automation tool used is Gradle.

Run the commands in which gradle file is located

For adding permission

    chmod +x gradlew  
    
For execution
    
    ./gradlew build -x test 
    

