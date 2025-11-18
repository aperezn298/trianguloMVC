# Triángulo MVC — Microaplicación Flask

Pequeña aplicación demostrativa que sigue el patrón MVC (Modelo-Vista-Controlador) para calcular
el área y perímetro de un triángulo. Está pensada como material educativo para ver separación
de responsabilidades: el modelo contiene la lógica matemática, la vista es una plantilla HTML
con Bootstrap y el controlador es el servidor Flask.

## Estructura del proyecto

- `app.py` — Controlador principal (Flask). Maneja la ruta `/` y procesa el formulario.
- `models/triangulo.py` — Lógica del modelo: funciones para área y perímetro.
- `templates/triangulo.html` — Plantilla Jinja2 con formulario y presentación de resultados.
- `static/css/estilos.css` — Estilos personalizados (acompaña a Bootstrap).

## Requisitos

Este microproyecto solo necesita `Flask` para ejecutarse. Desde la raíz del directorio `triangulo_mvc`
puedes crear un entorno virtual e instalar Flask:

Windows PowerShell:
```
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install flask
```

Linux / macOS:
```
python3 -m venv .venv
source .venv/bin/activate
pip install flask
```

Si integras esta microapp en un proyecto con `requirements.txt`, añade `Flask` allí.

## Ejecutar localmente

Desde el directorio `triangulo_mvc` y con el entorno virtual activado:

```
python app.py
```

Abre el navegador en `http://127.0.0.1:5000/` y verás el formulario para ingresar la base, altura y lados.

## Uso

- Completa los campos `Base`, `Altura`, `Lado 1` y `Lado 2`.
- Pulsa `Calcular`.
- La página mostrará el área y el perímetro calculados.


## Código relevante

- `models/triangulo.py` contiene:
  - `calcular_area(base, altura)`
  - `calcular_perimetro(base, lado1, lado2)`
  - `calcular_triangulo(base, altura, lado1, lado2)` — función de alto nivel que devuelve `(area, perimetro)`.

- `app.py` muestra el patrón clásico:
  - GET: renderiza el formulario vacío.
  - POST: valida y parsea los floats, llama al modelo y pasa el resultado a la plantilla.


## Despliegue

Puedes desplegar esta microapp en servicios como Render, Heroku o cualquier PaaS que soporte Flask.
Usa `gunicorn` para producción. Ejemplo de comando de inicio:

```
gunicorn app:app --bind 0.0.0.0:$PORT
```

## Autor
AperezN — material educativo / ejemplo didáctico.