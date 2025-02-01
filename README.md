<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

## Stack usado

*Nest

*MongoDb


# Ejecutar en desarrollo
1. Clonar el repositorio y asignamos al nuevo repo ya creado en git
```bash
git clone https://github.com/martinprado1000/nest-10-plantilla.git nuevoNombre

git remote set-url origin https://github.com/martinprado1000/nuevoNombre.git
```

2. Tener Nest CLI instalado:
```bash
npm i -g @nest/cli
```

3. Levantar la base de datos. Esta solo dockerizada la base de datos, no la app.
```bash
docker-compose up -d
```

4. Renombrar el archivo __.env.template__ por __.env__ y llenar las variables de entorno e instalar las dependencias:
```bash
#Instalar dependencias
npm install
```

5. Ejecutar en desarrollo
```bash
# Esto ejecuta el archivo docker.compose.yml
$ npm run star:dev

# Ejecutar seed de Usuarios,inserta multiples datos.
http://localhost:3000/api/seed
```


# Construir y ejecutar para producción
```bash
# Construir
$ npm run build

# Ejecutar
$ npm run start:prod
```

# Construir y ejecutar para producción la app y la base en mongo DOCKERIZADO

1. Renombrar el archivo __.env.template__ por __.env.prod__ y llenar las variables de entorno.

2. Crear las imagenes
```bash
# Usamos el docker-compose.prod.yaml y el .env.prod que son los de produccón.

docker-compose -f docker-compose.prod.yaml --env-file .env.prod up --build

# Si las imagenes ya fueron creadas y solo necesitamos levantar ejecutar:
docker-compose -f docker-compose.prod.yaml --env-file .env.prod up -d
```

#
### ¿QUE HACE ESTA App?
Configuraciones:

* Entidades: User, Auth, Logger

* Autenticacion y autorizacion. Recibe roles, un string o como arreglo: SUPERADMIN, ADMIN, OPERATOR, USER.

* .env  .env.template  .env.prod.

* ConfigModule,ConfigService,Joi.

* Logger Winston.

* CorrelationId.

* Swagger.

* Si ejecuto en mode dev solo esta dockerizada la db. 

* En prod usamos el archivo docker-compose.prod.yml donde esta dockerizada la app y la db.

