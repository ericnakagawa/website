* * *

id: docs_cli_check guide: docs_cli layout: guide

* * *

##### `yarn check` [](#toc-yarn-check){#toc-yarn-check.toc}

Verifies that versions of the package dependencies in the current project's `package.json` matches that of yarn's lock file.

##### `yarn check --integrity` [](#toc-yarn-check-integrity){#toc-yarn-check-integrity.toc}

Verifies that versions and hashed value of the package contents in the project's `package.json` matches that of yarn's lock file. This helps to verify that the package dependencies have not been altered.