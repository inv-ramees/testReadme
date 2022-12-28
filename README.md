# JSTO Secondary 

## JSTO Description

 In the past, the procedure of transferring an asset was an analog procedure, such as certifying the possession of the asset and confirming the transferee, so it was natural to spend a long time and effort. LBI Secondary is the world’s first financial asset transfer system using block chain that enables digital management of information such as investment interest in financial products held by customers. LBI Secondary is Japan’s first system that utilizes blockchain technology to buy and sell investment interests in financial products. According to the transaction rules, it is possible to carry out bilateral transactions related to transfer using digital tokens. In order to use the application, the user must create an LBI account using the application. A valid LBI account is needed to view the secondary tokens available with the Levias Secondary application. Secondary tokens are the tokens, which the app users can buy and sell through the application. In order to buy or sell the secondary tokens through the Secondary app, the app user must register for a VW ID (Virtual Wall ID). As part of the security process, the user needs to have an account in two systems for managing tokens. Users can sell or purchase products only if they have a primary virtual wall ID account. When a user buys, sells or edits anything in user settings who launches the application using LBI Secondary credentials, primary login (Virtual wall) details will be asked as part of security. At that time users can do the remaining process only when they complete the primary (Virtual wall) login. 

## Features of JSTO
     * LBI Account Operation
     * Virtual Wall Account Operation
     * Information List
     * Pick up Token
     * Secondary Tokens
     * Trending Secondary Tokens
     * TODO List
     * Status List
     * Notification List
     * App Settings
     * Application for Transfer - Seller/Buyer
     * Process/Status Details - Seller/Buyer

## JSTO Backend

* Git

* Java（OpenJDK 15）

* Editors (VSCode, Intellij, eclipse, etc)

* (recommended) MySQL client tools

* Gradle

## Setup Instructions (for Intellij)

#### Git branch

Switch to the develop branch using the following command.

    checkout develop

Open the project in the IntelliJ IDEA Editor 

 #### MySQL
  
Use configurations in application-env_dev.properties file for setting up database.

     env.trade.url - Url for connecting to jsto_secondary.

     env.trade.user and env.trade.pass - username and password for jsto_secondary.

     env.primary.url - Url for connecting to jsto_primary.

     env.primary.user and env.primary.pass - username and password for jsto_primary.

Create MySQL structure of jsto_primary and jsto_secondary Database.

Add the configuration file inorder to access remote server for database.

     jsto-secondary-dev-gateway-innovature.pem - File for Development

     jsto-secondary-stg-innovature.pem - File for Staging

     Need to use the access file details for adding configuration file such as IP, username, password, passphrase, Endpoint, URL, user, password.

  #### Starting Spring Boot

     Open project from jsto_root module.
    
  #### S3 Amazon

    Amazon S3 used for storing files.
    
    env.jsto.s3.accesskey.id , env.jsto.s3.secret.id , env.jsto.s3.bucket.name -> fields in application-dev.properties for accessing S3.
    
  #### IDMS 
    
    idms.base.url and idms.service.token in application-env_dev.properties for accessing Idms user login
    
  #### BlockChain

    baseurl.blockchain.origin - Url for blockchain calling (application-common.properties)
    
  #### Docusign

    env.docusign.auth.base.url, env.docusign.auth.user.id, application.docusign.auth.user-password - Login credentials for docusign
    
    
  ####  Primary api call from secondary

    env.primary.base.url and env.api.key- url and key in application-env_dev.properties for calling primary database related api
    
## Build procedure 

    Build automation tool used is Gradle.

    chmod +x gradlew  - For adding permission.
    
    ./gradlew build -x test  - For execution.
    

