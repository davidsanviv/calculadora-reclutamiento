# Calculadora de costo de contratar (PyMEs LATAM)

Página estática de solo consulta. Países: México, Colombia, Chile, Argentina, Guatemala.
No guarda ni envía datos del usuario.

## Estructura
- `index.html`: interfaz y lógica de cálculo. Cambia poco.
- `data/paises.json`: **todos los supuestos** (salarios, cargas sociales, tarifas, fuentes). Aquí se actualiza.
- `CHANGELOG.md`: qué cambió y cuándo.

## Actualizar supuestos
1. Edita `data/paises.json`.
2. Anota el cambio en `CHANGELOG.md` y sube `version` y `actualizado` en el JSON.
3. `git commit` y `git push`. Si el hosting está conectado al repo, se publica solo.
4. Para marcar una versión: `git tag v1.1.0 && git push --tags`.

## Probar en local
El navegador bloquea `fetch` desde `file://`; usa un servidor local:

    python3 -m http.server 8000

y abre http://localhost:8000

## Estados de dato (`st` en el JSON)
`src` con fuente · `weak` fuente débil · `est` estimado · `none` sin dato (valor 0, el usuario lo captura).
