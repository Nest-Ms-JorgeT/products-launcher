#### DEV
1. Clonar el repo
2. Crear el `.env` basado en `.env.template`
3. Ejecutar el comando `docker-compose up --build`. Si está en Linux y tiene problemas de permisos con el *volumen* de la base de datos de `orders-ms`, ejecute el anterior comando con `sudo`.

#### DEV (eng)
1. Clone the repo
2. Create `.env` file based on `.env.template`
3. Execute `docker-compose up --build`. If the build doesn't works because of permission problems with `/orders-ms/postgres` folder (pgdb-orders-ms volume) . Please run the command as `sudo`.