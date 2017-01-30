* * *

id: docs_usage guide: docs_getting_started layout: guide additional_reading_tags: ["basics", "cli"]

* * *

{% include vars.html %}

עכשיו לאחר שהתקנת את Yarn, אתה מוזמן להתחיל להשתמש בו. למטה מוצגות כמה מן הפקודות הנפוצות ביותר שבהן אפשר להשתמש.

**פתיחת פרויקט חדש**

```sh
yarn init
```

**הוספת חבילה**

```sh
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
```

**עדכון חבילה**

```sh
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```

**הסרת חבילה**

```sh
yarn remove [package]
```

**התקנת כל החבילות של הפרויקט**

```sh
yarn
```

או

```sh
yarn install
```