* * *

id: docs_dependency_versions guide: docs_dependencies description: docs_dependency_versions_description layout: guide

* * *

## Versionamento semântico [](#toc-semantic-versioning){#toc-semantic-versioning.toc}

Pacotes em fio sigam [Versionamento semântico](http://semver.org/), também conhecido como "semver". Quando você instala um novo pacote no seu registro, ele ira para seu arquivo `package.json` com o alcance da versão semver.

Essas versões são quebradas em `major.minor.patch` e se parecem com um desses: `3.14.1`, `0.42.0`, `2.7.18`. Cada parte da versão é incrementada em vários momentos:

- Incremente `importante` quando você faz uma **quebra** ou **incompatible** quando alterar a API de um pacote.
- Incremento `minor` quando você adicionar **novas funcionalidades** mantendo-se **compatível**
- Incremente `minor` quando você adicionar **novas funcionalidades** mantendo-se **compatível**

> **Nota:** Por vezes, há também "rótulos" ou "extensões" para o formato de semver que marcam coisas como versões pré-lançamento ou betas (por exemplo, `2.0.0-beta.3`)

Quando os desenvolvedores falam sobre duas versões de semver sendo "compatível" com o outro eles estão se referindo às mudanças **compatível** (`minor` e `patch`).

## Alcance de versão [](#toc-version-ranges){#toc-version-ranges.toc}

Quando você quer especificar uma dependência, especifique o nome e o **alcance de versnao** no seu arquivo `package.json` como um desses:

```json
{
  "dependencies": {
    "package-1": ">=2.0.0 <3.1.4",
    "package-2": "^0.4.2",
    "package-3": "~2.7.1"
  }
}
```

Você irá notar que temos um monte de caracteres separado da versão. Esses caracteres, `>=`, `<`, `^`, e `~`, são **operadores** e são usados para especificar o **alcance da versão**.

O propósito de uma gama de versão é para especificar quais versões de uma dependência irão trabalhar no seu código.

#### Comparadores [](#toc-comparators){#toc-comparators.toc}

Cada alcance de versão é composto de **comparadores**. Estes comparadores são simplesmente um *operador* seguido por uma *versão*. Aqui estão alguns dos operadores básicos:

| Comparador   | Descrição                                                 |
| ------------ | --------------------------------------------------------- |
| `<2.0.0`  | Qualquer versão que seja ***menor que*** `2.0.0`          |
| `<=3.1.4` | Qualquer versão que seja ***menor ou igual que*** `3.1.4` |
| `>0.4.2`  | Qualquer versão que seja ***maior que*** `0.4.2`          |
| `>=2.7.1` | Qualquer versão que seja ***maior ou igual a*** `2.7.1`   |
| `=4.6.6`     | Qualquer versão que seja ***igual a*** `4.6.6`            |

> **Nota**: se nenhum operador for especificado, então presume-se o alcance de versão `=`. Então, o operador de `=` é efetivamente opcional.

#### Interseções [](#toc-intersections){#toc-intersections.toc}

Comparadores podem ser unidos por espaço em branco para criar um **conjunto de comparador**. Isso cria uma **interseção** entre os comparadores inclusos. Por exemplo, o comparador `> = 2.0.0 < 3.1.4` significa *"Maior que ou igual a `2.0.0` **e** inferior a `3.1.4"`*.

#### Junções [](#toc-unions){#toc-unions.toc}

Uma alcance de versão completo inclui uma **união** de vários conjuntos de comparador unidas por `||`. Se ambos os lados da União são satisfeito, então o alcance inteiro versão é satisfeito. Por exemplo, o alcance de comparação `> = 2.0.0 < 3.1.4` significa *"Maior que ou igual a `2.0.0` **e** inferior a `3.1.4"`*.

#### Tags de pré-lançamento [](#toc-pre-release-tags){#toc-pre-release-tags.toc}

Versões também podem ter **tags de pré-lançamento** (ex. `3.1.4-beta.2`). Se um comparador inclui uma versão com um tag de pré-lançamento, corresponderá somente as versões que têm a mesma versão de `major.minor.patch`.

Por exemplo, o intervalo `> = 3.1.4-beta.2` corresponderia a `3.1.4-beta.2` ou `3.1.4-beta.12`, mas *não*corresponderia a `3.1.5-beta.1`, mesmo que seja *tecnicamente* "maior que ou igual a" (`> =`) a versão de `3.1.4-beta.2`.

Pré-lançamentos tendem a conter alterações que quebram o pacote, e normalmente você não quer corresponder com pré-lançamentos fora da versão que você especificou, então esse comportamento é útil.

#### Versões avançadas de alcance [](#toc-advanced-version-ranges){#toc-advanced-version-ranges.toc}

##### Intervalos de Hífen [](#toc-hyphen-ranges){#toc-hyphen-ranges.toc}

Intervalos de hífen (ex. `2.0.0 - 3.1.4`) especificam um conjunto *inclusivo*. Se parte da versão é deixado de fora (ex. `0,4` ou `2`), eles são preenchidos com zeros.

| Alcance de versão | Versões avançadas de alcance |
| ----------------- | ---------------------------- |
| `2.0.0 - 3.1.4`   | `>=2.0.0 <=3.1.4`      |
| `0.4 - 2`         | `>=0.4.0 <=2.0.0`      |

##### Alcance-X [](#toc-x-ranges){#toc-x-ranges.toc}

Qualquer um desses, `X`, `x` ou `*`, pode ser usado para deixar parte ou toda uma versão não especificada.

| Alcance de versão | Versões avançadas de alcance                           |
| ----------------- | ------------------------------------------------------ |
| `*`               | `>=0.0.0` (any version)                             |
| `2.x`             | `>=2.0.0 <3.0.0` (match major version)           |
| `3.1.x`           | `>=3.1.0 <3.2.0` (match major and minor version) |

Se parte de uma versão é omitido, presume-se ser uma x-gama.

| Alcance de versão | Versões avançadas de alcance      |
| ----------------- | --------------------------------- |
| `` (empty string) | `*` or `>=0.0.0`               |
| `2`               | `2.x.x` or `>=2.0.0 <3.0.0` |
| `3.1`             | `3.1.x` or `>=3.1.0 <3.2.0` |

##### Alcande de til(~)[](#toc-tilde-ranges){#toc-tilde-ranges.toc}

Usar `~` com uma versão secundária especificada permite alterações de `patch`. Usar `~` com versão única especificada permitirá mudanças `menores`.

| Alcance de versão | Versões avançadas de alcance      |
| ----------------- | --------------------------------- |
| `~3.1.4`          | `>=3.1.4 <3.2.0`            |
| `~3.1`            | `3.1.x` or `>=3.1.0 <3.2.0` |
| `~3`              | `3.x` or `>=3.0.0 <4.0.0`   |

> **Nota:** Especificar pré-lançamentos em alcances de til corresponderá somente pré-lançamentos na mesma versão completa. Por exemplo, o alcance de versão `~3.1.4-beta.2` corresponderia contra `3.1.4-beta.4` mas não `3.1.5-beta.2` porque a versão `major.minor.patch` é diferente.

##### Intervalos de circunflexo [](#toc-caret-ranges){#toc-caret-ranges.toc}

Permite alterações que não modificam o primeiro dígito diferente de zero na versão, como o o `3` em `3.1.4` ou o `4` em `0.4.2`.

| Alcance de versão | Versões avançadas de alcance |
| ----------------- | ---------------------------- |
| `^3.1.4`          | `>=3.1.4 <4.0.0`       |
| `^0.4.2`          | `>=0.4.2 <0.5.0`       |
| `^0.0.2`          | `>=0.0.2 <0.0.3`       |

> **Nota:** Por padrão quando você executa `yarn add [package-name]` ele usará um alcance de acento circunflexo.

Se parte da versão é deixado de fora, as partes que faltam são preenchidas com zeros. No entanto, ainda permitirá que o valor seja alterado.

| Alcance de versão | Versões avançadas de alcance |
| ----------------- | ---------------------------- |
| `^0.0.x`          | `>=0.0.0 <0.1.0`       |
| `^0.0`            | `>=0.0.0 <0.1.0`       |
| `^0.x`            | `>=0.0.0 <1.0.0`       |
| `^0`              | `>=0.0.0 <1.0.0`       |

### Mais recursos [](#toc-more-resources){#toc-more-resources.toc}

- Para uma especificação completa de como funciona esse sistema de controle de versão, consulte o [README do`node-semver`](https://github.com/npm/node-semver).
- Teste este sistema de controle de versão em pacotes usando o [npm semver calculator](https://semver.npmjs.com/).