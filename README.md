## Introducción a Testcontainers

# Testing

Una de las tareas clave en el desarrollo de software es el testing.

# Niveles de test

Según la pirámide de niveles de prueba de [Mike Cohn](https://martinfowler.com/bliki/TestPyramid.html); Hay 3 niveles principales:

1. Prueba unitaria
2. Prueba de Integración
3. Prueba de interfaz de usuario

# Pirámide de test

![Figura 1. Pirámide de prueba.](img/test-pyramid.png)
[https://martinfowler.com/bliki/TestPyramid.html](https://martinfowler.com/bliki/TestPyramid.html)

# Test de integración
Pruebas unitarias como base, y test de integración para verificar interacción con componentes externos fuera de la lógica de negocios.

# Test containers 
Testcontainers es una biblioteca Java que podemos usar para ejecutar diferentes frameworks de pruebas (como [JUnit](https://junit.org/junit5/) o [Spock](http://spockframework.org/)) con contenedores [docker](https://www.docker.com/).

# No solo Java

Hay implementaciones en Go, dotNet, Python, Node y Rust.

# Módulos 

* Base de datos (SQL, NoSQL)
* Nube (AWS vía localstack, Azure, GCloud)
* Kafka, MockServer, Solr, Vault...
* GenericContainers 

# Requisitos para una aplicación Java

* [Docker instalado](https://www.testcontainers.org/supported_docker_environment/)
* [junit-jupiter](https://search.maven.org/search?q=a:junit-jupiter%20AND%20g:org.testcontainers) si usamos JUnit 5.

# @notaciones

* [`@Testcontainers`](https://javadoc.io/doc/org.testcontainers/junit-jupiter/latest/org/testcontainers/junit/jupiter/Testcontainers.html): esta anotación maneja automáticamente el ciclo de vida del contenedor.

* [`@Container`](https://javadoc.io/doc/org.testcontainers/junit-jupiter/latest/org/testcontainers/junit/jupiter/Container.html): marca los contenedores para ser administrados por la extensión de Testcontainers.     

# Demo

# Conclusiones

* El uso de contendores es bastante sencillo.

* La opción [`withTmpFs`](https://javadoc.io/static/org.testcontainers/testcontainers/1.15.0-rc2/org/testcontainers/containers/GenericContainer.html#withTmpFs-java.util.Map -) que nos permite mapear el volumen del contenedor a nuestra memoria host.

* Si queremos acelerar nuestras pruebas de integración, podemos declarar contenedores como campos estáticos para compartir entre pruebas. En nuestro caso, nuestra prueba se ejecutó en un promedio de 150 ms.

# Más información

* https://testcontainers.org
* @testcontainers

# Juan Moreno

* Blog: https://proitcsolution.com.ve
* Twitter: [@JuanMorenoDev](https://twitter.com/JuanMorenoDev)
* Presentation link: https://bit.ly/testcontainers-intro 
* Repositorio: https://github.com/JuanMorenoDeveloper/testcontainers-samples