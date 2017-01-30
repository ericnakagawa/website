* * *

id: docs_managing_dependencies guide: docs_yarn_workflow layout: guide additional_reading_tags: ["dependencies", "package-json", "yarn-lock", "cli-add", "cli-upgrade", "cli-remove"]

* * *

{% include vars.html %}

Cuando quieres agregar, actualizar o eliminar dependencias, existen varios comandos que necesitas saber.

Cada comando actualizará automáticamente los archivos [`package.json`]({{url_base}}/docs/package-json) y [`yarn.lock`]({{url_base}}/docs/yarn-lock).

### Agregando una dependencia [](#toc-adding-a-dependency){#toc-adding-a-dependency.toc}

Si quieres utilizar otro paquete, primero debes agregarlo como dependencia. Para ello debes ejecutar:

```sh
yarn add [package]
```

Esto agregará automáticamente `[package]` a tus dependencias en tu `package.json`. También actualizará tu `yarn.lock` para reflejar el cambio.

```diff
  {
    "name": "my-package",
    "dependencies": {
+     "package-1": "^1.0.0"
    }
  }
```

También puedes agregar otros [tipos de dependencias]({{url_base}}/docs/dependency-types) usando los parámetros:

- `yarn add --dev` para agregar a `devDependencies`
- `yarn add --peer` para agregar a `peerDependencies`
- `yarn add --optional` para agregar a `optionalDependencies`

Puedes especificar la versión de un paquete que deseas instalar especificando una [versión de la dependencia]({{url_base}}/docs/dependency-versions) o una [etiqueta]({{url_base}}/docs/cli/tag).

```sh
yarn add [package]@[version]
yarn add [package]@[tag]
```

La `[version]` o `[tag]` será lo que se ha añadido a tu `package.json` y serán resueltas cuando la dependencia sea instalada.

Por ejemplo:

```sh
yarn add package-1@1.2.3
yarn add package-2@^1.0.0
yarn add package-3@beta
```

```json
{
  "dependencies": {
    "package-1": "1.2.3",
    "package-2": "^1.0.0",
    "package-3": "beta"
  }
}
```

### Actualizando una dependencia [](#toc-upgrading-a-dependency){#toc-upgrading-a-dependency.toc}

```sh
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```

Esto actualizará tu `package.json` y el archivo `yarn.lock`.

```diff
  {
    "name": "my-package",
    "dependencies": {
-     "package-1": "^1.0.0"
+     "package-1": "^2.0.0"
    }
  }
```

### Eliminando una dependencia [](#toc-removing-a-dependency){#toc-removing-a-dependency.toc}

```sh
yarn remove [package]
```

Esto actualizará tu `package.json` y el archivo `yarn.lock`.