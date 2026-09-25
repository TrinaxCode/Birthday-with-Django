# Cumpleaños con Django

Una página sencilla hecha con Django que cambia su mensaje según la fecha del servidor. El 14 de octubre muestra el saludo de cumpleaños; los demás días invita a volver en esa fecha. La página incluye videos y música servidos como archivos estáticos.

## Requisitos

- Python 3 y `pip`
- Git

## Ejecutar localmente

```bash
git clone https://github.com/TrinaxCode/Birthday-with-Django.git
cd Birthday-with-Django
python3 -m venv .venv
source .venv/bin/activate       # Windows PowerShell: .venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Abre <http://127.0.0.1:8000/>. La música se reproduce después de pulsar el botón, según las reglas de reproducción del navegador.

## Cómo funciona

La vista principal compara la fecha actual del servidor con el 14 de octubre y pasa el resultado a la plantilla `Felizcumple/index.html`. Los estilos, videos y pistas de audio están en `Felizcumple/static/`.

## Despliegue

El repositorio incluye un `Procfile` para iniciar Django con Gunicorn. Antes de desplegar, configura `SECRET_KEY` mediante una variable de entorno, desactiva `DEBUG` y ajusta `ALLOWED_HOSTS` para el dominio de producción. No uses la configuración de desarrollo como configuración de producción.
