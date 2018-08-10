# Node.js

1. [Fundamentos](#fundamentos)
1. [NPM](#npm)
1. [Express.js](#expressjs)
1. [Socket.IO](#socketio)
1. [MongoDB](#mongodb)
1. [API REST](#api-rest)

## Fundamentos

### [¿Qué es Node.js?](https://nodejs.org/)

> Node.js® es un entorno de ejecución para JavaScript construido con el motor de JavaScript V8 de Chrome. Node.js usa un modelo de operaciones E/S sin bloqueo y orientado a eventos, que lo hace liviano y eficiente. El ecosistema de paquetes de Node.js, npm, es el ecosistema mas grande de librerías de código abierto en el mundo.

* [Node.js en español](https://nodejs.org/es/)
* Instalación
  * Tipos de Versiones
    * **LTS** - *Long Term Support*
    * **Current**
  * Tipos de Instalación
    * [Stand Alone](https://nodejs.org/en/download/)
    * Node Version Manager
      * [NVM para Linux / Mac](https://github.com/creationix/nvm)
      * [NVM para Windows](https://github.com/coreybutler/nvm-windows)

### Ciclo de vida de un proceso

1. Pila de Procesos (Requests & Response)
1. Pila de Subprocesos (Async Requests)
1. Cola de Callbacks (Async Responses)

![Event Loop](https://raw.githubusercontent.com/jonmircha/markdowns/master/assets/event-loop.png)

### Blocking vs Non Blocking I/O

Comensales VS Meseros

![Comensales VS Meseros](https://raw.githubusercontent.com/jonmircha/markdowns/master/assets/comensales.jpg)

### Asincronía

Establece la capacidad que tienen las operaciones del flujo de un programa para devolver el control de la ejecución al mismo (programa) antes de que hayan terminado sus procesos, mientras siguen operando en segundo plano (procesos u operaciones no bloqueantes).

Esto agiliza el proceso de ejecución y permite aumentar la escalabilidad, pero complica el razonamiento sobre el programa.

![Asincronía](https://raw.githubusercontent.com/jonmircha/markdowns/master/assets/asincronia.png)

Mecanismos asíncronos en JavaScript:

* [Callbacks](http://callbackhell.com/)
* [Promises](https://www.promisejs.org/)
* [Async Functions](https://tc39.github.io/ecmascript-asyncawait/)

[🔙 Regresar](#nodejs)

## NPM

***[Node Package Manager](https://www.npmjs.com/)***

Es el gestor de paquetes de Node.js... y de todo JavaScript.

### Paquetes en Node:

* Nativos ( _[API Core](https://nodejs.org/api/)_  )
* Externos ( _[NPM Docs](https://docs.npmjs.com/)_ )

### Proyectos en Node:

```
$ > npm init //Con asistente

$ > npm init -y //Sin asistente
```

### _**[package.json](https://docs.npmjs.com/files/package.json)**_

Es el archivo de configuración de un proyecto de node.js.

### Tipos de instalación

* Dependencia de proyecto
* Dependencia de desarrollo
* Dependencia global

Instalando un paquete:

```
$ > npm install [package]

$ > npm install [package]@3.4.12 // Versión específica

$ > npm i [package] //shortcut
```

Como dependencia de proyecto:

```
$ > npm install [package] //sin flag

$ > npm install [package] --save //con flag

$ > npm install [package] -S //shortcut
```

Como dependencia de desarrollo:

```
$ > npm install [package] --save-dev //con flag

$ > npm install [package] -D //shortcut
```

Como dependencia global:

```
$ > npm install [package] --global //con flag

$ > npm install [package] -g //shortcut
```

Instalando múltiples paquetes de forma simultanea:

```
$ > npm install [package1] [package2] [package3] --flag
```

Desinstalando paquetes:

```
$ > npm uninstall [package]

$ > npm uninstall [package]@3.4.12 // Versión específica

$ > npm un [package] //shortcut

$ > npm un [package] --save

$ > npm un [package] --save-dev

$ > npm un [package] --global
```

Cuando un proyecto tiene registradas sus dependencias en el _**package.json**_ se pueden instalar simplemente con el comando:

```
$ > npm install
```

### Paquetes y Módulos

Podemos importar y exportar módulos en Node de 2 formas:

1. CommonJS ( estándar y nativa )
1. Módulos +ES6 ( se requiere usar Babel )

CommonJS:

```javascript
//exportar
module.exports = myModule

//importar
const myModule = require('./myModule')
```

Módulos +ES6:

```javascript
//exportar
export const myModule

//importar
import myModule from './myModule'
```

### Scripts NPM

Podemos ejecutar comandos desde la cli mediante la definición de scripts en el archivo _package.json_.

```
"scripts": {
  "sass": "node-sass -o ./dist/ ./src/",
  "dev-server": "browser-sync start --server --files public",
  "start": "nodemon app.js"
 }

$ > npm run sass
$ > npm run dev-server
$ > npm start
```

_**npm start**_ no necesita especificar la palabra '_run_' para ejecutarse. Generalmente es el script estandar para iniciar un proyecto.

[🔙 Regresar](#nodejs)

## [Express.js](http://expressjs.com/)

### ¿Qué es?

> Express es una infraestructura de aplicaciones web Node.js mínima y flexible que proporciona un conjunto sólido de características para las aplicaciones web y móviles.<br><br>
> Con miles de métodos de programa de utilidad HTTP y middleware a su disposición, la creación de una API sólida es rápida y sencilla.<br><br>
>Express proporciona una delgada capa de características de aplicación web básicas, que no ocultan las características de Node.js que tanto ama y conoce.

* [Express.js en español](http://expressjs.com/es)
* [Documentación](http://expressjs.com/en/4x/api.html)
* Express API:
  * [Express](http://expressjs.com/4x/api.html#express)
  * [Application](http://expressjs.com/4x/api.html#app)
  * [Require](http://expressjs.com/4x/api.html#req)
  * [Response](http://expressjs.com/4x/api.html#res)
  * [Router](http://expressjs.com/4x/api.html#router)
* [Generador de Express](http://expressjs.com/en/starter/generator.html)

#### Características

* Estrictamente web (microframework).
* Sencillo, flexible y minimalista.
* Muy popular.
* Se adapta muy bien a la filosofía de Node.
* Similar a Sinatra, Sylex, Flask, Spark, etc.

#### Útil para:

* Rutas.
* Parámetros.
* Formularios.
* Subida de ficheros.
* Cookies.
* Sesiones.
* Templates.

#### NO es útil para:

* Base de datos / ORM.
* Autenticación de usuarios.
* Seguridad.
* Migraciones.
* Deployment.
* Testing.
* Organización del código.

#### CONCRETAMENTE:

* Construye sobre `http`.
* Procesa la petición a través middlewares.
* Asocia rutas a manejadores.
* Procesa los objetos de petición y respuesta.
* Visualiza templates.
* Nosotros escogemos qué middlewares queremos usar, y en qué orden.

#### Frameworks inspirados o basados en Express:

* [Koa](https://koajs.com/)
* [Hapi](https://hapijs.com/)
* [Kraken](http://krakenjs.com/)
* [Sails](https://sailsjs.com/)
* [Adonis](https://adonisjs.com/)
* [Total](https://www.totaljs.com/)
* [Locomotive](http://www.locomotivejs.org/)
* [Geddy](http://geddyjs.org/)

### Middlewares

Express.js se ayuda de paquetes adicionales, para mantener su core simple y minimalista: los _[Middlewares](http://expressjs.com/en/guide/using-middleware.html)_.

Son módulos _**plug and play**_ que se pueden apilar arbitrariamente en cualquier orden y proveen cierta funcionalidad.

Hay de dos tipos:

1. **Filtros**: procesan tráfico entrante/saliente, pero no responden a ninguna petición. Por ejemplo `bodyParser`.
1. **Proveedores**: ofrecen respuestas automáticas a algún tipo de petición. Por ejemplo `static`.

Escribir middlewares para express es muy sencillo:

* Una función que recibe 3 parámetros: `req`, `res`, `next`.
* Al terminar su tarea, tiene que invocar a `next()`:
  * **Sin parámetro**: se invoca al siguiente middleware del stack.
  * **Con parámetro**: se cambia la ruta a lo que se pase como parámetro.
* Dos maneras de activar middlewares:
  1. **Globalmente**, activos para toda la app.
  1. **Locales**. para ciertas rutas.

### Templates Engines

Express tiene un mecanismo para renderizar plantillas que es:

* Agnóstico
* Modular
* Simple

Templates compatibles con Express:

* [Jade](http://jade-lang.com/)
* [Pug](https://pugjs.org/)
* [EJS](http://ejs.co/)
* [Handlebars](http://handlebarsjs.com/)
* [Hogan.js](http://twitter.github.io/hogan.js/)
* [Dust](http://www.dustjs.com/)
* [Twig.js](https://github.com/twigjs/twig.js)
* [Vash](https://github.com/kirbysayshi/vash)

[🔙 Regresar](#nodejs)

## [Socket.IO](https://socket.io/)

### ¿Qué es?

* Una librería para manipular websockets.
* Muy popular.
* Fallback para navegadores obsoletos.
* Muy fácil de usar.
* Servidor / Cliente.
* [API Docs](https://socket.io/docs/).

### ¿Qué son los [WebSockets](https://www.websocket.org/)?

* Protocolo de comunicación.
* Full-duplex.
* Una sola conexión permanente.
* Stream de mensajes.
* Contenido en tiempo real.
* El cliente puede enviar y recibir datos en tiempo real.
* Orientado a eventos (mensajes).
* Siempre conectado.
* Baja latencia.
* Son fundamentales, para:
  * Aplicaciones colaborativas.
  * Juegos multijugador.
  * Envío de datos.
  * Cargar recursos.
* En resumen: "tiempo real" en vez de "a petición".

[🔙 Regresar](#nodejs)

## [MongoDB](https://www.mongodb.com/)

### Diferencias ente SQL y NoSQL

SQL | NoSQL
-- | --
_Structured Query Language_ | _Not Only SQL_
Relacional | No Relacional
Tablas | Colecciones
Registros | Documentos (BSON)
Campos | Atributos
Esquema definido | Esquema libre
Sin lazy loading | Con lazy loading

### ¿Qué es?

> MongoDB es una base de datos NoSQL de tipo documental con alta escalabilidad y flexibilidad que:
> * Almacena datos en documentos flexibles, similares a JSON , lo que significa que los campos pueden variar de un documento a otro y la estructura de datos se puede cambiar con el tiempo.
> * El modelo de documento se correlaciona con los objetos en el código de la aplicación , facilitando el trabajo de los datos.
> * Las consultas ad hoc, la indexación y la agregación en tiempo real proporcionan formas poderosas de acceder y analizar datos.
> * Es una base de datos distribuida en su núcleo , por lo que la alta disponibilidad, la escala horizontal y la distribución geográfica están integradas y son fáciles de usar.
> * Es gratuita y de código abierto , publicado bajo la Licencia Pública General Affero de GNU.

#### Características

* Sin esquema, no impone forma a los datos.
* Alto rendimiento, enfocada en escalabilidad horizontal.
* Sharding automático (balanceo de carga de datos).
* Lenguaje de consultas potente.
* No necesita migraciones, ni reestructuración.
* Permite estructuras muy complejas.
* Agregado de datos, índices geoespaciales y búsquedas FTS (Full Text Search).
* Almacenamiento eficiente de blobs y ficheros.
* Sin transacciones y sin JOINs, pero, puede empotrar documentos y arrays.

#### Úsalo para

* Aplicaciones con mucha carga de escritura.
* Agregado de datos a un nivel medio/alto.
* Aplicaciones con datos muy heterogéneos.
* Enormes colecciones de datos (sharding).
* Almacenar ficheros (sharding).
* Se suelen favorecer los diseños desnormalizados.

### Conceptos Básicos

#### [Instalación](https://www.mongodb.com/download-center?jmp=nav#community)

* [Linux](https://docs.mongodb.com/manual/administration/install-on-linux/)
* [macOS](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)
* [Windows](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)

#### Bases de datos

* Es un almacén de documentos, dividido en colecciones.
* Al igual que en JS, todo es un objeto.
* ¡Se integra genial con JavaScript!
* Los documentos son básicamente, objetos JSON Binarios (BSON).
* El límite de un documento es < 16MB.
* Consultas basadas en la estructura del documento.

#### Colecciones

* Una colección es una agrupación de documentos.
* Puede alojar cualquier documento (no impone estructura).
* Puede alojar documentos con diferentes estructuras.

#### Documentos

Estructura de un documento:

```json
{
  "_id" : ObjectId("524872a99c50880000000001"),
  "email" : "jonmircha@gmail.com",
  "password" : "qwerty",
  "name" : "Jonathan",
  "date" : ISODate(),
  "token" : "hm6ly43v.0o1or"
}
```

Un documento puede contener arreglos y otros documentos:

```json
{
  "_id" : ObjectId("5249a2e9b90687d56453b2f3"),
  "text" : "Soy un comentario",
  "user" : {
    "_id" : ObjectId("524872a99c50880000000001"),
    "nombre" : "Usuario Prueba",
    "avatar" : "/img/user-test.jpg"
  },
  "tags" : [ "test", "prueba" ]
}
```

#### [Documentación](https://docs.mongodb.com/manual/)

* [Comandos del Shell](https://docs.mongodb.com/manual/reference/method/)
* [Comandos para Bases de Datos](https://docs.mongodb.com/manual/reference/command/)
* [Tipos de datos BSON](https://docs.mongodb.com/manual/reference/bson-types/index.html)
* [CRUD en documentos](https://docs.mongodb.com/manual/crud/)
* [Operadores](https://docs.mongodb.com/manual/reference/operator/)
* [Validación de esquemas](https://docs.mongodb.com/manual/core/schema-validation/)
* [Modelado de Datos](https://docs.mongodb.com/manual/core/data-model-design/)
* Relaciones
  * [Relación 1 a 1](https://docs.mongodb.com/manual/tutorial/model-embedded-one-to-one-relationships-between-documents/)
  * [Relación 1 a Muchos, con documento embebido](https://docs.mongodb.com/manual/tutorial/model-embedded-one-to-many-relationships-between-documents/)
  * [Relación 1 a Muchos, con documento referenciado](https://docs.mongodb.com/manual/tutorial/model-referenced-one-to-many-relationships-between-documents/)
* [Funciones Almacenadas](https://docs.mongodb.com/manual/tutorial/store-javascript-function-on-server/index.html)


[🔙 Regresar](#nodejs)

## API REST

### ¿Qué es una API REST?

Digamos que estás tratando de encontrar videos sobre Batman en Youtube.

Abres Youtube, escribe "Batman" en un campo de búsqueda, pulsas enter, y verás una lista de videos sobre Batman.

Una _**API REST**_ funciona de manera similar. Buscas algo y obtienes una lista de resultados del servicio que está solicitando.

Una _**API**_ es una _**Interfaz de Programación de Aplicaciones**_.

Es un conjunto de reglas que permiten que los programas se comuniquen entre sí. El desarrollador crea la API en el servidor y permite que el cliente hable con ella.

_**REST**_  significa "_**Transferencia de Estado Representacional**_".

Es un conjunto de reglas que los desarrolladores siguen cuando crean un API. Una de estas reglas establece que se debe poder obtener un dato al que se le llama _**recurso**_  cuando se vincula a una URL específica.

Cada URLs a la que se puede acceder  se denomina una  _**petición**_ mientras que los datos que regresan son la _**respuesta**_ a dicha petición.

#### Anatomía de una petición

Una petición se compone de cuatro elementos:

1. Punto final o Ruta ( _**endpoint / route**_ ).
1. Método ( _**method**_ ).
1. Cabeceras ( _**headers**_ ).
1. Datos o Cuerpo ( _**data / body**_ ).

### Ruta

La ruta es la url que la API solicita.

Por ejemplo, la ruta del API de GitHub sería:

```
https://api.github.com/
```

La ruta determina el recurso que se está solicitando. Piensa en ello como un contestadora automática que te pide que presiones 1 para una opción, 2 para otro servicio, 3 para hablar con un operador y así sucesivamente.

Puede acceder a las rutas al igual que puede vincular a partes de un sitio web.

Por ejemplo, en un sitio hecho en WordPress, para obtener una lista de todas las publicaciones etiquetadas con alguna palabra por ejemplo "JavaScript" en Smashing Magazine, se navega así:

```
https://css-tricks.com/tag/javascript/
```

Donde `https://css-tricks.com/` es el _**endpoint**_  y `/tag/javascript` es el _**path**_ de la ruta.

En un API para comprender qué rutas hay disponibles es necesario consultar la documentación.

Por ejemplo, para obtener una lista de repositorios de cierto usuario a través de la [API de GitHub](https://developer.github.com/v3/). La documentación indica lo siguiente:

```
/users/:username/repos
```

Cualquier signo de dos puntos '**`:`**' en una ruta denota una variable. Se debe reemplazar esta variable con los valores reales cuando se envía una petición. Por ejemplo:

```
https://api.github.com/users/jonmircha/repos
```

#### Parámetros de Consulta

La parte final de una ruta se le denomina parámetros de consulta ( _**query parameters**_ ).

Técnicamente, los parámetros de consulta no son parte de la arquitectura _**REST**_, pero muchas API los usan, ya que dan la opción de modificar una petición con pares de _**clave=valor**_.

Siempre comienzan con un signo de interrogación '**?**'. Cada juego de clave=valor se separan con un signo de _**ampersand**_ '**&**'. Por ejemplo:

```
?query1=value1&query2=value2
```

Regresando al ejemplo del API de GitHub, cuando se intenta obtener una lista de los repositorios de un usuario, se pueden agregar tres posibles parámetros para modificar los resultados de una petición, como lo indica la [documentación](https://developer.github.com/v3/repos/#list-user-repositories):

1. `type`
1. `sort`
1. `direction`

Por ejemplo, si se desea obtener una lista de los repositorios que un usuario empuja ( **`push`** ) la petición sería así:

```
https://api.github.com/users/jonmircha/repos?sort=pushed
````

#### JSON

Todos los lenguajes de programación pueden enviar peticiones a APIs, por ejemplo en JavaScript se puede usar _**AJAX**_ o _**Fetch**_.

La manera en como devuelven los datos las APIs es en _**JSON**_ ( _**JavaScript Object Notation**_ ) un formato común para enviar y recibir datos a través de una API REST.

La respuesta que la API de GitHub devuelve es JSON.

Un objeto JSON se parece a un objeto JavaScript. En JSON, cada propiedad y valor debe estar entre comillas dobles, como este ejemplo:

```json
{
  "propiedad1": "valor1",
  "propiedad2": "valor2",
  "propiedad3": "valor3"
}
```

### Método

El método es el tipo de petición que se envía al servidor de la API. Los métodos más utilizados son:

* _**GET**_
* _**POST**_
* _**PUT**_
* _**DELETE**_

Estos métodos proporcionan un significado para la petición que se está realizando y  se utilizan para realizar las cuatro acciones posibles a un modelo de datos, mejor conocido como _**CRUD**_: _**Create**_, _**Read:**, _**Update**_ y _**Delete**_.

| Método | Significado |
| -- | -- |
| _**GET**_ |	Esta petición se usa para obtener un recurso de un servidor. Si se realiza una petición `GET`, el servidor busca los datos que se han solicitado y se los envía de vuelta. En otras palabras, una petición `GET` realiza una operación` READ`. Este es el método de petición predeterminado. |
| _**POST**_ | Esta petición se usa para crear un nuevo recurso en un servidor. Si se realiza una petición `POST`, el servidor crea una nueva entrada en la base de datos y le dice si la creación es exitosa. En otras palabras, una petición `POST` realiza una operación` CREATE`. |
| _**PUT**_ | Estas dos peticiones se utilizan para actualizar un recurso en un servidor. Si se realiza una petición `PUT`, el servidor actualiza una entrada en la base de datos y le informa si la actualización fue exitosa. En otras palabras, una petición `PUT` realiza una operación `UPDATE`. |
| _**DELETE**_ | Esta petición se usa para eliminar un recurso de un servidor. Si se realiza una petición `DELETE`, el servidor borra una entrada en la base de datos y le dice si la eliminación fue exitosa. En otras palabras, una petición `DELETE` realiza una operación` DELETE`. |

Las APIs deben saber qué método usa cada petición. Regresando a nuestro ejemplo de GitHub, para obtener una lista de los repositorios de un usuario, se necesita una petición `GET`:

```
GET /users/:username/repos
```

Con el API [Fetch](https://developer.mozilla.org/es/docs/Web/API/Fetch_API/Utilizando_Fetch) de JavaScript nuestro ejemplo al API REST de GitHub quedaría así:

```js
let route = 'https://api.github.com/users/jonmircha/repos',
  options = { method: 'GET' }

fetch(route, options)
  .then(res => console.log(res))
  .catch(err => console.log(err))
```
Para crear un nuevo repositorio GitHub, se necesita hacer una petición `POST`, con Fetch y JavaScript sería:

```js
let route = 'https://api.github.com/user/repos',
  options = { method: 'POST' }

fetch(route, options)
  .then(res => console.log(res))
  .catch(err => console.log(err))
```

Al ejecutar esta petición. Se obtendrá una respuesta que indica que se requiere autenticación:

```js
Response {
  body: ReadableStream,
  bodyUsed: false,
  headers: Headers {},
  ok: false,
  redirected: false,
  status: 401,
  statusText: "Unauthorized",
  type: "cors",
  url: "https://api.github.com/user/repos"
}
```

### Cabeceras

Las cabeceras se utilizan para proporcionar información tanto al cliente como al servidor. Se pueden utilizar para muchos fines, como la autenticación y la información sobre el contenido del cuerpo de la petición.

La lista de cabeceras válidas se puede consultar en la Referencia [HTTP headers](https://developer.mozilla.org/es/docs/Web/HTTP/Headers) de MDN.

Las cabeceras HTTP son pares de clave-valor que están separados por dos puntos. El siguiente ejemplo muestra una cabecera que le dice al servidor que espera contenido JSON.

```json
{
  "Content-Type": "application/json"
}
```

Regresando al ejemplo de GitHub, podemos mandar una cabecera con Fetch de la siguiente manera:

```js
let route = 'https://api.github.com/',
  options = {
    headers: {
      'Content-Type': 'application/json'
    }
  }

fetch(route, options)
  .then(res => console.log(res))
  .catch(err => console.log(err))
```

### Datos

Los datos ( a veces llamados _cuerpo_ o _mensaje_ ) contienen información que se desea enviar al servidor. Esta opción sólo se utiliza con peticiones `POST`, `PUT` o `DELETE`.

Regresando al ejemplo del API de GitHub, podemos mandar datos de la siguiente manera:

```js
let route = 'https://api.github.com/user/repos',
  data = { login: 'jonmircha' },
  options = {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify(data)
  }

fetch(route, options)
  .then(res => console.log(res))
  .catch(err => console.log(err))
```

### Códigos de estado de HTTP

Algunos de los mensajes recibidos anteriormente, como "_**Unauthorized**_" u "_**OK**_" son mensajes del servidor, mejor conocidos como códigos de estado HTTP que permiten decir el estado de la respuesta. El rango de valores van de  100+ a 500+.

| Código | Significado |
| -- | -- |
| 100+ | Respuestas informativas |
| 200+ | Peticiones correctas |
| 300+ | Redirecciones |
| 400+ | Errores del cliente |
| 500+ | Errores de servidor |

Para más información consulta la [Referencia de estado HTTP de MDN](https://developer.mozilla.org/es/docs/Web/HTTP/Status).

[🔙 Regresar](#nodejs)
