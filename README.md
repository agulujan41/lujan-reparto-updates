# lujan-reparto-updates

Repo público de solo actualizaciones para la app Reparto Luján — **no tiene
código fuente**, solo sirve para que la app sepa si hay una versión más
nueva para instalar.

- `latest.json`: versión publicada actualmente (la app lo lee al abrir).
- `releases/`: los `.apk` de cada versión.

## Publicar una versión nueva

1. Compilar el release: `flutter build apk --release` (con el `version:` de
   `pubspec.yaml` ya subido, formato `X.Y.Z+N` — el `N` tiene que ser mayor
   al de la última vez).
2. Copiar el APK a `releases/app-release-X.Y.Z+N.apk` en este repo.
3. Editar `latest.json` con la versión, el `buildNumber` (el `N`) y la URL
   del nuevo archivo.
4. `git add . && git commit -m "..." && git push`.

Apenas se hace push, cualquier teléfono con una versión más vieja instalada
va a ver la pantalla de actualización obligatoria la próxima vez que abra
la app con internet.
