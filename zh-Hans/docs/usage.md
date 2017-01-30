* * *

id: docs_usage guide: docs_getting_started layout: guide additional_reading_tags: ["basics", "cli"]

* * *

{% include vars.html %}

Now that you have Yarn [installed]({{url_base}}/docs/install), you can start using Yarn. Here are some of the most common commands you'll need.

**开始新项目**

```sh
yarn init
```

**添加依赖包**

```sh
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
```

**升级依赖包**

```sh
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```

**移除依赖包**

```sh
yarn remove [package]
```

**安装项目的全部依赖**

```sh
yarn
```

或者

```sh
yarn install
```