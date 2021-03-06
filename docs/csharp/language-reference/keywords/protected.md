---
title: protected (C# Başvurusu)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: a3115fe82b452f52ee75cf222302ece0fc67b330
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269576"
---
# <a name="protected-c-reference"></a>protected (C# Başvurusu)
`protected` Sözcüktür üye erişim değiştiricisi. 

 > Bu sayfayı kapsayan `protected` erişim. `protected` Sözcüktür ayrıca parçası [ `protected internal` ](./protected-internal.md) ve [ `private protected` ](./private-protected.md) erişim değiştiricileri. 

Korumalı üye kendi sınıfı içinde ve türetilen sınıf örnekleri tarafından erişilebilir. 

Bir karşılaştırması `protected` diğer erişim değiştiricileri ile bkz [erişilebilirlik düzeyleri](../../../csharp/language-reference/keywords/accessibility-levels.md). 
  
## <a name="example"></a>Örnek  
 Yalnızca erişim üzerinden türetilmiş sınıf türü oluşuyorsa korumalı bir temel sınıf üyesi türetilen bir sınıfta erişilebilir. Örneğin, aşağıdaki kod kesimi göz önünde bulundurun:  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 Deyim `a.x = 10` ana statik yöntemi içinde oluşturulur ve b sınıf örneği değil çünkü bir hata oluşturur  
  
 Yapı üyeleri yapısı devraldığından korunamaz.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, sınıf `DerivedPoint` türetildiği `Point`. Bu nedenle, doğrudan türetilmiş sınıftan temel sınıfın korumalı üyeleri erişebilir.  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 Erişim düzeyleri değiştirirseniz `x` ve `y` için [özel](../../../csharp/language-reference/keywords/private.md), derleyici hata iletileri verecek:  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a>C# Dil Belirtimi  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# başvurusu](../../../csharp/language-reference/index.md)  
 [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
 [C# Anahtar Sözcükleri](../../../csharp/language-reference/keywords/index.md)  
 [Erişim Değiştiricileri](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [Erişilebilirlik Düzeyleri](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [Değiştiriciler](../../../csharp/language-reference/keywords/modifiers.md)  
 [public](../../../csharp/language-reference/keywords/public.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)  
 [İç sanal anahtar ile ilgili güvenlik konuları](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))