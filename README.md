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
![01](https://user-images.githubusercontent.com/39604832/51506911-34488f00-1db4-11e9-96f6-0f9c7cd9476d.png)
1. Start the docker compose with ```sudo docker-compose up``` or with ```sudo docker-compose up -d```. The first command shows the status of the container in the foreground while the second command put the process in the background
![02](https://user-images.githubusercontent.com/39604832/51506913-34488f00-1db4-11e9-9266-a6b8a27a0c7d.png)
![03](https://user-images.githubusercontent.com/39604832/51506915-34e12580-1db4-11e9-9db1-5e9e3a1ab5f6.png)
1. Check docker containers status: ```docker ps```
![04](https://user-images.githubusercontent.com/39604832/51506917-34e12580-1db4-11e9-8d54-a8bb8156dfd5.png)
1. Two containers are required by the application, one for the ngsi_api and one for mongoDB. To verify that the containers are up and running: ```docker logs CONTAINER_ID```
![05](https://user-images.githubusercontent.com/39604832/51506919-34e12580-1db4-11e9-852d-0869e4c8fda6.png)
1. If the container shows an error, restart the container: ```sudo docker-compose restart```
![06](https://user-images.githubusercontent.com/39604832/51506921-34e12580-1db4-11e9-9576-deaa6d301f43.png)
![07](https://user-images.githubusercontent.com/39604832/51506923-3579bc00-1db4-11e9-9992-26e79d033b92.png)
1. Stop the application: ```sudo docker-compose down```
![08](https://user-images.githubusercontent.com/39604832/51506925-3579bc00-1db4-11e9-8cdf-c00f016afd16.png)

## How to use
Access the service via the [NGSI Encryption Layer Application official website](http://148.241.3.246:3900/) or http://127.0.0.1:3800 / http://localhost:3800 if the application was installed locally

The correct functionality of the application is achieved by using Firefox, Chrome, and Opera web browsers. The application is not optimized for mobile devices.

## A walkthrough
### Sign up into the App
1. In the main page of the application, select the "Sign up" button at the right-top side of the web page
![09](https://user-images.githubusercontent.com/39604832/51506927-3579bc00-1db4-11e9-8da1-46156dab2396.png)
![1](https://user-images.githubusercontent.com/39604832/51506912-34488f00-1db4-11e9-9e5e-1fac90211a4d.png)
1. In the "Sign up" page, fill up the "First name", "Last name", "User name", "Email", and "Password" fields
1. Click the "Sign up" button at the left-bottom side of the web page
![2](https://user-images.githubusercontent.com/39604832/51506914-34488f00-1db4-11e9-90c9-f8f0e393b414.png)
1. A message will be displayed asking to confirm the provided Gmail account. To perform this process, go to the Gmail account provided and click the confirmation URL contained into the email
![3](https://user-images.githubusercontent.com/39604832/51506916-34e12580-1db4-11e9-8ed7-43352aabfd66.png)
![4](https://user-images.githubusercontent.com/39604832/51506918-34e12580-1db4-11e9-874f-ad0dfe4dca48.png)

### Login process
1. In the main page of the application, fill up the "Email" and "Password" fields with the corresponding credentials
![09](https://user-images.githubusercontent.com/39604832/51506927-3579bc00-1db4-11e9-8da1-46156dab2396.png)
1. Click the "Login" button at the left-bottom side of the web page
![6](https://user-images.githubusercontent.com/39604832/51506922-3579bc00-1db4-11e9-906d-ca1542e84da3.png)
1. A web page with access to the user profile, as well as to the encryption, decryption, and anonymization algorithms is displayed
![7](https://user-images.githubusercontent.com/39604832/51506924-3579bc00-1db4-11e9-9410-4e4e3a8b7199.png)

### Update the user's profile
1. Follow up the [login process](https://github.com/ITESM-FIWARE/NGSI-Encryption-Layer-App#login-process)
1. In th main page, click the button with the username at the right-top side of the web page
![8](https://user-images.githubusercontent.com/39604832/51506926-3579bc00-1db4-11e9-9a83-e85e1dd2416b.png)
1. Click the "My profile" button
![9](https://user-images.githubusercontent.com/39604832/51506928-3579bc00-1db4-11e9-9bfa-1168338c3470.png)
1. A web page that encompasses the username, email, and profile picture is displayed
![10](https://user-images.githubusercontent.com/39604832/51506929-36125280-1db4-11e9-93e9-a83de649defc.png)
1. Click the "Edit profile" button at the left-bottom side of the web page
![11](https://user-images.githubusercontent.com/39604832/51506930-36125280-1db4-11e9-9354-bede36d2faed.png)
1. A page that enables to update the "First name", "Last name", "Username", and "Email" fields, as well as the profile picture, is displayed
![12](https://user-images.githubusercontent.com/39604832/51506932-36125280-1db4-11e9-8246-8edf94c06155.png)
1. Click the "Update" button to apply the modifications
![13](https://user-images.githubusercontent.com/39604832/51506933-36125280-1db4-11e9-8fba-dee71189e0b0.png)

### Encrypt a JSON file
1. Follow up the [login process](https://github.com/ITESM-FIWARE/NGSI-Encryption-Layer-App#login-process)
1. In the main page, click the "Encrypt" button at the left-top side of the web page
1. Select an encryption algorithm
![14](https://user-images.githubusercontent.com/39604832/51506935-36125280-1db4-11e9-880e-4282a91d81b5.png)
1. A web page with the selected algorithm is displayed
![15](https://user-images.githubusercontent.com/39604832/51506936-36125280-1db4-11e9-981e-6fc8d7d0ed30.png)
1. Click the "Load JSON" button to load a JSON file stored in the local computer
1. Select a JSON file that encompasses a [FIWARE data model](https://www.fiware.org/developers/data-models/) format
![16](https://user-images.githubusercontent.com/39604832/51506937-36125280-1db4-11e9-9989-1d44f8542c77.png)
1. A confirmation message is displayed
![17](https://user-images.githubusercontent.com/39604832/51506938-36aae900-1db4-11e9-96d4-7191842b87f3.png)
1. Select the attributes that want to be encrypted at the left side of the web page
![18](https://user-images.githubusercontent.com/39604832/51506939-36aae900-1db4-11e9-97e7-16c83b7b2322.png)
1. Click the "Encrypt" button at the left-bottom of the web page
![19](https://user-images.githubusercontent.com/39604832/51506940-36aae900-1db4-11e9-8172-4076308ca23a.png)
1. The encrypted file is displayed on the right side of the web page
![20](https://user-images.githubusercontent.com/39604832/51506941-36aae900-1db4-11e9-9394-e29bf5ad0c7c.png)
1. Click the "Download the encrypted JSON" button to locally save both the encrypted file and the Key file
![21](https://user-images.githubusercontent.com/39604832/51506942-36aae900-1db4-11e9-8381-95fb7a4574b5.png)
1. Click the "View of the original JSON" to visualize the uploaded JSON file
![22](https://user-images.githubusercontent.com/39604832/51507531-00bb3400-1db7-11e9-9dd7-33f7ef6c1e25.png)

### Decrypt a JSON file
1. Follow up the [login process](https://github.com/ITESM-FIWARE/NGSI-Encryption-Layer-App#login-process)
1. In the main page, click the "Decrypt" button at the left-top side of the web page
1. Select a decryption algorithm
![23](https://user-images.githubusercontent.com/39604832/51506943-36aae900-1db4-11e9-9083-9be64769491d.png)
1. A web page with the selected algorithm is displayed
![24](https://user-images.githubusercontent.com/39604832/51506944-36aae900-1db4-11e9-89f0-29c2782a31e7.png)
1. Click the "Load JSON" button to load a JSON file stored in the local computer
1. Select a JSON file that encompasses a [FIWARE data model](https://www.fiware.org/developers/data-models/) format and that was encrypted with the selected algorithm
![25](https://user-images.githubusercontent.com/39604832/51506945-37437f80-1db4-11e9-93ad-86328c222981.png)
1. A confirmation message is displayed
![26](https://user-images.githubusercontent.com/39604832/51506946-37437f80-1db4-11e9-967d-550901d34eda.png)
1. Click the "Load Key" button to load a file with the keys to decrypt the JSON file provided
1. Select a TXT file that comprises the keys to decrypt the selected JSON file
![27](https://user-images.githubusercontent.com/39604832/51506947-37437f80-1db4-11e9-9988-313bd9422393.png)
1. A confirmation message is displayed
![28](https://user-images.githubusercontent.com/39604832/51506948-37437f80-1db4-11e9-9d48-932dcbc48ff9.png)
1. Select the atributes that want to be decrypted at the left side of the web page
![30](https://user-images.githubusercontent.com/39604832/51507726-d61dab00-1db7-11e9-819a-83bc91182b89.png)
1. Click the "Decrypt" button at the left-bottom of the web page
![31](https://user-images.githubusercontent.com/39604832/51507761-006f6880-1db8-11e9-8e6d-ea08da23240c.png)
1. The decrypted file is displayed on the right side of the web page
1. Click the "Download the decrypted JSON" button to locally save the decrypted file
![33](https://user-images.githubusercontent.com/39604832/51506952-37dc1600-1db4-11e9-82bd-f9cfca08c8a9.png)
1. Click the "View of the encrypted JSON" to visualize the uploaded encrypted JSON file
![34](https://user-images.githubusercontent.com/39604832/51506953-37dc1600-1db4-11e9-9b7d-2aad5d8c576b.png)

### Anonymize a JSON file
1. Follow up the [login process](https://github.com/ITESM-FIWARE/NGSI-Encryption-Layer-App#login-process)
1. In the main page, click the "Anonymize" button at the left-top side of the web page
1. Select an anonymization algorithm
![35](https://user-images.githubusercontent.com/39604832/51506954-37dc1600-1db4-11e9-9fe8-0c71096be615.png)
1. A web page with the selected algorithm is displayed
![36](https://user-images.githubusercontent.com/39604832/51506955-37dc1600-1db4-11e9-9acd-69b9a7a24d6d.png)
1. Click the "Load JSON" button to load a JSON file stored in the local computer
1. Select a JSON file that encompasses a [FIWARE data model](https://www.fiware.org/developers/data-models/) format
![37](https://user-images.githubusercontent.com/39604832/51506956-37dc1600-1db4-11e9-88e3-84acca25a157.png)
1. A confirmation message is displayed
![38](https://user-images.githubusercontent.com/39604832/51506957-37dc1600-1db4-11e9-9187-d123bab855f4.png)
1. Select the attributes that want to be anonymized at the left side of the web page
![39](https://user-images.githubusercontent.com/39604832/51506958-3874ac80-1db4-11e9-8549-a7b2b01f4ac1.png)
1. Click the "Anonymize" button at the left-bottom of the web page
![40](https://user-images.githubusercontent.com/39604832/51506959-3874ac80-1db4-11e9-81a9-f20d02a6004b.png)
1. The anonymized file is displayed on the right side of the web page
![41](https://user-images.githubusercontent.com/39604832/51506960-3874ac80-1db4-11e9-8ba4-4d7c430fdefc.png)
1. Click the "Download the anonymized JSON" button to locally save the anonymized file
![42](https://user-images.githubusercontent.com/39604832/51506961-3874ac80-1db4-11e9-8cc0-0b3fb871f8dd.png)
1. Click the "View of the original JSON" to visualize the uploaded JSON file
![43](https://user-images.githubusercontent.com/39604832/51507870-91deda80-1db8-11e9-8a5b-26946b6d3b39.png)

### Visualize the App documentation
1. In the main page, click the "Documentation" button at the top side of the web page
![44](https://user-images.githubusercontent.com/39604832/51506962-3874ac80-1db4-11e9-8f59-18f179884da0.png)
1. The documentation is displayed at the [official web site of the application](https://github.com/ITESM-FIWARE/NGSI-Encryption-Layer-App/blob/master/README.md)
![45](https://user-images.githubusercontent.com/39604832/51506963-3874ac80-1db4-11e9-827c-ce0142d2c7be.png)

### Log out process
1. Follow up the [login process](https://github.com/ITESM-FIWARE/NGSI-Encryption-Layer-App#login-process)
1. In the main page, click the button with the username at the right-top side of the web page
1. Click the "Log out" button
![46](https://user-images.githubusercontent.com/39604832/51506964-3874ac80-1db4-11e9-82ef-a7ebd5dda665.png)
1. The "Login" window is displayed
![47](https://user-images.githubusercontent.com/39604832/51506965-390d4300-1db4-11e9-8da1-2cc0325de1cf.png)

