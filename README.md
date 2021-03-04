# FundamentosNube_LASR
Luis Alberto Sánchez Rios - 15198633

# Database:
Folder BD - contains the folders conf for configuration, files and logs, it also contains the docker-compose.yml file.
    Folder conf - contains the file my.cnf de MySQL.

    Folder files - contains the data base schemas and MySQL info files.

    Folder logs - contains the log files about what has happened inside the database, from queries to errors that occured.

    docker-compose.yml - 

            1. Refers to the docker-compose format version, in this case we are using the version 3.1, not all versions of docker-compose are compatible with every docker engine version.

            2. Line skip just for separating.

            3. Here begins the declaration of our services inside the container.

            4. Line skip just for separating. 

            5. Name given to our database and we open the space to define its components (One identation space due to it belonging to the services section).

            6. Image for the database we will be using in the conteiner, in this case we are using mariadb (Two identation spaces due to it belonging to the mydatabase section).

            7. Indicates that the container will restar in case of failing or restarting docker, if the user turns it off it won´t restart unless the user turns it back on or docker restarts (Two identation spaces due to it belonging to the mydatabase section).

            8. Here begins the declaration for our environment variables (Two identation spaces due to it belonging to the mydatabase section).

            9. Defining the password for the user root in our database (Three identation spaces due to it belonging to the environment section).

            10. Creation of a default schema (Three identation spaces due to it belonging to the environment section). 

            11. Creation of a user for our MySQL conection (Three identation spaces due to it belonging to the environment section).

            12. Defining the passiword for the recently created user (Three identation spaces due to it belonging to the environment section).

            13. Here begins the decalration of our container´s port (Two identation spaces due to it belonging to the mydatabase section).

            14. In the left side we have the host´s port, and on the right side we have our containers port (Three identation spaces due to it belonging to the ports section).

            15. Here begins the section in which we link the folders in our host with the ones in our container, which is called volumes (Two identation spaces due to it belonging to the mydatabase section).

            16. In the left side we define the local folder and from the colon to the right we have the folder inside our container. In this case we are synching our files folder with the folder /var/lib/mysql/ inside our container (Three identation spaces due to it belonging to the volumes section).

            17. In this case we want to sync the folder logs with the folder /var/log/mysql/ inside our container (Three identation spaces due to it belonging to the volumes section).
            
            18. In this las case, we want to sync our conf folder with the folder  /etc/mysql/conf.d/ inside our container (Three identation spaces due to it belonging to the volumes section).

Container´s description: Container with the official image of mariadb, this container allows us to use mariadb without having to directly install it in our computer. Each time we want to use the database, all we have to do is run docker and the container, and now we can connect to it directly from our database manager.

# WEB
Folder web - contains the folder with our main code and the docker-compose.yml file.
    Folder appcode - contains the main code from our web app.

    docker-compose.yml - 

    1. Refers to the docker-compose format version, in this case we are using the version 3.1, not all versions of docker-compose are compatible with every docker engine version.

    2. Line skip just for separating.

    3. Here begins the declaration of our services inside the container.

    4. Name given to our WEB app and we open the space to define its components (One identation space due to it belonging to the services section).

    5. Image for the WEB app we will be using in the conteiner, in this case we are using webdevops/php-apache:7.4 (Two identation spaces due to it belonging to the measurmetapp section).

    6. Indicates that the container will restar in case of failing or restarting docker, if the user turns it off it won´t restart unless the user turns it back on or docker restarts (Two identation spaces due to it belonging to the measurmetapp section.

    7. Here begins the declaration for our environment variables (Two identation spaces due to it belonging to the measurmentapp section).

    8. Environment variable with the original value of 0 (false), we are using the value of 1 (true) for it to show us the errors that occure in our WEB app (Three identation spaces due to it belonging to the environment section).

    9. Here begins the decalration of our container´s port (Two identation spaces due to it belonging to the measurmentapp section).

    10. In the left side we have the host´s port, and on the right side we have our containers port (Three identation spaces due to it belonging to the ports section).

    11. Here begins the section in which we link the folders in our host with the ones in our container, which is called volumes (Two identation spaces due to it belonging to the measurmentapp section).

    12. In this case we want our appcode folder to be in sync with the /app folder inside our container so that it can identify where ir our app´s main code (Three identation spaces due to it belonging to the volumes section).
    
Container´s description: WEB app programmed in php, this app is used to convert general measures to their equivalent in another measurment unit. This container contains the image webdevops/php-apache:7.4, and while running it we can acces to the web app from any web browser.

