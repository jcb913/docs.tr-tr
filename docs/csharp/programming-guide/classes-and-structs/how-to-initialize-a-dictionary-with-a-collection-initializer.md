---
title: 'Nasıl yapılır: Koleksiyon Başlatıcısı ile bir Sözlük Başlatma (C# Programlama Kılavuzu)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: b8c44ebbdc89d72398c3380d708b45d0b7dfdad3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324180"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Nasıl yapılır: Koleksiyon Başlatıcısı ile bir Sözlük Başlatma (C# Programlama Kılavuzu)
A <xref:System.Collections.Generic.Dictionary`2> anahtar/değer çiftleri koleksiyonu içerir. Kendi <xref:System.Collections.Generic.Dictionary`2.Add*> yöntemi iki parametre, bir anahtar ve değer için bir alır. Başlatmak için bir <xref:System.Collections.Generic.Dictionary`2>, ya da herhangi bir koleksiyonu olan `Add` yöntemi birden çok parametre alır, aşağıdaki örnekte gösterildiği gibi her parametrelerinin ayraçlar içinde alın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde, bir <xref:System.Collections.Generic.Dictionary`2> türü örnekleri ile başlatılmış `StudentName`.  
  
 [!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]  
  
 Her öğe koleksiyonunun ayraç iki çiftlerini unutmayın. Nesne Başlatıcısı en içteki köşeli parantez içine `StudentName`, ve Başlatıcı eklenecek anahtar/değer çifti için en dıştaki köşeli parantez içine `students` <xref:System.Collections.Generic.Dictionary`2>. Son olarak, tüm koleksiyon Başlatıcısı sözlüğü için ayraç içine alınır.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kodu çalıştırmak için kopyalayın ve Visual Studio'da oluşturulan bir Visual C# konsol uygulaması projesi sınıfı yapıştırın. Varsayılan olarak, bu proje 3.5 sürümünü hedefler [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], ve System.Core.dll ve kullanarak bir başvuru içeriyor System.Linq yönergesi. Bir veya daha fazla bu gereksinimleri projeden eksikse, bunları el ile ekleyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
 [Nesne ve Koleksiyon Başlatıcıları](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
