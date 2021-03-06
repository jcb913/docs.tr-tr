---
title: 'Nasıl yapılır: Numaralandırma için Yeni bir Yöntem Oluşturma (C# Programlama Kılavuzu)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 8de44cbddf26af45245709d0e28d2d157256ce59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33313039"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>Nasıl yapılır: Numaralandırma için Yeni bir Yöntem Oluşturma (C# Programlama Kılavuzu)
Belirli numaralandırma türü için özel işlevsellik eklemek için genişletme yöntemleri kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `Grades` numaralandırma öğrencinin bir sınıfta alabilirsiniz olası harf dereceleri temsil eder. Adlı bir genişletme yöntemi `Passing` eklenen `Grades` türü artık her örneği bilir"veya değil, geçirme düzeyde temsil edip etmediğini böylece" yazın.  
  
 [!code-csharp[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 Unutmayın `Extensions` sınıfı ayrıca dinamik olarak güncelleştirilen bir statik değişken içerir ve uzantı yönteminin dönüş değeri bu değişkenin geçerli değeri yansıtır. Bu arka planda tanımlı doğrudan statik sınıf üzerinde genişletme yöntemleri çağrılır, gösterir.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kodu çalıştırmak için kopyalayın ve Visual Studio'da oluşturulan bir Visual C# konsol uygulaması projesi yapıştırın. Varsayılan olarak, bu proje 3.5 sürümünü hedefler [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], ve System.Core.dll bir başvuru içeriyor ve bir `using` System.Linq yönergesi. Bir veya daha fazla bu gereksinimleri projeden eksikse, bunları el ile ekleyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
 [Genişletme Yöntemleri](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
