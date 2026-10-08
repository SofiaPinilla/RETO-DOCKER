# Reto: informe de notas con Python y Docker

## Equipos

| Grupo | Integrantes |
| --- | --- |
| 1 | JOAQUIN_VILLALOBOS (MDIA) · IGNACIO-PINAZO (MDIA) · RICARDO_ROMAN (MDES) |
| 2 | FRAN_ALAPONT (MDIA) · LUCAS_OSEJO (MDIA) · RAUL_FERRIS (MDES) |
| 3 | RAFA_BROTONS (MDIA) · HUGO_GAVILAN (MDIA) · JAIME_SANFELIX (MDES) |
| 4 | ADRIAN_LAZARO (MDIA) · CHRISTIAN_VAZQUEZ (MDIA) · IGNACIO_IBÁÑEZ-RIZO (MDES) |
| 5 | JORGE_DURA (MDIA) · LOLA_BONET (MDIA) · NICO_GOMEZ (MDES) |
| 6 | MANOLO_TORTAJADA (MDIA) · ANGEL_CARLOS_PEREZ (MDIA) · ANTONIO_NAVARRO (MDES) |
| 7 | OSCAR_HERREROS (MDIA) · INGRID (MDIA) · CARLOS_GUTIERREZ (MDES) |
| 8 | ANDRES_GIMENO (MDIA) · Laura Soler Úbeda (MDIA) · MARIO_GONZALEZ (MDES) |
| 9 | ALEJANDRO-CERVERA (MDIA) · JUANJO_PRADES (MDIA) · DAVID_GALLART (MDES) |
| 10 | LORENZO_SABBATINI (MDIA) · JADE_LOPEZ (MDIA) · JORGE_OLIVER (MDIA) |
| 11 | JAVIER_MARTINEZ (MDIA) · PABLO_LEGORBURO (MDIA) |
| 12 | PABLO_CUNAT (MDIA) · Jana Mei Cervera Monzó (MDIA) |

## El problema

Preparad un programa que analice las notas de un grupo y muestre un informe por consola. Los datos estarán escritos en el código: **no utilicéis `input()` ni un menú**.

## Datos de partida

```python
alumnos = [
    {"nombre": "Ana", "nota": 8.5},
    {"nombre": "Luis", "nota": 4.0},
    {"nombre": "Marta", "nota": 7.0},
    {"nombre": "Pablo", "nota": 3.5},
    {"nombre": "Sara", "nota": 9.0},
]
```

## Qué debe hacer

1. Recorrer la lista con un `for`.
2. Mostrar el nombre en mayúsculas, su nota y si está aprobado o suspendido. Se aprueba con una nota mayor o igual a 5.
3. Contar cuántos alumnos hay, cuántos aprueban y cuántos suspenden.
4. Calcular la media del grupo y redondearla a dos decimales.
5. Mostrar un resumen con esos cuatro resultados.

Cread una función `calcular_media(alumnos)` que reciba la lista y devuelva la media. Si la lista está vacía, debe devolver `0`. Añadid una docstring.

Guardad el programa en `notas.py`. Los datos de este reto son números entre 0 y 10; no hace falta pedir datos ni validar otros tipos.

## Pruebas

| Datos | Resultado esperado |
| --- | --- |
| Lista inicial | 5 alumnos, 3 aprobados, 2 suspendidos, media `6.4` |
| Una persona con nota `5.0` | 1 aprobado, 0 suspendidos, media `5.0` |
| Lista vacía | 0 alumnos, 0 aprobados, 0 suspendidos, media `0` |

Para probar otros casos, cambiad la lista en el código. No hace falta que los decimales tengan siempre dos cifras.

## Dockerización

Escribid un `Dockerfile`, sin extensión, que:

- Parta de una imagen de Python, por ejemplo `python:3.12-slim`.
- Defina una carpeta de trabajo con `WORKDIR`.
- Copie `notas.py` con `COPY`.
- Configure con `CMD` la ejecución del programa.

Construid la imagen desde la carpeta del proyecto:

```bash
docker build -t informe-notas .
```

Ejecutadla:

```bash
docker run --rm informe-notas
```

El programa debe mostrar el informe y terminar. Si cambiáis el código o los datos, reconstruid la imagen antes de probarla de nuevo.

## Entrega

Cread un repositorio de GitHub por equipo con las ramas **`main` y `develop`**.

- Trabajad los cambios en `develop`.
- Cread al menos una **pull request de `develop` a `main`** con una descripción de los cambios.
- Otro integrante del equipo debe revisar la pull request antes de fusionarla.
- Fusionadla para que la entrega final esté en `main` y mantened también la rama `develop`.
- Incluid en el README el enlace a la pull request realizada.

El repositorio debe contener:

- `notas.py`.
- `Dockerfile`.
- `README.md` con integrantes, comandos para construir y ejecutar, resultados de las pruebas y respuestas breves:
  1. ¿Cómo habéis usado la lista y los diccionarios?
  2. ¿Cómo decidís quién aprueba y quién suspende?
  3. ¿Qué recibe y devuelve vuestra función?
  4. ¿Cómo evitáis dividir entre cero si la lista está vacía?
  5. ¿Qué hace cada instrucción del Dockerfile?

Enviad el enlace a **scpinilla@edem.es** con el asunto `Reto notas Python y Docker — Grupo XX`. Aseguraos de que la profesora pueda acceder.
