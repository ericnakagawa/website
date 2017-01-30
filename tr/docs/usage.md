* * *

id: docs_usage guide: docs_getting_started layout: guide additional_reading_tags: ["basics", "cli"]

* * *

{% include vars.html %}

Yarn'ı [yüklediğinize]({{url_base}}/docs/install) göre, kullanmaya başlayabilirsiniz. İhtiyacınız olacak yaygın komutların bazıları şunlar:

**Yeni bir projeye başlama**

```sh
yarn init
```

**Bir bağımlılık ekleme**

```sh
yarn upgrade [paket]
yarn upgrade [paket]@[versiyon]
yarn upgrade [paket]@[etiket]
```

**Bir bağımlılık güncelleme**

```sh
yarn upgrade [paket]
yarn upgrade [paket]@[versiyon]
yarn upgrade [paket]@[etiket]
```

**Bir bağımlılık silme**

```sh
yarn remove [paket]
```

**Projenin tüm bağımlılıklarını yükleme**

```sh
yarn
```

ya da

```sh
yarn install
```