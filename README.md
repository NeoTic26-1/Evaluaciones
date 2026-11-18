# Evaluaciones en línea

Página para que el docente cree evaluaciones por sección y las califique, y para que los alumnos las rindan desde el celular o la computadora y descarguen su evaluación en Word.

- `index.html`: la página completa.
- `firebase-config.js`: los datos de conexión a tu proyecto de Firebase.
- `firestore.rules`: las reglas de acceso para pegar en Firestore.

## Puesta en marcha

1. En Firebase (https://console.firebase.google.com) crea un proyecto y, dentro, una base de datos **Firestore**.
2. En **Firestore → Reglas**, reemplaza el contenido por el de `firestore.rules` y toca **Publicar**.
3. En **Configuración del proyecto → Tus apps**, agrega una **app web** y copia sus datos en `firebase-config.js`.
4. En GitHub, **Settings → Pages**: elige la rama `main` y la carpeta `/ (root)`.

La clave inicial del docente es `12345`. Cámbiala en la pestaña **Clave** la primera vez que entres.

## A tener en cuenta

- Cada evaluación se borra automáticamente, con sus entregas y fotos, 30 días después de su hora de cierre. El borrado ocurre cuando el docente abre la página. Los alumnos ven hasta qué fecha pueden descargar su Word. Para cambiar los días, edita `RET_DAYS` en `index.html`.
- Eliminar una evaluación a mano también borra sus entregas, notas y fotos.

- Las reglas permiten leer y escribir a cualquiera que abra la página. La clave del docente y las reglas del examen se revisan dentro de la página, así que alguien con conocimientos técnicos podría saltárselas.
- El plan gratuito de Firestore alcanza para un curso normal: 1 GB guardado, 50 000 lecturas y 20 000 escrituras por día.
