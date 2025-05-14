# API Hola Mundo con Flask

Una simple API REST que devuelve un mensaje "Hola mundo" con soporte CORS.

## Instalación de dependencias

```
pip install -r requirements.txt
```

## Ejecutar la aplicación

```
python app.py
```

## Endpoints disponibles

- `GET /`: Página de inicio, muestra un mensaje indicando que la API está funcionando.
- `GET /api/hello`: Devuelve un JSON con el mensaje "Hola mundo".

## Pruebas

Puedes probar la API de las siguientes maneras:

1. **Navegador web**: Abre http://localhost:5000/api/hello
2. **Postman**: Realiza una petición GET a http://localhost:5000/api/hello
3. **Curl**: Ejecuta `curl http://localhost:5000/api/hello`

El soporte CORS está habilitado, por lo que puedes consumir esta API desde cualquier origen.
