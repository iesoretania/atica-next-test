# ÁTICA
[![Build Status](https://travis-ci.org/iesoretania/atica-next.svg?branch=master)](https://travis-ci.org/iesoretania/atica-next)
[![SensioLabsInsight](https://insight.sensiolabs.com/projects/525e5e1d-bfc7-408d-9340-8121d5e95c6a/mini.png)](https://insight.sensiolabs.com/projects/525e5e1d-bfc7-408d-9340-8121d5e95c6a)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/iesoretania/atica-next/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/iesoretania/atica-next/?branch=master)
[![Code Climate](https://codeclimate.com/github/iesoretania/atica-next/badges/gpa.svg)](https://codeclimate.com/github/iesoretania/atica-next)

Evolución de la aplicación web para la gestión de centros educativos (en desarrollo, aún no está lista para producción).

Aunque su origen se encuentra en la gestión documental, la nueva iteración permitirá la integración de distintos
módulos. En concreto, están proyectados módulos para la gestión de la Formación en Centros de Trabajo (FCT), de
cumplimentación de encuestas y de gestión de entradas/salidas al centro (HORUS).

Este proyecto utiliza [Symfony2] y otros muchos componentes que se instalan usando [Composer] y [Bower].

Para facilitar el desarrollo se proporciona un entorno [Vagrant] con todas las dependencias ya instaladas.

## Requisitos

- PHP 5.4.x o superior
- Servidor web Apache2 (podría funcionar con nginx, pero no se ha probado)
- Cualquier sistema gestor de bases de datos que funcione bajo Doctrine (p.ej. MySQL, MariaDB, PosgreSQL, SQLite, etc.)
- PHP [Composer]
- [Bower]

## Instalación

- Ejecutar `composer install` desde la carpeta del proyecto.
- Ejecutar `bower install`.
- Configurar el sitio de Apache2 para que el `DocumentRoot` sea la carpeta `web/`
- Modificar el fichero `parameters.yml` con los datos de acceso al sistema gestor de bases de datos.
- Ejecutar `app/console assets:install` para completar la instalación de los recursos en la carpeta `web/`.
- Para crear la base de datos: `app/console doctrine:database:create`.
- Para crear las tablas: `app/console doctrine:schema:create`.
- Para insertar los datos iniciales: `app/console doctrine:fixtures:load`.

## Entorno de desarrollo

Para poder ejecutar la aplicación en un entorno de desarrollo basta con tener [Vagrant] instalado junto con [VirtualBox]
y ejecutar el comando `vagrant up`. La aplicación será accesible desde la dirección http://192.168.33.10/

## Licencia
Esta aplicación se ofrece bajo licencia [AGPL versión 3].

[Vagrant]: https://www.vagrantup.com/
[VirtualBox]: https://www.virtualbox.org
[Symfony2]: http://symfony.com/
[Composer]: http://getcomposer.org
[AGPL versión 3]: http://www.gnu.org/licenses/agpl.html
[Bower]: http://bower.io/
