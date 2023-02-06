
# Getting started
Para correr los test con Newman, es necesario tener una version de Node.js >= v10. 

# Installation
The easiest way to install Newman is using NPM. If you have Node.js installed, it is most likely that you have NPM installed as well.

```
npm install -g newman
```

# Uso de la CLI de Newman
El comando de ejecución newman le permite especificar una colección para ejecutar. Puede exportar fácilmente su colección Postman como un archivo json desde la aplicación Postman y ejecutarlo con Newman.
En éste repositorio:
```
newman run test/AbstractaPetStore.postman_collection.json
```

# Agregar Reporte HTML
```
npm install -g newman-reporter-html
```
docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11