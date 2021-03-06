---
title: DotNet command - .NET Core CLI yayımlama
description: Dotnet yayımlama komutu .NET Core projenizi bir dizine yayımlar.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 38224aa8472f99df107e523667e18892384a20b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696666"
---
# <a name="dotnet-publish"></a>DotNet yayımlama

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Ad

`dotnet publish` -Dağıtım barındırma sistem için bir klasöre uygulamayı ve bağımlılıklarını paketler.

## <a name="synopsis"></a>Özet

# <a name="net-core-21tabnetcore21"></a>[.NET core 2.1](#tab/netcore21)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[.NET core 2.0](#tab/netcore20)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET core 1.x](#tab/netcore1x)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```
---

## <a name="description"></a>Açıklama

`dotnet publish` Uygulama derler, proje dosyasında belirtilen bağımlılıklarını aracılığıyla okur ve bir dizine dosyaları sonuç kümesini yayımlar. Çıktı şu varlıkları içerir:

* Ara dil (IL) ile bir derlemeyi kodda bir *dll* uzantısı.
* *. deps.json* tüm proje bağımlılıklarını içeren dosya.
* *. runtime.config.json* çalışma zamanı (örneğin, atık toplama türü) için diğer yapılandırma seçeneklerini yanı sıra uygulama bekler paylaşılan çalışma zamanı belirten dosyası.
* Uygulama bağımlılıkları, NuGet önbellekten çıkış klasörüne kopyalanır.

`dotnet publish` Komutunun çıktısını, dağıtım için bir barındırma sistemi hazır (örneğin, bir sunucu, PC, Mac, dizüstü) yürütme için. Bu uygulama dağıtım için hazırlamak için yalnızca resmi olarak desteklenen yoludur. Projeyi belirtir. Dağıtım türü, bağlı olarak ana bilgisayar sistemi olabilir veya .NET Core üzerinde yüklü çalışma zamanı paylaşılmayan sahip. Daha fazla bilgi için bkz: [.NET Core uygulama dağıtımı](../deploying/index.md). Yayımlanmış bir uygulama dizin yapısı için bkz: [dizin yapısını](/aspnet/core/hosting/directory-structure).

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Arguments

`PROJECT`

Yayımlanacak projeyi. Belirtilmezse, geçerli dizine varsayılan olur.

## <a name="options"></a>Seçenekler

# <a name="net-core-21tabnetcore21"></a>[.NET core 2.1](#tab/netcore21)

`-c|--configuration {Debug|Release}`

Derleme yapılandırması tanımlar. Varsayılan değer `Debug` şeklindedir.

`-f|--framework <FRAMEWORK>`

Uygulama için belirtilen yayımlar [hedef framework](../../standard/frameworks.md). Proje dosyasında hedef Framework'ü belirtmeniz gerekir.

`--force`

Son geri yükleme başarılı olsa bile çözümlenmesi için tüm bağımlılıkları zorlar. Bu bayrak belirten aynıdır silme *project.assets.json* dosya.

`-h|--help`

Komutu için kısa bir Yardım yazdırır.

`--manifest <PATH_TO_MANIFEST_FILE>`

Bir veya birkaç belirtir [hedef bildirimleri](../deploying/runtime-store.md) uygulamayla yayımlanan paket kümesini kırpma için kullanılacak. Bildirim dosyası çıkışını bir parçasıdır [ `dotnet store` komutu](dotnet-store.md). Birden çok bildirimleri belirtmek için ekleyin bir `--manifest` her bildirimi için seçeneği. Bu seçenek, .NET Core 2.0 SDK'sı ile başlayarak kullanılabilir.

`--no-build`

Yayımlamadan önce projeyi derlemek değil. Ayrıca örtük ayarlar `--no-restore` bayrağı.

`--no-dependencies`

Proje Proje başvuruları yoksayar ve yalnızca kök proje geri yükler.

`--no-restore`

