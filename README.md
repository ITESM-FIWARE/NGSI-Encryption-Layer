# NGSI Encryption Layer Application

This document describes the encryption service App developed at ITESM as a web application for encrypting, decrypting, and anonymizing [FIWARE data models](https://www.fiware.org/developers/data-models/).

[FIWARE](https://www.fiware.org/) is a curated framework of open source platform components to accelerate the development of Smart solutions. The [FIWARE platform](https://www.fiware.org/developers/catalogue/) provides a rather simple yet powerful set of APIs (Application Programming Interfaces) that ease the development of Smart Applications in multiple vertical sectors. 

The main and only mandatory component of any "Powered by FIWARE" platform or solution is the [FIWARE Orion Context Broker Generic Enabler](https://fiware-orion.readthedocs.io/en/master/), which brings a cornerstone function in any smart solution: the need to manage context information in a highly decentralized and large-scale manner, enabling to perform updates and bring access to context.

[FIWARE data models](https://www.fiware.org/developers/data-models/) have been harmonized to enable data portability for different applications including, but not limited, to Smart Cities. They are intended to be used together with [FIWARE NGSI version 2](https://www.fiware.org/2016/06/08/fiware-ngsi-version-2-release-candidate/).

The Web application allows the encryption, decryption, and anonimization of [FIWARE data models](https://www.fiware.org/developers/data-models/) that reside in a local JSON file.

## Prerequisites
The encryption service can be installed on any Operative System.

The following software must be previously installed in the server which will hold the encryption application.
1. [Docker](https://www.docker.com/get-started)
1. [Docker-compose](https://docs.docker.com/compose/install/)

The application requires an active Gmail account. The use of other email accounts will cause the malfunction of the service.

## Installation and Configuration
1. Clone or download this repository
1. Open a terminal in the location of the docker-compose.yml file
1. Start the docker compose with ```sudo docker-compose up``` or with ```sudo docker-compose up -d```. The first command shows the status of the container in the foreground while the second command put the process in the background
1. Check docker containers status: ```docker ps```
1. Two containers are required by the application, one for the ngsi_api and one for mongoDB. To verify that the containers are up and running: ```docker logs CONTAINER_ID``` 
1. If the container shows an error, restart the container: ```sudo docker-compose restart```
1. Stop the application: ```sudo docker-compose down```

## How to use
Access the service via the [NGSI Encryption Layer Application official website](http://148.241.3.246:3900/) or http://127.0.0.1:3800 / http://localhost:3800 if the application was installed locally

The correct functionality of the application is achieved by using Firefox, Chrome, and Opera web browsers. The application is not optimized for mobile devices.

## A walkthrough
### Sign up into the App
1. In the main page of the application, select the "Sign up" button at the right-top side of the web page
1. In the "Sign up" page, fill up the "First name", "Last name", "User name", "Email", and "Password" fields
1. Click the "Sign up" button at the left-bottom side of the web page
1. A message will be displayed asking to confirm the provided Gmail account. To perform this process, go to the Gmail account provided and click the confirmation URL contained into the email

### Login process
1. In the main page of the application, fill up the "Email" and "Password" fields with the corresponding credentials
1. Click the "Login" button at the left-bottom side of the web page
1. A web page with access to the user profile, as well as to the encryption, decryption, and anonymization algorithms is displayed

### Update the user's profile
1. Follow up the login process
1. In th main page, click the button with the username at the right-top side of the web page
1. Click the "My profile" button
1. A web page that encompasses the username, email, and profile picture is displayed
1. Click the "Edit profile" button at the left-bottom side of the web page
1. A page that enables to update the "First name", "Last name", "Username", and "Email" fields, as well as the profile picture, is displayed
1. Click the "Update" button to apply the modifications

### Encrypt a JSON file
1. Follow up the login process
1. In the main page, click the "Encrypt" button at the left-top side of the web page
1. Select an encryption algorithm
1. A web page with the selected algorithm is displayed
1. Click the "Load JSON" button to load a JSON file stored in the local computer
1. Select a JSON file that encompasses a [FIWARE data model](https://www.fiware.org/developers/data-models/) format
1. A confirmation message is displayed
1. Select the attributes that want to be encrypted at the left side of the web page
1. Click the "Encrypt" button at the left-bottom of the web page
1. The encrypted file is displayed on the right side of the web page
1. Click the "Download the encrypted JSON" button to locally save both the encrypted file and the Key file
1. Click the "View of the original JSON" to visualize the uploaded JSON file

### Decrypt a JSON file
1. Follow up the login process
1. In the main page, click the "Decrypt" button at the left-top side of the web page
1. Select an encryption algorithm
1. A web page with the selected algorithm is displayed
1. Click the "Load JSON" button to load a JSON file stored in the local computer
1. Select a JSON file that encompasses a [FIWARE data model](https://www.fiware.org/developers/data-models/) format and that was encrypted with the selected algorithm
1. A confirmation message is displayed
1. Click the "Load Key" button to load a file with the keys to decrypt the JSON file provided
1. Select a TXT file that comprises the keys to decrypt the selected JSON file
1. A confirmation message is displayed
1. Select the atributes that want to be decrypted at the left side of the web page
1. Click the "Decrypt" button at the left-bottom of the web page
1. The decrypted file is displayed on the right side of the web page
1. Click the "Download the decrypted JSON" button to locally save the decrypted file
1. Click the "View of the encrypted JSON" to visualize the uploaded encrypted JSON file

### Anonymize a JSON file
1. Follow up the login process
1. In the main page, click the "Anonymize" button at the left-top side of the web page
1. Select an anonymization algorithm
1. A web page with the selected algorithm is displayed
1. Click the "Load JSON" button to load a JSON file stored in the local computer
1. Select a JSON file that encompasses a [FIWARE data model](https://www.fiware.org/developers/data-models/) format
1. A confirmation message is displayed
1. Select the attributes that want to be anonymized at the left side of the web page
1. Click the "Anonymize" button at the left-bottom of the web page
1. The anonymized file is displayed on the right side of the web page
1. Click the "Download the anonymized JSON" button to locally save the anonymized file
1. Click the "View of the original JSON" to visualize the uploaded JSON file

### Visualize the App documentation
1. In the main page, click the "Documentation" button at the top side of the web page
1. The documentation is displayed at the [official web site of the application](https://github.com/ITESM-FIWARE/NGSI-Encryption-Layer-App/blob/master/README.md)

### Log out process
1. Follow up the login process
1. In the main page, click the button with the username at the right-top side of the web page
1. Click the "Log out" button
1. The "Login" window is displayed

