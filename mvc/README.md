# Introduccion
### ¿Qué es MVC?
El patrón de diseño (de software) MVC se encarga de separar la lógica de negocio de la interfaz de usuario y es el mas utilizado en aplicaciones web, framework, etc, ya que facilita la funcionalidad, mantenibilidad, y escalabilidad del sistema, de forma comoda y sencilla, a la vez que ayuda no mezclar lenguajes de programación en el mismo código, el conocido “código espagueti”.
MVC divide las aplicaciones en tres niveles de abstracción:

* Modelo: es la lógica de negocios. Es decir las clases y métodos que se comunican directamente con la base de datos.
* Vista: es la encargada de mostrar la información al usuario, con de forma gráfica y legible.
* Controlador: el intermediario entre la vista y el modelo, se encarga de controlar las interacciones del usuario en la vista, pide los datos al modelo y los devuelve de nuevo a la vista para que esta los muestre al usuario. Es decir las llamadas a clases y métodos, y los datos recibidos de formularios.

# Marco Teórico 
### ¿Qué frameworks utilizan el modelo MVC?
1. Laravel
2. CodeIgniter
3. Symfony
4. Zend
5. Phalcon
6. CakePHP
7. Yii
8. FuelPHP
### Ventajas
* Nuestros sistemas serán más limpios, simples, más fácilmente mantenibles y, a la postre, más robustos.
* Mayor velocidad de desarrollo en equipo, que es consecuencia de lo anterior, ya que al estar separado en tres partes tan diferenciadas, diferentes programadores pueden ocuparse de cada parte en paralelo. Esto la hace ideal para el desarrollo de aplicaciones grandes.
* Múltiples vistas a partir del mismo modelo, pudiendo reaprovechar mucho mejor los desarrollos y asegurando consistencia entre ellas.
* Facilidad para realización de pruebas unitarias.
### ¿Qué otros modelos/frameworks existen de patrones de diseño?
* (MVVM) significa Modelo Vista VistaModelo, porque en este patrón de diseño se separan los datos de la aplicación, la interfaz de usuario pero en vez de controlar manualmente los cambios en la vista o en los datos, estos se actualizan directamente cuando sucede un cambio en ellos, por ejemplo si la vista actualiza un dato que está presentando se actualiza el modelo automáticamente y viceversa.
* (MVP) El Patrón Modelo-Vista-Presentador surge para ayudar a realizar pruebas automáticas de la interfaz gráfica, para ello la idea es codificar la interfaz de usuario lo más simple posible, teniendo el menor código posible, de forma que no merezca la pena probarla. En su lugar, toda la lógica de la interfaz de usuario, se hace en una clase separada (que se conoce como Presentador), que no dependa en absoluto de los componentes de la interfaz gráfica y que, por tanto, es más fácil de realizar pruebas.
### Ejemplo de modelo MVC
1. PHP Nativo
```
-- controllers
-- db
-----base.sql
-- models
-- views
-----inicio.php
-index.php
```
2. Laravel 
```
--app/
--bootstrap/
--config/
--database/
--public/
--resources/
--storage/
--tests/
--vendor/
```
3. CodeIgniter
```
--aplication
--system
--user_guide
-index.php
```

### Referencias
https://ingsoftwarei2014.wordpress.com/category/comparacion-de-los-patrones-de-arquitectura-mvc-mv-vm-mvp/

https://www.campusmvp.es/recursos/post/que-es-el-patron-mvc-en-programacion-y-por-que-es-util.aspx

https://victorroblesweb.es/2013/11/18/tutorial-mvc-en-php-nativo/