# tm-my-image-model

Modelo de clasificación de imágenes entrenado con Google Teachable Machine y exportado en formato TensorFlow.js. El modelo utiliza imágenes de 224 × 224 píxeles y devuelve una probabilidad para cada clase.

## Clases

El modelo exportado conserva las etiquetas `Class 1`, `Class 2` y `Class 3`.

## Archivos

| Archivo | Contenido |
| --- | --- |
| `model.json` | Arquitectura del modelo y referencia al archivo de pesos. |
| `weights.bin` | Pesos aprendidos durante el entrenamiento. |
| `metadata.json` | Etiquetas de las clases y configuración de entrada. |

## Uso en una página web

Coloca `model.json`, `weights.bin` y `metadata.json` en la misma carpeta y sírvelos por HTTP o HTTPS. Si ya tienes el código HTML que ofrece Teachable Machine al exportar, ajusta la ruta base para que apunte a esa carpeta.

Por ejemplo, si la página y los archivos del modelo se sirven desde el mismo directorio, puedes cargar el modelo así después de incluir TensorFlow.js y `@teachablemachine/image`:

```js
const modelo = await tmImage.load('./model.json', './metadata.json');
```

Luego puedes llamar a `modelo.predict(imagen)` con un elemento de imagen, vídeo o canvas para obtener las probabilidades por clase.
