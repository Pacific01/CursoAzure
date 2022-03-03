# Giphy Search

> Aplicación para buscar gifs en la API de giphy y levantarlo con Azure, usando
> Azure functions como BackEnd.

## Requisitos

* [Git-scm](https://git-scm.com/)
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

⚠️ El profesor hace un ejemplo en la pizzara de como se ha de hacer.⚠️

* Descargamos las actualizaciones

```sh
git pull
```

### Puede que ons salga una adevtencia para configurar el pull por defecto:

```
git config pull.rebase true
```

* Hacemos un cambio en la aplicación, Editando el index.html. Vamos a añadir una
  descripión de como funciona la aplicación.

* Volvemos a subir los cambios

```sh
git push
```

* En este punto esperamos a que Azure suba los cambios de forma automática.
