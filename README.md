# JSTO Secondary 

## JSTO Description

  Jsto Secondary is a backend API provider spring boot project for Gokurakujoto application.LBI Secondary is Japan’s first system that utilizes blockchain technology to buy and sell investment interests in financial products.

## JSTO Requirement

* Java（OpenJDK 15）
* MySQL(ver)
* Spring Boot
* MyBatis
* Gradle 
* Editors (VSCode, Intellij, eclipse, etc)
* Git

## Setup Configuration (for Intellij)

#### Git branch

Clone the repository
    
    git clone https://github.com/levias-org/jsto_secondary.git
    
Switch to the develop branch using the following command.

    checkout develop

Open the project with jsto_root folder in the IDEA Editor (IntelliJ)

#### Project Folder Structure

    jsto_secondary
       │        
       └─README.md 
       │        
       └─source
          │     
          └────── batch        
          │
          └──────gt-fw-common       
          │
          └──────gt-fw-db   
          │        
          └──────gt-fw-logic
          │ 
          └──────gt-fw-web
          │      
          └──────jsto-business-common
          │   
          └──────jsto-db-trade
          │  
          └──────jsto-docusign
          │  
          └──────jsto-io
          │   
          └──────jsto-logic
          │ 
          └──────jsto-logic-admin
          │   
          └──────jsto-logic-investor
          │ 
          └──────jsto-peer
          │ 
          └──────jsto-root
          │            │     
          │            └──────gradle
          │            │   
          │            └──────build.gradle
          │            │  
          │            + 
          │            + 
          │            +
          │            └──────settings.gradle
          │
          └──────jsto-trade-polling
                      

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

Build automation tool used is Gradle. Run the commands at gradle file.

Open the project at jsto-root folder where the gradle file is located.

    cd jsto_secondary/source/jsto-root

For adding permission

    chmod +x gradlew  
    
For execution
    
    ./gradlew build -x test 
    

