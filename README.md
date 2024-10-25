#### DEV
1. Clonar el repo
2. Crear el `.env` basado en `.env.template`
3. Ejecutar el comando `git submodule update --init --recursive`
4. Ejecutar el comando `docker-compose up --build`. Si está en Linux y tiene problemas de permisos con el *volumen* de la base de datos de `orders-ms`, ejecute el anterior comando con `sudo`.

#### DEV (eng)
1. Clone the repo
2. Create `.env` file based on `.env.template`
3. Execute `git submodule update --init --recursive`
4. Execute `docker-compose up --build`. If the build doesn't works because of permission problems with `/orders-ms/postgres` folder (pgdb-orders-ms volume) . Please run the command as `sudo`.

### Pasos para crear los Git Submodules


1. Crear un nuevo repositorio en GitHub
2. Clonar el repositorio en la máquina local
3. Añadir el submodule, donde `repository_url` es la url del repositorio y `directory_name` es el nombre de la carpeta donde quieres que se guarde el sub-módulo (no debe de existir en el proyecto)
```
git submodule add <repository_url> <directory_name>
```
4. Añadir los cambios al repositorio (git add, git commit, git push)
Ej:
```
git add .
git commit -m "Add submodule"
git push
```
5. Inicializar y actualizar Sub-módulos, cuando alguien clona el repositorio por primera vez, debe de ejecutar el siguiente comando para inicializar y actualizar los sub-módulos
```
git submodule update --init --recursive
```
6. Para actualizar las referencias de los sub-módulos
```
git submodule update --remote
```


## Importante
Si se trabaja en el repositorio que tiene los sub-módulos, **primero actualizar y hacer push** en el sub-módulo y **después** en el repositorio principal. 

Si se hace al revés, se perderán las referencias de los sub-módulos en el repositorio principal y tendremos que resolver conflictos.



### PROD
Run all 
1. Clonar el repo
2. Crear el `.env` basado en el `.env.template`
3. Ejecutar el comando
```
docker-compose -f docker-compose.prod.yaml build
```