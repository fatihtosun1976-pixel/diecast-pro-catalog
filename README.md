# DieCast Pro Catalog

DieCast Pro uygulaması için statik katalog deposu.

Bu depo, uygulamanın ücretli arama veya OCR API'lerine ihtiyaç duymadan katalog verisi ve katalog görsellerini indirebilmesi için hazırlanmıştır.

## Yapı

```text
catalog_version.json
hotwheels/
  sth/
    <yıl>/
      sth.json
      image_manifest.json
      images/
        <parça-kodu>.jpg
```

## Kullanım

Uygulama önce `catalog_version.json` dosyasını kontrol eder. İlgili yıl için tanımlanan `sth.json` dosyasını indirir ve model kayıtlarındaki göreli `image` yollarını kullanır.

Ana sürüm dosyası:

```text
https://raw.githubusercontent.com/fatihtosun1976-pixel/diecast-pro-catalog/main/catalog_version.json
```

## Katalog türü

`STH_ONLY` — Mattel / Hot Wheels. Yıllar ve kayıt sayıları `catalog_version.json` içinden okunur.

## Görsel bütünlüğü

Her yılın `image_manifest.json` dosyasında dosya adı, byte boyutu ve SHA-256 özeti tutulur. Yayınlama aracı push öncesinde bunları yerel dosyalarla karşılaştırır.

## Güncelleme akışı

Katalog oluşturulduktan sonra:

```text
C:\DCP\CATALOG_MANAGER_V1\PUBLISH_TO_GITHUB.cmd
```

çalıştırılır. Araç JSON ve görselleri doğrular, yerel yol sızıntısını kontrol eder, Git değişikliklerini gösterir ve kullanıcı onayından sonra commit/push yapar.

## Görsel hakları

`imageRights: user_managed` alanı, görsel kullanım ve yeniden dağıtım haklarının depo sahibi tarafından yönetildiğini belirtir. Bu depo üçüncü taraf görseller için otomatik lisans iddiasında bulunmaz.

## DieCast Pro

Bu depo uygulama kodundan ayrıdır. Amaç katalog güncellemelerinin yeni APK yayımlamadan dağıtılabilmesidir.
