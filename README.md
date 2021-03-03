# FundamentosNube_LASR
Luis Alberto Sánchez Rios - 15198633

# Base de datos:
Carpeta BD - contiene la carpeta de configuración, de archivos y de logs, de igual manera
             se encuentra el docker-compose.yml dentro.
    Carpeta conf - Contiene el archivo my.cnf de MySQL.

    Carpeta files - Contiene los schemas y archivos de información de MySQL.

    Carpeta logs - Contiene los archivos de logs acerca de lo que se haya hecho o errores
               que hayan ocurrido.

    docker-compose.yml - 

            1. Se refiere a la versión del formato de nuestro archivo en este caso tenemos la versión 3.1, no todas las versiones son compatibles con todos los engines de docker.

            2. Salto de linea para indicar separación de conceptos.

            3. Marcar donde esta iniciando la declaración de nuestros servicios.

            4. Salto de linea para separar el inicio de nuestras definiciones. 

            5. Nombre que le asignamos a nuestra base de datos y abrimos espacio para definir sus componentes (Tiene un espacio de identación debido a que pertenece a la sección de services).

            6. Imagen para la base de datos que utilizara el contenedor, en este caso se esta utilizando mariadb (Tiene dos espacios de identación debido a que pertenece a la sección de mydatabase).

            7. Indica que el contenedor va a reiniciarse si se detiene, en caso de que se detenga de manera manual por el usuario, se reiniciara hasta que docker se vuelva a correr o se reinicie de manera manual (Tiene dos espacios de identación debido a que pertenece a la sección de mydatabase).

            8. Inicia la sección para definir variables de entorno (Tiene dos espacios de identación debido a que pertenece a la sección de mydatabase).

            9. Asignación de contraseña para el usuario root de la base de datos (Tiene tres espacios de identación debido a que pertenece a la sección de enviroment).

            10. Creación de un schema default (Tiene tres espacios de identación debido a que pertenece a la sección de enviroment). 

            11. Creación de un usuario para la conexión de MySQL (Tiene tres espacios de identación debido a que pertenece a la sección de enviroment).

            12. Asignación de contraseña para el usuario de la basa de datos (Tiene tres espacios de identación debido a que pertenece a la sección de enviroment).

            13. Inicia la sección para asignar el puerto que se va a utilizar (Tiene dos espacios de identación debido a que pertenece a la sección de mydatabase).

            14. En la izquiera se ubica el puerto del host y a la derecha se encuentra el puerto del contenedor (Tiene tres espacios de identación debido a que pertenece a la sección de ports).

            15. Inicia la sección en la cual se vincularán las carpetas de los volumenes (Tiene dos espacios de identación debido a que pertenece a la sección de mydatabase).

            16. Del lado izquierdo indicamos la carpeta local y del lado derecho de los 2 puntos indicamos la carpeta dentro del contenedor, en esta ocación queremos que nuestra carpeta files se sincronice con /var/lib/mysql/ dentro del contenedor (Tiene tres espacios de identación debido a que pertenece a la sección de volumes).

            17. En este caso queremos que la carpeta logs se sinconice con la carpeta /var/log/mysql/ dentro de nuestro contenedor (Tiene tres espacios de identación debido a que pertenece a la sección de volumes).
            
            18. En este ultimo caso, queremos que nuestra carpeta conf se sincronice con la carpeta /etc/mysql/conf.d/ dentro de nuestro contenedor (Tiene tres espacios de identación debido a que pertenece a la sección de volumes).

Descripción del contenedor: Contenedor con la imagen oficial de mariadb, es una variación de MySQL con pocos cambios a la estructura, sirve para no tener que instalar mariadb directamente de manera local, con el contenedor cada vez que queramos utilizar la base de datos, puede ser directamente desde la terminal que incluye, o puede se puede conectar directo a un gestor de base de datos.

# WEB
Carpeta web - contiene la carpeta con el codigo de la aplicación y el archivo docker-compose.yml.
    Carpeta appcode - contiene el codigo completo de nuestra aplicación.
    docker-compose.yml - 
    1. Se refiere a la versión del formato de nuestro archivo en este caso tenemos la versión 3.1, no todas las versiones son compatibles con todos los engines de docker.

    2. Salto de línea para indicar separación de conceptos.

    3. Marcar donde esta iniciando la declaración de nuestros servicios.

    4. Nombre que le asignamos a nuestra aplicación y abrimos espacio para definir sus componentes (Tiene un espacio de identación debido a que pertenece a la sección de services).

    5. Imagen para la aplicación web que utilizara el contenedor, en este caso se esta utilizando webdevops/php-apache:7.4 (Tiene dos espacios de identación debido a que pertenece a la sección de measurmentapp).

    6. Indica que el contenedor va a reiniciarse si se detiene, en caso de que se detenga de manera manual por el usuario, se reiniciara hasta que docker se vuelva a correr o se reinicie de manera manual (Tiene dos espacios de identación debido a que pertenece a la sección de measurmentapp).

    7. Inicia la sección para definir variables de entorno (Tiene dos espacios de identación debido a que pertenece a la sección de measurmentapp).

    8. Variable de entorno que originalmente su valor se encuentra en 0 (false), la colocamos en 1 (true) para que nos muestre los errores que haya en la aplicación web (Tiene tres espacios de identación debido a que pertenece a la sección de enviroment).

    9. Inicia la sección para asignar el puerto que se va a utilizar (Tiene dos espacios de identación debido a que pertenece a la sección de measurmentapp).

    10. En la izquiera se ubica el puerto del host y a la derecha se encuentra el puerto del contenedor (Tiene tres espacios de identación debido a que pertenece a la sección de ports).

    11. Inicia la sección en la cual se vincularán las carpetas de los volumenes (Tiene dos espacios de identación debido a que pertenece a la sección de measurmentapp).

    12. En este caso queremos que la carpeta appcode se sincronice con la carpeta /app dentro de nuestro contenedor, para que se pueda identificar cual es nuestro codigo fuente (Tiene tres espacios de identación debido a que pertenece a la sección de volumes).
    
Descripción del contenedor: Aplicación web programada en php, esta aplicación se utiliza para convertir medidas generales a sus equivalentes en otra medida, el contenedor utiliza la imagen webdevops/php-apache:7.4 y al correrlo se puede entrar de cualquier navegador.

