# 🏕️ Predicciones del Campamento

Juego web para jugar **en vivo** con el público. Una sola persona (el presentador) maneja la computadora; el resto dice en voz alta sus predicciones y el presentador las carga.

## Cómo jugar

1. **Elegir pregunta**  
   En el desplegable elegís la pregunta (choclo, remeras, distancia, Mercado Pago, camas, Instagram, alarma).

2. **Cargar predicciones**  
   El público va diciendo nombre + número (o hora). Vós los vas cargando: nombre y predicción, y tocás **Agregar**. Podés sumar varios.

3. **Revelar**  
   Cuando sepan la respuesta real, la cargás en “Respuesta correcta” (o usás un archivo de respuestas) y tocás **Revelar** o **ESPACIO**. Gana quien estuvo más cerca (en números: diferencia absoluta; en hora: diferencia en minutos).

4. **Siguiente ronda**  
   Cambiás de pregunta en el desplegable y se vacía la lista para la siguiente.

## Proyección (pantalla grande)

- Las **preguntas** y el texto principal están en tamaño grande para que el público vea bien desde lejos.
- **Ocultar controles:** tocá **“Ocultar controles”** antes de proyectar. Así el público solo ve la pregunta, el cartel “Predicción en curso” y el botón **Revelar**. No se ven el desplegable, la lista de predicciones ni el cuadro donde se escribe la respuesta correcta. Para volver a cargar predicciones o cambiar la respuesta, tocá **“Mostrar controles”**.

## Respuestas desde respuestas.json

Podés cargar las respuestas correctas desde un archivo JSON y no tipearlas en pantalla:

1. Usá el archivo de ejemplo `respuestas.json` (o creá uno igual).
2. En el juego, tocá **“Cargar respuestas desde archivo”** y elegí el archivo.
3. Al revelar, si hay una respuesta para esa pregunta en el archivo, se usa esa; si no, se usa lo que esté escrito en el cuadro “Respuesta correcta”.

Formato de `respuestas.json`: las claves son el número de pregunta (0 a 6) y el valor es la respuesta en texto (número o hora como `"07:30"`).

```json
{
  "0": "500",
  "1": "3",
  "2": "2.5",
  "3": "15000",
  "4": "20",
  "5": "42",
  "6": "07:30"
}
```

## Cómo correr el juego (local)

### Recomendado: servidor local (respuestas automáticas)
Desde la carpeta del proyecto:

```bash
# Con Python 3
python3 -m http.server 8000

# O con Node (npx)
npx serve .
```

Entrá en el navegador a **http://localhost:8000**. Así `respuestas.json` se carga solo y no tenés que hacer nada más.

### Alternativa: abrir el archivo directo
Abrí `index.html` con doble clic. Funciona, pero tendrás que usar **"Cargar respuestas.json"** una vez para elegir el archivo (el navegador no puede leerlo automáticamente).

## Preguntas incluidas

- ¿Cuánto sale un choclo de la playa?
- ¿Cuántas remeras trajo … al campamento?
- ¿Cuánta distancia (km) caminando hay del predio a Iglesia del Salvador?
- ¿Cuánta plata tiene en Mercado Pago …?
- ¿Cuántas camas tiene el predio?
- ¿Cuántos posteos en Instagram tiene …?
- ¿A qué hora tiene seteada la alarma …?

Los "…" son para reemplazar con el nombre de la persona cuando lo digan en vivo.

---

Diseño pensado para proyectar o usar en una pantalla; solo el presentador necesita tocar la compu.
