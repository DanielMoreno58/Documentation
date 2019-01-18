# Rails

### Comandos Rails

rails server = inicio de servidor en rails.

rails server p -3001 = inicio de servidor en rails con puerto 3001.

rails routes = rutas que tiene rails.

rails generate controller "nombre" = genera un controlador en rails.

rails generate model "nombre" + parámetros" + referencias (opcional) = genera un modelo en rails.

rails generate migration "nombre" = genera una migración en rails.

gem which *gemname* = obtiene la dirección de una gema instalada.

rails c = consola rails

gem query --local = muestra la lista de las gemas instaladas.

!!! = Salta todos los binding.pry

rails g serializer user = genera un serializador con la gema 'active_model_serializers'

### Notas del lenguaje Rails

Variables:
  ```
  @var = variable de instancia global que se puede usar en todo el programa
  `var x = 2´ =  variable normal de ruby se puede colocar cualquier tipo de
  valor
  ```

Clases:
  ```
  Class controlador < ApplicationController = heredación de clases
  Class clase1::clase2 = representa un clase dentro de una clase (compact class)
  ```

```
Class clase1
  Class clase2
  end
end
```
Lo anterior representa una clase dentro de otra clase (nested class)

Métodos públicos:
  ```
  def metodo
  end
  ```

Métodos privados:
  ```
  private

  def metodo
  End
  ```

!Nota: los métodos privados iran debajo de los publico y todos los métodos
declarados posterior a la palabra private serán privados.

---Gema Pry--------------------------------------------------------------------

  binding.pry = funciona como breakpoint para detener el código justo donde
  lo necesitas

### 12 principios para la creación de una app

1.CodeBase
Mantener un control de versiones y realizar deploys en una base de código
establecidas manteniendo un orden con el código inicial y mantenerlo escalable
y utilizable para otros desarrolladores con el uso de los estándares de Git.

2.Dependencies
Escoger y configurar los paquetes y librerías a usar en el proyecto en
directorios como "vendoring" o "bundling".

3.Config
Realizar la configuración del proyecto en cuanto rutas, base de datos, y
variables de entorno (desarrollo, staging, producción, test) durante todo
el proyecto.

4.Backing services
Se define los servicios a utilizar y tienen que estar unificados al mismo
deploy, no hay distinción entre servicios locales y de terceros, todos son
manejados con una url apuntando el servicio deseado sin necesidad de cambio en
el código.

5.Build,release,run
Se define los tres escenarios que se encuentran en una etapa de no desarrollo
los cuales se representan como:
  -Build: Se realiza la complicación y se integran las dependencias del proyecto
  -Release: Toma el escenario de build y lo combina con la configuración(config)
  del proyecto. También se considera que cada release tendrá un ID único,
  generalmente la versión del proyecto; ejemplo: v1.0.1.
  -Run: Se corre la aplicación en un estado de ejecución realizando algunos
  'procesos' del proyecto.
Estos escenarios deben de estar estrictamente separados ya que cada escenario
realiza diferentes acciones que conllevan a construir el proyecto para un estado
de desarrollo.

6.Process
Se define los procesos que tiene la app, ya que una app puede ejecutar uno
o más procesos que requieren espacio de memoria en la computadora o algún dato
mediante una cookie por lo que se mantiene a la espera como un trigger para
cuando se obtenga la información pueda actuar sobre esta.

7.Port binding
Se define y configura los web-services en base a las tecnologías utilizadas
del proyecto creando un enlace donde se pueda visualizar el proyecto en todos
los ambientes.

8.Concurrency
Se catalogan los procesos ya que cada proceso tiene que estar separado
con el fin de que el proyecto pueda ser escalable dividido por
el tipo de proceso,  por ejemplo el proceso que ejecuta PHP con Apache o
el envío de datos a través de una API, etc.

9.Disposability
Se definen el fin de los procesos con el fin de que estos sean 'desechables'
para cuando termine pueda dejar espacio en memoria haciendo más eficiente el
sistema y escalable en cuanto a los recursos que se cuentan.

10.Dev/prod parity
Hacer que la diferencia entre desarrollo y producción sea mínima, en cuestión
de tiempos a nivel de código personal para sean horas en vez de semanas, en
cuestión de que el desarrollador que trabajo en 'development' sea la misma
persona que haga el deploy en producción eficientizando el trabajo en equipo,
y mantener el nivel de desarrollo y producción lo más parecido y cercano posible
para estar actualizados con la información del proyecto y que las versiones sean
constantes y cambiantes en el proyecto.

11.Logs
Visualizar los logs para usar esa información para beneficio de nuestro proyecto
ya que estos pueden mostrar errores y/o datos clave que mejoran nuestra app,
además que muestran eventos que se realizaron en el programa e inclusive podemos
graficar la actividad que esta teniendo el programa.

12.Admin processes
Facilitar y aprender el uso de las tareas administrativas que a menudo pueden
ser usadas por los desarrolladores, como por ejemplo, la migración de la base de
datos, entre otras tareas.

### For create a role of a non-existing database we use:

> In our `database.yml`:

```yaml
development:
  adapter: postgresql
  encoding: utf8
  database: app_development
  pool: 5
  username: app_name
  password:
