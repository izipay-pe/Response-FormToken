# Response-FormToken

Este es un ejemplo de como obtener un FormToken con NODE.JS para poder crear un [formulario INCRUSTADO](https://secure.micuentaweb.pe/doc/es-PE/rest/V4.0/javascript/) con la pasarela de pagos de Izipay. 


## Requisitos Previos

* Poder ingresar a su Back Office Vendedor. [Guía Aquí](https://github.com/izipay-pe/obtener-credenciales-de-conexion)

* Debe instalar la [versión de LTS node.js](https://nodejs.org/es/).

* Tener o crear una cuenta en [HEROKU](https://www.heroku.com/) (no tienen costo).

* OPCIONAL: tener una cuenta en [GitHub](https://github.com/).

## 1.- Crear el proyecto

  * Descargar el proyecto .zip haciendo click [Aquí](https://github.com/izipay-pe/Response-FormToken/archive/refs/heads/main.zip) o clonarlo desde Git.  
  ```sh
  git clone https://github.com/izipay-pe/Response-FormToken.git
  ``` 

  * Ingrese a la carpeta raíz del proyecto. A continuación, instale Express y Morgan para poder ejecutar y ver las consultas en el servidor.

  ```bash
  npm i express morgan
  ```
  
  * Para poder probar si el servidor está operativo, ejecute el comando.

  ```bash
  npm run start
  ```
`Tener en cuenta que se debe cumplir el paso 2 "Configurar la autentifiacion" antes de probar el servidor`

  puede ver el resultado en su servidor local: http://localhost:5000/CreatePayment


## 2.- Configurar la autentifiacion

  Este manual requiere que ingrese los valores de su cuenta Back Office Vendedor, en la siguiente ruta: `Configuraion -> Tienda -> Claves de API REST`

  En caso de no contar con una cuenta en Izipay puede utilizar las credenciales de prueba extraidas desde la pagina web "MI CUENTA WEB" en el siguiente [Enlace web](https://secure.micuentaweb.pe/doc/es-PE/rest/V4.0/api/get_my_keys.html)

  * En la raiz del proyecto entrar en la siguiente ruta: `src -> data -> keys_Audthentication` e ingresar sus credenciales de conexion API REST.

      ![crear app](/src/imagenes-readme/Keys.png)

## 3.- Subirlo al servidor web

  Para este ejemplo se utilizó el servidor gratuito de [Heroku](https://www.heroku.com/), ingrese a su cuenta de Heroku y siga los siguientes pasos.

  * paso 1: creamos nuestro app, donde se subirá el proyecto.
          ![crear app](/src/imagenes-readme/crear-app.png)

  * paso 2: ingresamos un nombre para nuestro aplicativo y elegimos el servidor que más se adecue a nuestro proyecto, finalizamos dándole click a botón `"Create app"`.
          ![nombre app](/src/imagenes-readme/nombre-app.png)

  * paso 3: ingresamos a `"Deploy"`.
        ![deploy app](/src/imagenes-readme/deploy.png)

  * paso 4: Seleccionamos el método con el que subiremos el proyecto, tenemos 2 opciones:  
        ![deploy app](/src/imagenes-readme/metodo-deploy.png)    

    - 4.1.- Heroku CLI: seguir los pasos que indica.
      ![deploy app](/src/imagenes-readme/heroku-cli.png) 

    - 4.2.- Repositorio GitHub: se sincroniza con tu repositorio, buscas el nombre de tu proyecto y le das conectar.
      ![deploy app](/src/imagenes-readme/repositorio-git.png) 

      - cuando encuentre tu repositorio verificas tu rama y finalizas dándole click en el botón `"Deploy Branch"`
        ![deploy app](/src/imagenes-readme/finalizar.png) 

  * paso 5: Para visualizar nuestro proyecto le damos click en `"View"`.
      ![deploy app](/src/imagenes-readme/ver-IPN.png)  

    - A la ruta que se muestra añadimos nuestra ruta endpoint `"/CreatePayment"`, debería quedar de la siguiente manera:

      ```bash
      https://izpay-prueba.herokuapp.com/CreatePayment
      ```

  
