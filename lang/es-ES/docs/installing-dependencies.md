* * *

id: docs_installing_dependencies guide: docs_yarn_workflow layout: guide additional_reading_tags: ["dependencies", "package-json", "yarn-lock", "cli-install"]

* * *

Si has solicitado un paquete para modificación del [control de versión](./version-control), tendrás que instalar esas dependencias.

> Si estas [añadiendo dependencias](./managing-dependencies#toc-adding-a-dependency) para tu proyecto, esas dependencias son automáticamente instaladas durante el proceso.

### Instalando dependencias [](#toc-installing-dependencies){#toc-installing-dependencies.toc}

Para instalar todas las dependencias de un proyecto se usa [`yarn install`](./cli/install). Las dependencias son solicitadas del archivo `package.json` de tu proyecto, y son guardadas en el archivo `yarn.lock`.

Cuando estas desarrollando un paquete, la instalación de las dependencias se hace comúnmente después de:

  1. Has solicitado para modificación un código para un proyecto que esta creando un paquete.
  2. Otro desarrollador del proyecto ha añadido una nueva dependencia que tú necesitas.

### Opciones de instalación [](#toc-installing-options){#toc-installing-options.toc}

Hay muchas opciones para instalar dependencias, incluyendo:

  1. Instalando todas las dependencias: `yarn` o `yarn install`
  2. Instalando una y sólo una versión de un paquete: `yarn install --flat`
  3. Forzando un nueva descarga de todos los paquetes: `yarn install --force`
  4. Instalando solo dependencias de producción: `yarn install --production`

Revisa [la lista completa](./cli/install) de opciones que puedes pasarle a `yarn install`.