Örtük bir geri yükleme komutu çalıştırırken yürütmez.

`-o|--output <OUTPUT_DIRECTORY>`

Çıktı dizini yolunu belirtir. Belirtilmezse, varsayılan olarak *./bin/[configuration]/[framework]/publish/* framework bağımlı dağıtım için veya *./bin/[configuration]/[framework]/[runtime]/publish/* için bir kendi içinde bulunan dağıtım.
Göreli yol ise, oluşturulan çıktı dizini proje dosya konumu, geçerli çalışma dizini için görelidir.

`--self-contained`

Çalışma zamanı hedef makinede yüklü olması gerekmez için uygulamanızın ile .NET çekirdeği çalışma zamanı yayımlar. Bir çalışma zamanı tanıtıcı belirtilirse, varsayılan değeri olduğu `true`. Farklı dağıtım türleri hakkında daha fazla bilgi için bkz: [.NET Core uygulama dağıtımı](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Uygulama için belirli bir çalışma zamanı yayımlar. Bu oluşturulurken kullanılan bir [müstakil dağıtım (SCD)](../deploying/index.md#self-contained-deployments-scd). Çalışma zamanı tanımlayıcıları (RID) bir listesi için bkz: [RID katalog](../rid-catalog.md). Varsayılan değer yayımlamak için bir [framework bağımlı dağıtım (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).

`-v|--verbosity <LEVEL>`

Komutun ayrıntı düzeyi ayarlar. İzin verilen değerler `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, ve `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Yıldız işareti değiştirmek için Sürüm soneki tanımlar (`*`) proje dosyasının sürüm alanında.

# <a name="net-core-20tabnetcore20"></a>[.NET core 2.0](#tab/netcore20)

`-c|--configuration {Debug|Release}`

Derleme yapılandırması tanımlar. Varsayılan değer `Debug` şeklindedir.

`-f|--framework <FRAMEWORK>`

Uygulama için belirtilen yayımlar [hedef framework](../../standard/frameworks.md). Proje dosyasında hedef Framework'ü belirtmeniz gerekir.

`--force`

Son geri yükleme başarılı olsa bile çözümlenmesi için tüm bağımlılıkları zorlar. Bu bayrak belirten aynıdır silme *project.assets.json* dosya.

`-h|--help`

Komutu için kısa bir Yardım yazdırır.

`--manifest <PATH_TO_MANIFEST_FILE>`

Bir veya birkaç belirtir [hedef bildirimleri](../deploying/runtime-store.md) uygulamayla yayımlanan paket kümesini kırpma için kullanılacak. Bildirim dosyası çıkışını bir parçasıdır [ `dotnet store` komutu](dotnet-store.md). Birden çok bildirimleri belirtmek için ekleyin bir `--manifest` her bildirimi için seçeneği. Bu seçenek, .NET Core 2.0 SDK'sı ile başlayarak kullanılabilir.

`--no-dependencies`

Proje Proje başvuruları yoksayar ve yalnızca kök proje geri yükler.

`--no-restore`

Örtük bir geri yükleme komutu çalıştırırken yürütmez.

`-o|--output <OUTPUT_DIRECTORY>`

Çıktı dizini yolunu belirtir. Belirtilmezse, varsayılan olarak *./bin/[configuration]/[framework]/publish/* framework bağımlı dağıtım için veya *./bin/[configuration]/[framework]/[runtime]/publish/* için bir kendi içinde bulunan dağıtım.
Göreli yol ise, oluşturulan çıktı dizini proje dosya konumu, geçerli çalışma dizini için görelidir.

`--self-contained`

Çalışma zamanı hedef makinede yüklü olması gerekmez için uygulamanızın ile .NET çekirdeği çalışma zamanı yayımlar. Bir çalışma zamanı tanıtıcı belirtilirse, varsayılan değeri olduğu `true`. Farklı dağıtım türleri hakkında daha fazla bilgi için bkz: [.NET Core uygulama dağıtımı](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Uygulama için belirli bir çalışma zamanı yayımlar. Bu oluşturulurken kullanılan bir [müstakil dağıtım (SCD)](../deploying/index.md#self-contained-deployments-scd). Çalışma zamanı tanımlayıcıları (RID) bir listesi için bkz: [RID katalog](../rid-catalog.md). Varsayılan değer yayımlamak için bir [framework bağımlı dağıtım (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).

`-v|--verbosity <LEVEL>`

Komutun ayrıntı düzeyi ayarlar. İzin verilen değerler `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, ve `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Yıldız işareti değiştirmek için Sürüm soneki tanımlar (`*`) proje dosyasının sürüm alanında.

# <a name="net-core-1xtabnetcore1x"></a>[.NET core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Derleme yapılandırması tanımlar. Varsayılan değer `Debug` şeklindedir.

`-f|--framework <FRAMEWORK>`

Uygulama için belirtilen yayımlar [hedef framework](../../standard/frameworks.md). Proje dosyasında hedef Framework'ü belirtmeniz gerekir.

`-h|--help`

Komutu için kısa bir Yardım yazdırır.

`--manifest <PATH_TO_MANIFEST_FILE>`

Bir veya birkaç belirtir [hedef bildirimleri](../deploying/runtime-store.md) uygulamayla yayımlanan paket kümesini kırpma için kullanılacak. Bildirim dosyası çıkışını bir parçasıdır [ `dotnet store` komutu](dotnet-store.md). Birden çok bildirimleri belirtmek için ekleyin bir `--manifest` her bildirimi için seçeneği. Bu seçenek, .NET Core 2.0 SDK'sı ile başlayarak kullanılabilir.

`-o|--output <OUTPUT_DIRECTORY>`

Çıktı dizini yolunu belirtir. Belirtilmezse, varsayılan olarak *./bin/[configuration]/[framework]/publish/* framework bağımlı dağıtım için veya *./bin/[configuration]/[framework]/[runtime]/publish/* için bir kendi içinde bulunan dağıtım.
Göreli yol ise, oluşturulan çıktı dizini proje dosya konumu, geçerli çalışma dizini için görelidir.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Uygulama için belirli bir çalışma zamanı yayımlar. Bu oluşturulurken kullanılan bir [müstakil dağıtım (SCD)](../deploying/index.md#self-contained-deployments-scd). Çalışma zamanı tanımlayıcıları (RID) bir listesi için bkz: [RID katalog](../rid-catalog.md). Varsayılan değer yayımlamak için bir [framework bağımlı dağıtım (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).

`-v|--verbosity <LEVEL>`

Komutun ayrıntı düzeyi ayarlar. İzin verilen değerler `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, ve `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Yıldız işareti değiştirmek için Sürüm soneki tanımlar (`*`) proje dosyasının sürüm alanında.

---

## <a name="examples"></a>Örnekler

Proje geçerli dizinde yayımlayın:

`dotnet publish`

Belirtilen proje dosyası kullanarak uygulama yayımlama:

`dotnet publish ~/projects/app1/app1.csproj`

Geçerli bir dizin içinde proje yayımlama `netcoreapp1.1` framework:

`dotnet publish --framework netcoreapp1.1`

Geçerli kullanarak uygulamayı yayımlamak `netcoreapp1.1` framework ve Çalışma Zamanı Modülü `OS X 10.10` (proje dosyasında bu RID listelemeniz gerekir).

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

Geçerli uygulamayı yayımlamak, ancak proje proje (P2P) başvuruları, yalnızca kök proje (.NET Core SDK 2.0 ve sonraki sürümler) geri yükleme işlemi sırasında geri yüklemeyin:

`dotnet publish --no-dependencies`

## <a name="see-also"></a>Ayrıca bkz.

* [Hedef çerçeveler](../../standard/frameworks.md)
* [Çalışma zamanı tanımlayıcı (RID) Kataloğu](../rid-catalog.md)
