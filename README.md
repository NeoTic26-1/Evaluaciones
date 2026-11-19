# Test de Laboratorios UNI-FIIS

Página para que el docente cree evaluaciones por sección y las califique, y para que los alumnos las rindan desde el celular o la computadora y descarguen su evaluación en Word.

- `index.html`: la página completa.
- `firebase-config.example.js`: modelo de la configuración de Firebase. El archivo real, `firebase-config.js`, no se guarda en el repositorio: se genera al publicar con la clave del secreto `FIREBASE_API_KEY`.
- `.github/workflows/pages.yml`: publica la página en GitHub Pages en cada cambio.
- `firestore.rules`: las reglas de acceso para pegar en Firestore.

## Puesta en marcha

1. En Firebase (https://console.firebase.google.com) crea un proyecto y, dentro, una base de datos **Firestore**.
2. En **Firestore → Reglas**, reemplaza el contenido por el de `firestore.rules` y toca **Publicar**.
3. En **Configuración del proyecto → Tus apps**, agrega una **app web**. Si cambias de proyecto, actualiza los datos de `firebase-config.example.js` (todo menos la clave).
4. En GitHub, **Settings → Secrets and variables → Actions → New repository secret**: nombre `FIREBASE_API_KEY`, valor la clave de API (restringida al sitio `https://neotic26-1.github.io/*` y a Cloud Firestore API).
5. En GitHub, **Settings → Pages → Source: GitHub Actions**.

La clave inicial del docente es `12345`. Cámbiala en la pestaña **Clave** la primera vez que entres.

## A tener en cuenta

- Cada evaluación se borra automáticamente, con sus entregas y fotos, 30 días después de su hora de cierre (`MAX_DAYS` en `index.html`). El borrado ocurre cuando el docente abre la página, que además muestra el espacio usado aproximado. Los alumnos ven hasta qué fecha pueden descargar su Word.
- Eliminar una evaluación a mano también borra sus entregas, notas y fotos.

- Las reglas permiten leer y escribir a cualquiera que abra la página. La clave del docente y las reglas del examen se revisan dentro de la página, así que alguien con conocimientos técnicos podría saltárselas.
- El plan gratuito de Firestore alcanza para un curso normal: 1 GB guardado, 50 000 lecturas y 20 000 escrituras por día.