```

> In our `bash`:

```bash
$ psql -d postgres
postgres=# create role app_name login createdb;
postgres=# \q
```

---

### Rails composer guide

## Crear nueva app en Rails

Si tienes una carpeta e hiciste un git clone de un repositorio ya existente, corre el siguiente comando:

```rails new . -m https://raw.github.com/RailsApps/rails-composer/master/composer.rb```

## Atributos

Selecciona las opciones en **negritas**:

*Build a starter application?*
1)  Build a RailsApps example application
2)  Contributed applications

**3)  Custom application (experimental)**

*Get on the mailing list for Rails Composer news?*

**Enter**

*Web server for development?*

**1)  Puma (default)**

2)  Thin
3)  Unicorn
4)  Phusion Passenger (Apache/Nginx)
5)  Phusion Passenger (Standalone)

*Web server for production?*

**1)  Same as development**

2)  Thin
3)  Unicorn
4)  Phusion Passenger (Apache/Nginx)
5)  Phusion Passenger (Standalone)

*Database used in development?*
1)  SQLite

**2)  PostgreSQL**

3)  MySQL

*Template engine?*

**1)  ERB**

2)  Haml
3)  Slim

*Test framework?*
1)  None

**2)  RSpec**

*Continuous testing?*

**1)  None**

2)  Guard

*Front-end framework?*
1)  None

**2)  Bootstrap 4.0**

3)  Bootstrap 3.3
4)  Bootstrap 2.3
5)  Zurb Foundation 5.5
6)  Zurb Foundation 4.0
7)  Simple CSS

*How to install jQuery?*
1)  Add jquery-rails gem
**2)  Add using yarn**

*Add support for sending email?*
1)  None
2)  Gmail
3)  SMTP

**4)  SendGrid**

5)  Mandrill

*Authentication?*

**1)  None**

2)  Devise
3)  OmniAuth

*Authorization?*

**1)  None**

2)  Simple role-based
3)  Pundit

*Add pages?*

**1)  None**

2)  Home
3)  Home and About
4)  Home and Users
5)  Home, About, and Users

*Install page-view analytics?*
1)  None

**2)  Google Analytics**

3)  Segment.com

*Google Analytics ID?*

**Enter**

*Prepare for deployment?*
1)  no

**2)  Heroku**

3)  Capistrano

*Disable Rails Turbolinks? (y/n)*

**y**

*Create a GitHub repository? (y/n)*

**n**

Add gem and file for environment variables?

**1)  None**

2)  Add .env with Foreman

*Improve error reporting with 'better_errors' during development? (y/n)*

**y**

*Use 'pry' as console replacement during development and test? (y/n)*

**y**

*Use 'rubocop' to ensure that your code conforms to the Ruby style guide? (y/n)*

**y**

*Username for PostgreSQL?(leave blank to use the app name)*

**Enter**

*Host for PostgreSQL in database.yml? (leave blank to use default socket connection)*

**Enter**

*Okay to drop all existing databases named rails-trabajo-en-restaurantes-admin? (y/n)*

**y**
