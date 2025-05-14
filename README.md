# API con Flask - Dockerizada para Heroku

Una API REST que devuelve la IP del cliente y una suma sencilla, con soporte CORS y despliegue automatizado mediante Docker y GitHub Actions en Heroku.

## Instalación de dependencias

```
pip install -r requirements.txt
```

## Ejecutar la aplicación localmente

```
python app.py
```

## Endpoints disponibles

- `GET /`: Página de inicio, muestra un mensaje indicando que la API está funcionando.
- `GET /api/hello`: Devuelve un JSON con la IP del cliente y una suma sencilla.

## Pruebas locales

Puedes probar la API de las siguientes maneras:

1. **Navegador web**: Abre http://localhost:5000/api/hello
2. **Postman**: Realiza una petición GET a http://localhost:5000/api/hello
3. **Curl**: Ejecuta `curl http://localhost:5000/api/hello`

El soporte CORS está habilitado, por lo que puedes consumir esta API desde cualquier origen.

## Despliegue con Heroku

Esta aplicación está configurada para ser desplegada en Heroku. El archivo `Procfile` indica a Heroku cómo ejecutar la aplicación utilizando gunicorn como servidor web.

## Configuración de Docker

El proyecto incluye un `Dockerfile` que permite containerizar la aplicación para su despliegue. La imagen Docker está configurada para usar las variables de entorno que proporciona Heroku.

## Automatización con GitHub Actions

El flujo de trabajo de CI/CD está configurado en `.github/workflows/heroku-deploy.yml`. Este proceso automatiza:

1. La construcción de la imagen Docker
2. El envío de la imagen al registro de contenedores de Heroku
3. El despliegue de la aplicación en Heroku

### Configuración de secretos para GitHub Actions

Para que el despliegue automático funcione, debes configurar los siguientes secretos en tu repositorio de GitHub:

- `HEROKU_API_KEY`: Tu API key de Heroku
- `HEROKU_EMAIL`: La dirección de correo electrónico asociada a tu cuenta de Heroku
- `HEROKU_APP_NAME`: El nombre de tu aplicación en Heroku

## Flujo de trabajo

1. Haces push a la rama principal (main/master) de tu repositorio
2. GitHub Actions detecta el push y ejecuta el workflow
3. Se construye la imagen Docker con tu aplicación
4. La imagen se envía al registro de Heroku
5. La aplicación se despliega automáticamente en Heroku
