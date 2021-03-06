---
title: 'Nasıl yapılır: yapma modeli ve eşleme dosyaları katıştırılmış kaynakları'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 3fd3c3628e94b4727dfc711e02a9f4b754aa8a2c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756351"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Nasıl yapılır: yapma modeli ve eşleme dosyaları katıştırılmış kaynakları
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] , Modeli ve eşleme dosyaları uygulamanın gömülü kaynaklar dağıtmanıza olanak tanır. Varlık bağlantısı aynı uygulama etki alanında katıştırılmış modeli ve eşleme dosyaları içeren derlemenin yüklü olması gerekir. Daha fazla bilgi için bkz: [bağlantı dizeleri](../../../../../docs/framework/data/adonet/ef/connection-strings.md). Varsayılan olarak, [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] araçları katıştırmak modeli ve eşleme dosyaları. Model ve eşleme dosyaları el ile tanımladığınızda, dosyaları ile birlikte gömülü kaynaklar olarak dağıtıldığından emin olmak için bu yordamı kullanın bir [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] uygulama.  
  
> [!NOTE]
>  Katıştırılmış kaynakları korumak için model ve eşleme dosyaları değiştirdiğinde bu yordamı yineleyin gerekir.  
  
### <a name="to-embed-model-and-mapping-files"></a>Model ve eşleme dosyaları eklemek için  
  
1.  İçinde **Çözüm Gezgini**, kavramsal (.csdl) dosyasını seçin.  
  
2.  İçinde **özellikleri** kümesi bölmesi, **yapı eylemi** için **katıştırılmış kaynak**.  
  
3.  Depolama (.ssdl) dosyası ve eşleme (.msl) dosyası için 1 ve 2. adımları yineleyin.  
  
4.  İçinde **Çözüm Gezgini**, App.config dosyasına çift tıklayın ve ardından değiştirme `Metadata` parametresinde `connectionString` özniteliği aşağıdaki biçimlerden birini temel alarak:  
  
    -   `Metadata=``res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=``res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     Daha fazla bilgi için bkz: [bağlantı dizeleri](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki bağlantı dizesi başvuran katıştırılmış modeli ve eşleme dosyaları için [AdventureWorks satış modeli](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). Bu bağlantı dizesi projenin App.config dosyasında depolanır.  
  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Modelleme ve Eşleme](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [Nasıl yapılır: Bağlantı Dizesi Tanımlama](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)  
 [Nasıl yapılır: Bir EntityConnection Bağlantı Dizesi Oluşturma](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
 [ADO.NET varlık veri modeli araçları](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
