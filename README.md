# Clasificador de prensa

Web estática para anotar noticias sobre violencias, delito, seguridad, justicia y legislación penal, con anclaje argentino. Investigación de Escuela IDAES – UNSAM.

## Uso

Abrir la web desde el celular o la computadora. En el menú del navegador se puede agregar un acceso a la pantalla de inicio. Cuatro decisiones: **Sí, entra**, **Fuera del tema**, **Fuera de Argentina**, **Tengo dudas**. Empezar por el test de validación sin consultar predicciones. Las teclas 1, 2, 3 y 0 hacen lo mismo; z deshace la última decisión.

El avance se guarda en este navegador. Para continuar en otro dispositivo, descargar el respaldo JSON e importarlo en el otro. Las anotaciones no se envían a GitHub ni a una API. Descargar respaldos periódicamente antes de borrar datos del navegador. El menú permite importar también los JSON del clasificador HTML anterior; ignora filas ajenas a las muestras vigentes y conserva la decisión más reciente.

Luego de una primera apertura completa con conexión, el service worker guarda la aplicación y la muestra para usarlas sin red. No se requiere mantener encendida la computadora del proyecto.

## Muestra y criterio

Versión `2015-2025-20261113-v1`: 400 tareas de validación, idénticas a las de octubre, y 1.467 de entrenamiento; solo se retiró una nota de 2011 del entrenamiento. No se volvieron a sortear ni renumerar las restantes. Los conjuntos son disjuntos por la identidad canónica del proyecto. No incluye predicciones de modelos ni puntajes del lexicón.

El universo del que se preparan nuevas muestras está recortado a fechas registradas entre 2015 y 2025. Los títulos se reconstruyen del slug del enlace y se identifican como tales; los fragmentos son los mismos de las muestras originales. Cada tarea conserva el enlace al medio. La definición operacional completa está incluida en el menú. Los textos periodísticos pertenecen a sus respectivos medios y se muestran como fragmentos para su análisis académico.

## Desarrollo

HTML, CSS y JavaScript, sin dependencias ni claves. `dataset.json` contiene exclusivamente las tareas y el criterio. GitHub Pages publica la rama `main`, directorio raíz. Para probar localmente: `python3 -m http.server 4183`, abrir la dirección que corresponda. Las pruebas locales de Chromium verifican decisiones, deshacer, persistencia tras recarga, importación/exportación, lectura móvil y disponibilidad offline.

## Instalar como app (PWA)

En el menú de la web, **Instalar como app** abre el diálogo del navegador cuando está disponible. Si todavía no lo ofrece, el botón muestra los pasos para Android/Chrome y iPhone/Safari. En Android: menú de Chrome → Agregar a pantalla principal → Instalar. En iPhone: Compartir en Safari → Agregar a pantalla de inicio; dejar activado Abrir como app web cuando aparezca. Abrir después desde el ícono del clasificador.

El manifiesto incluye identidad y scope del proyecto, ventana standalone, íconos PNG de 192 y 512, variante maskable y apple-touch-icon. Los íconos se generaron desde el favicon SVG propio del proyecto. Se conserva la misma clave de localStorage, la misma muestra y el mismo formato de respaldo. En iPhone Safari y la app tienen guardado separado: exportar primero lo anotado en Safari e importarlo en la app si se empezó a clasificar antes de instalarla.
