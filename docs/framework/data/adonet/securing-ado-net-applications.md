---
title: ADO.NET uygulamalarının güvenliğini sağlama
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: efe25082b4e4de9170179ebeff6a1dca8f67446c
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728608"
---
# <a name="securing-adonet-applications"></a>ADO.NET uygulamalarının güvenliğini sağlama
Güvenli bir ADO.NET uygulama yazma birden fazla kullanıcı girişini doğrulama değil gibi ortak kodlama Tuzaklar önleme içerir. Verilere erişen bir uygulama birçok olası bir saldırganın alınamıyor, değiştirmek veya hassas verilere zarar yararlanabilir hata noktalarını sahiptir. Bu nedenle, güvenlik, uygulamanızın son dağıtım ve devam eden bakım tasarım aşamasında modelleme tehdit işleminden tüm yönlerini anlamak önemlidir.  
  
 .NET Framework pek çok yararlı sınıfları, hizmetleri ve güvenli hale getirme ve veritabanı uygulamaları yönetmek için araçlar sağlar. Ortak dil çalışma zamanı (CLR), daha fazla yönetilen kod izinlerini kısıtlamak için kod erişimi güvenliği ile (CA) çalıştırmak için kod için bir tür kullanımı uyumlu ortamı sağlar. Güvenli veri yöntemler kodlama erişim olası bir saldırgan tarafından şiddet hasarı kısıtlar.  
  
 Güvenli kod yazmaya karşı kendi kendine inflicted güvenlik açıklarını veritabanları gibi yönetilmeyen kaynaklar ile çalışırken koruma sağlamaz. SQL Server gibi birçok server veritabanlarını düzgün şekilde uygulandığında güvenliğini kendi güvenlik sistemlerinde vardır. Ancak, uygun şekilde yapılandırılmamışsa, daha güçlü bir güvenlik sistemi ile bir veri kaynağı bir saldırı kurban.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Güvenliğe Genel Bakış](../../../../docs/framework/data/adonet/security-overview.md)  
 Güvenli ADO.NET uygulamalar tasarlama için öneriler sağlar.  
  
 [Güvenli Veri Erişimi](../../../../docs/framework/data/adonet/secure-data-access.md)  
 Güvenli veri kaynağı ile nasıl çalışılacağını açıklar.  
  
 [Güvenli İstemci Uygulamaları](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 İstemci uygulamaları için güvenlik konuları açıklanmaktadır.  
  
 [Kod Erişimi Güvenliği ve ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md)  
 CA'ları ADO.NET kodu korumaya nasıl yardımcı olabileceğini açıklar. Ayrıca kısmi güven ile çalışma konusunda anlatılmaktadır.  
  
 [Gizlilik ve Veri Güvenliği](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 ADO.NET uygulamalar için şifreleme seçenekleri açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [SQL Server Güvenliği](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 SQL Server güvenlik özellikleri geliştiricinin açısından açıklar.  
  
 [Güvenlik Konuları](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 Entity Framework uygulamaları için güvenliği açıklar.  
  
 [Güvenlik](../../../../docs/standard/security/index.md)  
 .NET ve güvenlik tüm yönlerini açıklayan konulara bağlantılar içerir.  
  
 [Güvenlik araçları](http://msdn.microsoft.com/library/2a3eb98a-2de6-4fba-b41c-01a74d354c11)  
 Güvenlik İlkesi'ni yönetme ve güvenliğini sağlamak için .NET framework Araçları'nı tıklatın.  
  
 [Güvenli uygulamalar oluşturmak için kaynaklar](http://msdn.microsoft.com/library/0ebf5f69-76f2-498a-a2df-83cf3443e132)  
 Güvenli uygulamalar oluşturmak için konulara bağlantılar sağlar.  
  
 [Güvenlik Kaynakçası](/visualstudio/ide/security-bibliography)  
 Çevrimiçi ve yazdırma kullanılabilir dış kaynaklara bağlantılar sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
