---
title: 'İçeri Aktarma Bildirimleri: open Anahtar Sözcüğü (F#)'
description: 'F # içeri aktarma bildirimleri ve bunların nasıl bir modül veya ad alanı belirtin bir tam ad kullanmadan başvuru öğeleri öğrenin.'
ms.date: 05/16/2016
ms.openlocfilehash: 29f09297993b347464f1572ac9ca24902c786f4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563538"
---
# <a name="import-declarations-the-open-keyword"></a>İçeri aktarma bildirimleri: `open` anahtar sözcüğü

> [!NOTE]
Bu makalede API başvuru bağlantılar için MSDN götürür.  Docs.microsoft.com API Başvurusu tamamlanmadı.

Bir *bildirimi almak* bir modüle ya da öğeleri bir tam ad kullanmadan başvuru isim belirtir.


## <a name="syntax"></a>Sözdizimi

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Açıklamalar
Tam ad veya modülü yolunu kullanarak kod başvuran her yazma, okuma ve Bakım sabit kod oluşturabilirsiniz. Bunun yerine, kullanabileceğiniz `open` anahtar sözcüğü için sık kullanılan modülleri ve ad alanlarını böylece, modül veya ad alanı üyesi başvurduğunuzda tam adı yerine kısa formun adını kullanabilirsiniz. Bu anahtar sözcük benzer `using` C# anahtar sözcüğü `using namespace` Visual C++ ' ta ve `Imports` Visual Basic'te.

Modüle ya da sağlanan ad alanı aynı projede veya başvurulan proje ya da derleme olmalıdır. Değilse, projesine bir başvuru ekleyin, veya kullanın `-reference` komutu`-`satır seçeneği (ya da kendi kısaltmayı `-r`). Daha fazla bilgi için bkz: [derleyici seçenekleri](compiler-options.md).

Alma bildirimi adlarını kapsayan ad alanı, modül veya dosya sonuna kadar bildirimi aşağıdaki kodda kullanılabilir hale getirir.

Birden çok içeri aktarma bildirimleri kullandığınızda, ayrı satırlara görüntülenmesi gerekir.

Aşağıdaki kod kullanımı gösterilmiştir `open` kodu basitleştirmek için anahtar sözcüğü.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

Aynı adlı birden fazla açık modülü veya ad alanı oluştuğunda belirsizlikleri oluştuğunda F # derleyici bir hata veya uyarı yayma değil. Belirsizlikleri gerçekleştiğinde, F # tercih daha yakın zamanda açılan modülü veya ad alanı sağlar. Örneğin, aşağıdaki kodda, `empty` anlamına gelir `Seq.empty`rağmen `empty` ikisinde bulunan `List` ve `Seq` modüller.

```fsharp
open List
open Seq
printfn "%A" empty
```

Modülleri veya ad alanları gibi açtığınızda, bu nedenle dikkatli olun `List` veya `Seq` aynı adlara sahip; bunun yerine, tam ad kullanmayı deneyin üyeleri içerir. Kod içeri aktarma bildirimleri sırasını bağımlı olduğu tüm durumlarda kaçınmalısınız.


## <a name="namespaces-that-are-open-by-default"></a>Varsayılan olarak açık olan ad alanları
Bazı ad alanlarının, bunlar örtük olarak bir açık alma bildirimi gerek olmadan açıldığından F # kodunda çok sık kullanılır. Aşağıdaki tabloda, varsayılan olarak açık olan ad alanları gösterir.

|Ad Alanı|Açıklama|
|---------|-----------|
|`Microsoft.FSharp.Core`|Temel F # için tür tanımları yerleşik türleri gibi içeren `int` ve `float`.|
|`Microsoft.FSharp.Core.Operators`|Temel aritmetik işlemler gibi içeren `+` ve `*`.|
|`Microsoft.FSharp.Collections`|Değişmez koleksiyon sınıfları içerir `List` ve `Array`.|
|`Microsoft.FSharp.Control`|Denetim yapıları geç değerlendirme ve zaman uyumsuz iş akışları gibi türler içerir.|
|`Microsoft.FSharp.Text`|Biçimlendirilmiş g/ç için gibi işlevler içeren `printf` işlevi.|

## <a name="autoopen-attribute"></a>AutoOpen özniteliği
Uygulayabileceğiniz `AutoOpen` derleme başvurulduğunda bir ad alanı veya modülü otomatik olarak açmak istiyorsanız, bir derlemede özniteliği. Ayrıca uygulayabilirsiniz `AutoOpen` öznitelik üst modüle ya da ad alanı açıldığında otomatik olarak bu modülü açmak için bir modül. Daha fazla bilgi için bkz: [Core.AutoOpenAttribute sınıfı](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).


## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess özniteliği
Bazı modüller, kayıtları ya da birleşim türlerini belirtmek `RequireQualifiedAccess` özniteliği. Bu modüller, kayıtları veya birleşimler öğeleri başvuru yaptığınızda, bir içeri aktarma bildirimi içerip bağımsız olarak bir tam ad kullanmanız gerekir. Bu öznitelik stratejik üzerinde kullanıyorsanız, yaygın olarak tanımlayan türler kullanılan adları, ad çakışmaları önlemek ve böylece kodu daha esnektir kitaplıklarında değişiklikler yapmak yardımcı olur. Daha fazla bilgi için bkz: [Core.RequireQualifiedAccessAttribute sınıfı](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).


## <a name="see-also"></a>Ayrıca Bkz.
[# Dil Başvurusu](index.md)

[Ad Alanları](namespaces.md)

[Modüller](modules.md)

