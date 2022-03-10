# Giphy Search

> Aplicación para buscar gifs en la API de giphy y levantarlo con Azure, usando
> Azure functions como BackEnd.

## Requisitos

* [Git-scm](https://git-scm.com/)
* Install [Azure Functions Core Tools](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=v4%2Cwindows%2Ccsharp%2Cportal%2Cbash#install-the-azure-functions-core-tools)
* Install [Azure-cli](https://docs.microsoft.com/es-es/cli/azure/install-azure-cli)
* Cuanta de [GitHub](https://github.com/)
* Cuenta de [Giphy Developers](https://developers.giphy.com/)
* Cuenta de [Azure](https://azure.microsoft.com/en-us/)

## Pasos

* Creamos una nueva carpeta para el proyecto y entramos dentro

```sh
mkdir giphy
cd giphy
```

* Creamos un documento index.html

```sh
touch index.html
```

* Editamos el documento e introducimos un formulario con un input

```html
<html>
    <h1>Giphy Searcher</h1>
    <form action="">
        <input type="text">
        <button>
            Search
        </button>
    </form>
</html>
```

* Inicializamos el proyecto git y hacemos nuestro primer commit

```sh
git init
git add .
git commit -m "Primer commit"
```

* Lo subimos a GitHub

```sh
git push -u origin main
```

* Configuramos un APP Service de web estática con GitHub

⚠️ El profesor hace un ejemplo en la pizarra de como se ha de hacer.⚠️

* Importante tener en cuenta los "Valores preestablecidos de compilación" =>
  "Custom"
  * "Ubicación de la aplicación" => "/"
  * "Ubicación de la API" => "/api"
  * "Ubicación de salida" => "/"

* Descargamos las actualizaciones que ha hecho Azure en nuestro proyecto en
  local.

```sh
git pull
```

### Puede que nos salga una advertencia para configurar el pull por defecto

```sh
git config pull.rebase true
```

## Vamos a comprobar que todo es correcto

* Hacemos un cambio en la aplicación, Editando el index.html. Vamos a añadir una
  descripción de como funciona la aplicación.

```html
<h2>Gif Search es un buscador de gifs sobre la API de [GIPHY](https://giphy.com/)</h1>
```

* Volvemos a subir los cambios

```sh
git push
```

* En este punto esperamos a que Azure suba los cambios de forma automática.

## Azure Functions

⚠️ El profesor explica que es una API, como se desarrolla con azure functions y
como hacer pruebas en local⚠️

* Link de interés para esta parte del ejercicio: [Azure Functions JavaScript
  Command
  line](https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-cli-node?tabs=azure-cli%2Cbrowser)

* Crear la carpeta de funciones donde estarán definidas todas nuestras funciones
  API.

```sh
func init api --javascript
```

* Se habrá creado una carpeta con cierto contenido útil para Azure.

* Entramos dentro

```sh
cd api
```

* Crear la function API getGif.

```sh
func new --name getGif --template "HTTP trigger" --authlevel "anonymous"
```

* Ahora vamos a testearla en local.

```sh
func start
```

* Como podemos ver este comando levantará un servidor en local con el cual
  podemos testear nuestra API y nos ofrecerá un link al que acceder para hacer
  esta prueba. El link en cuestión acabará en `/api/getGif` Si hacemos click en
  el, se abrirá en el navegador una web con el siguiente resultado.

```html
This HTTP triggered function executed successfully. Pass a name in the query
string or in the request body for a personalized response.
```

⚠️ El profesor explica que es un parámetro URL y como funcionan las URLS.⚠️

* Por último podemos comprobar una funcionalidad extra añadiendo un parámetro a
  la URL de la siguiente forma `/api/getGif?name=jaime`. Deberíamos ver un
  mensaje como el siguiente

```html
Hello, jaime. This HTTP triggered function executed successfully.
```

## Deploy

⚠️ El profesor explica que es un deploy.⚠️

* Volvemos a la carpeta raíz del proyecto.

```sh
cd ..
```

* Hacemos un nuevo commit.

```sh
git add .
git commit -m "My function"
```

* Lo subimos al servidor.

```sh
git push
```

* En este punto esperamos a que Azure suba los cambios de forma automática.

* Auna vez pasado un tiempo prudencial deberemos comprobar que todo se ha
  aplicado correctamente.

  Para ello desde el panel de administración de Azure y en el apartado de
  nuestro aplicación de contenido estático accedemos a la configuración de
  Funciones, donde debería aparecer la función que acabamos de subir.

  Aviso, esta suele tardar unos segundos en aparecer.

* Una vez aparezca getGif en la lista de funciones sabremos que el deploy ha
  sido efectivo.

* Ahora vamos a comprobar que efectivamente nuestra función está ahí y funciona.
  Hemos de darle al botón de examinar y añadir al final de la ruta el siguiente
  path `/api/getGif` Debería salir un texto como el siguiente:

```html
This HTTP triggered function executed successfully. Pass a name in the query
string or in the request body for a personalized response.
```

* Al igual que en la comprobación local, vamos a comprobar que el resto de
  nuestra función es correcta accediendo a `/api/getGif?name=jaime`

* MUY BIEN! Ya tienes una web estática y una API funcionales. Ahora solo queda
  combinarlas.

## Combinar ambas funcionalidades ( Web Estática + Función )

⚠️ El profesor explica como funciona la API de GIPHY.⚠️

* Entramos en la carpeta api y probamos nuestra función en local.

* Pedimos a giphy nuestra API_KEY.

* Editamos la funcion getGif con el siguiente contenido:

```js

```

## Otros

* [Azure functions API Example](https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-cli-node?tabs=azure-cli%2Ccurl)

