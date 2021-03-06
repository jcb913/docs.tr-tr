---
title: Geri aramalar ve olayları
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90cc40024de627f151a4d0df879a65e5900004b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573639"
---
# <a name="events-and-callbacks"></a>Geri aramalar ve olayları
Geri aramalar kullanıcı kodu bir temsilci aracılığıyla geri çağırmak için bir çerçeve izin genişletilebilirlik noktalarıdır. Bu temsilci genellikle framework bir yöntemin parametre geçirildi.  
  
 (Bir olay işleyicisi) temsilci sağlama için uygun ve tutarlı sözdizimi destekleyen bir özel durum geri aramalar, olaylardır. Ayrıca, Visual Studio'nun deyim tamamlama ve tasarımcıları olay tabanlı API'lerini kullanarak Yardım sağlayabilir. (Bkz [olay tasarım](../../../docs/standard/design-guidelines/event.md).)  
  
 **✓ DÜŞÜNÜN** çerçevesi tarafından yürütülecek özel kod sağlamak için kullanıcıların izin vermek için geri çağırmaları kullanma.  
  
 **✓ DÜŞÜNÜN** framework nesne odaklı tasarım anlamak için gerek kalmadan davranışını özelleştirmek kullanıcıların olayları kullanarak.  
  
 **✓ YAPMAK** daha geniş bir grup geliştiriciler için tanıdık ve Visual Studio deyim tamamlama ile tümleşik olduğundan olayları düz geri aramalar tercih.  
  
 **KAÇININ x** geri aramalar performans duyarlı API'leri kullanarak.  
  
 **✓ YAPMAK** yeni `Func<...>`, `Action<...>`, veya `Expression<...>` API'leri ile geri aramalar tanımlarken özel temsilciler yerine türleri.  
  
 `Func<...>` ve `Action<...>` genel temsilciler temsil eder. `Expression<...>` derlenmiş ve daha sonra ancak çalışma zamanında da çağrılan temsil işlev tanımları sıralanabilir ve uzak işlemler geçirildi.  
  
 **✓ YAPMAK** ölçmek ve performans etkilerini kullanmanın `Expression<...>`, yerine `Func<...>` ve `Action<...>` temsilciler.  
  
 `Expression<...>` türleridir çoğu durumda mantıksal olarak eşdeğer `Func<...>` ve `Action<...>` temsilciler. Bunlar arasındaki temel fark temsilcileri yerel işlem senaryolarda kullanılması amaçlanmıştır olan; ifadeler faydalı ve uzak işlem veya makine ifadesinde değerlendirmek mümkün olduğu durumlarda yöneliktir.  
  
 **✓ YAPMAK** temsilci çağırarak rastgele kod yürütülmekte olduğunu anlamak ve güvenlik, doğruluk ve uyumluluk varsa sahip olabilir.  
  
 *Bölümleri © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*  
  
 *Pearson eğitim, Inc. şirketinin izni tarafından yeniden yazdırılmaları [Framework tasarım yönergeleri: kuralları, deyimleri ve yeniden kullanılabilir .NET kitaplıkları, 2 sürümü için desenleri](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams tarafından 22 Eki 2008 tarafından yayımlanan Microsoft Windows geliştirme serisi bir parçası olarak Addison-Wesley Professional.*  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilebilirlik için Tasarlama](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Çerçeve Tasarım Yönergeleri](../../../docs/standard/design-guidelines/index.md)
