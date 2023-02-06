
# Getting started
Para correr los test con Newman, es necesario tener una version de Node.js >= v10. 

# Installation
```
npm install -g newman
```

# Uso de la CLI de Newman
El comando de ejecución newman le permite especificar una colección para ejecutar. Puede exportar fácilmente su colección Postman como un archivo json desde la aplicación Postman y ejecutarlo con Newman.
En éste repositorio:
```
newman run test/AbstractaPetStore.postman_collection.json
git clone git@github.com:juanignaciorey/Api-Testing-Abstracta.git
cd ./Api-Testing-Abstracta
```

# Modo de uso
```
newman run test\US-240-TX-PetStoreAbstracta.postman_collection.json
```

# Ejemplo del reporte corriendo
```
US-240|TX|PetStoreAbstracta

□ US 240 | TS 1 | Petstore | User
└ TC 01 | Crear un usuario
  POST https://petstore.swagger.io/v2/user/createWithArray [200 OK, 370B, 764ms]
  √  Response code is 200
  √  Message is 'ok'

└ TC 02 | Hacer login con el usuario recién creado
  GET https://petstore.swagger.io/v2/user/login?username=usuario73&password=6848 [200 OK, 471B, 742ms]

└ TC 06 | Hacer el logout a la aplicación
  GET https://petstore.swagger.io/v2/user/logout [200 OK, 370B, 164ms]

□ US 240 | TS 2 | Petstore | Pet
└ TC 03 | Listar todas las mascotas que tengan el status “disponible”
  GET https://petstore.swagger.io/v2/pet/findByStatus?status=available [200 OK, 67.36kB, 472ms]

└ TC 05 | Agregar una nueva mascota a la Store
  POST https://petstore.swagger.io/v2/pet [200 OK, 542B, 164ms]

└ TC 04 | Consultar los datos de una mascota en específico
  GET https://petstore.swagger.io/v2/pet/9223372036854598000 [404 Not Found, 384B, 161ms]

□ US 240 | TS 3 | Petstore | Store
└ US 240 | TS3 | TC05 | Crear una orden (compra) para una mascota
  POST https://petstore.swagger.io/v2/store/order [200 OK, 450B, 164ms]

□ US 240 | TS 4 | TC X | Otros / US 240 | TS 4 | Petstore | Store By ID
└ Buscar orden de compra por id
  GET https://petstore.swagger.io/v2/store/order/1500 [404 Not Found, 386B, 168ms]

└ Eliminar orden de compra por ID
  DELETE https://petstore.swagger.io/v2/store/order/:orderId [404 Not Found, 438B, 162ms]

┌─────────────────────────┬─────────────────────┬────────────────────┐
│                         │            executed │             failed │
├─────────────────────────┼─────────────────────┼────────────────────┤
│              iterations │                   1 │                  0 │
├─────────────────────────┼─────────────────────┼────────────────────┤
│                requests │                   9 │                  0 │
├─────────────────────────┼─────────────────────┼────────────────────┤
│            test-scripts │                  12 │                  0 │
├─────────────────────────┼─────────────────────┼────────────────────┤
│      prerequest-scripts │                  10 │                  0 │
├─────────────────────────┼─────────────────────┼────────────────────┤
│              assertions │                   2 │                  0 │
├─────────────────────────┴─────────────────────┴────────────────────┤
│ total run duration: 3.9s                                           │
├────────────────────────────────────────────────────────────────────┤
│ total data received: 67.75kB (approx)                              │
├────────────────────────────────────────────────────────────────────┤
│ average response time: 329ms [min: 161ms, max: 764ms, s.d.: 245ms] │
└────────────────────────────────────────────────────────────────────┘
```
