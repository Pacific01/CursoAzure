# Giphy Search

> Aplicación para buscar gifs en la API de giphy y levantarlo con Azure, usando
> Azure functions como BackEnd.

## Requisitos

* [Git-scm](https://git-scm.com/)
* Install Azure Functions
* Install Azure-cli
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

* Descargamos las actualizaciones que ha hecho Azure en nuestro proyecto en
  local.

```sh
git pull
```

### Puede que nos salga una advertencia para configurar el pull por defecto

```sh
git config pull.rebase true
```

## Vamos a comprobar que todo es correcto.

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

⚠️ El profesor hace un ejemplo en la pizarra de como se ha de hacer.⚠️

- Link de interés para esta parte del ejercicio: [Azure Functions JavaScript Command line](https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-cli-node?tabs=azure-cli%2Cbrowser)

* Crear la carpeta de funciones aka api

```sh
func init api --javascript
```

* Se habrá creado una carpeta con cierto contenido útil para Azure.

* Entramos dentro

```sh
cd api
```

* Crear la function
* Conectar la App Service Static to the function

## Otros

* [Azure functions API Example](https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-cli-node?tabs=azure-cli%2Ccurl)

