---
title: "Nasıl yapılır: Dosyalar, Klasörler ve Sürücüler Hakkında Bilgi Alma (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d5652dda53a0192ce39be497b6e8ad3c97bef042
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a>Nasıl yapılır: Dosyalar, Klasörler ve Sürücüler Hakkında Bilgi Alma (C# Programlama Kılavuzu)
.NET Framework'teki aşağıdaki sınıflar kullanarak dosya sistemi bilgileri erişebilirsiniz:  
  
-   <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
-   <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
-   <xref:System.IO.Directory?displayProperty=nameWithType>  
  
-   <xref:System.IO.File?displayProperty=nameWithType>  
  
 <xref:System.IO.FileInfo> Ve <xref:System.IO.DirectoryInfo> sınıfları bir dosya veya dizin temsil eder ve NTFS dosya sistemi tarafından desteklenen dosya öznitelikleri çoğunu kullanıma özellikler içerir. Bunlar ayrıca açma, kapatma, taşıma ve dosya ve klasörleri silme yöntemlerini içerir. Oluşturucuya dosya, klasör veya sürücüde adını temsil eden bir dize geçirerek bu sınıfların örnekleri oluşturabilirsiniz:  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 Dosyalar, klasörler veya sürücüler adlarını çağrıları kullanarak edinebilirsiniz <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType>, ve <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.  
  
 <xref:System.IO.Directory?displayProperty=nameWithType> Ve <xref:System.IO.File?displayProperty=nameWithType> sınıfları dizinler ve dosyalar hakkında bilgi almak için statik yöntemler sağlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, dosya ve klasörleri hakkındaki bilgilere erişmek için çeşitli yollar gösterir.  
  
 [!code-csharp[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Kullanıcı tanımlı yol dizeleri işlerken, aşağıdaki koşullar için özel durumları işler:  
  
-   Dosya adı yanlış biçimlendirilmiş. Örneğin, geçersiz karakterler veya yalnızca boşluk içeriyor.  
  
-   Dosya adı null.  
  
-   Dosya adı sistem tarafından tanımlanan uzunluk üst sınırından daha uzun.  
  
-   Dosya adında iki nokta üst üste (:) içerir.  
  
 Uygulamayı belirtilen dosyasını okumak için yeterli izinlere sahip değilse `Exists` yöntemi döndürür `false` bakılmaksızın bir yolu var olup; yöntemi bir özel durum değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IO?displayProperty=nameWithType>  
 [C# programlama kılavuzu](../../../csharp/programming-guide/index.md)  
 [Dosya sistemi ve kayıt defteri (C# programlama Kılavuzu)](../../../csharp/programming-guide/file-system/index.md)