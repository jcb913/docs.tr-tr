---
title: 'Nasıl yapılır: RefType sonuçları döndüren bir sorgu yürütme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dbbfbcd-93f5-4546-9dbf-e5fa290b69fa
ms.openlocfilehash: 53741b8f2c22f8f20ba3a318218fe518b736d1ac
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760667"
---
# <a name="how-to-execute-a-query-that-returns-reftype-results"></a>Nasıl yapılır: RefType sonuçları döndüren bir sorgu yürütme
Bu konuda kullanarak kavramsal model karşı komut yürütme gösterilmiştir bir <xref:System.Data.EntityClient.EntityCommand> nesne ve nasıl alınacağını <xref:System.Data.Metadata.Edm.RefType> kullanarak sonuçları bir <xref:System.Data.EntityClient.EntityDataReader>.  
  
### <a name="to-run-the-code-in-this-example"></a>Bu örnekte kodu çalıştırmak için  
  
1.  Ekleme [AdventureWorks satış modeli](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) projenize ve kullanmak için projenizin yapılandırma [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: Varlık veri modeli Sihirbazı'nı](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Uygulamanız için kod sayfasında aşağıdakileri ekleyin `using` deyimleri (`Imports` Visual Basic'te):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Örnek  
 Bu örnek döndüren bir sorgu yürütür <xref:System.Data.Metadata.Edm.RefType> sonuçları. Bağımsız değişken olarak aşağıdaki sorguyu geçirdiğiniz `ExectueRefTypeQuery` işlevi, işlevi varlığa bir başvuru döndürür:  
  
 [!code-csharp[DP EntityServices Concepts 2#REF2](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref2)]  
  
 Aşağıdaki gibi parametreli bir sorgu başarılı olursa eklemek <xref:System.Data.EntityClient.EntityParameter> nesneleri <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> özellikte <xref:System.Data.EntityClient.EntityCommand> nesnesi.  
  
 [!code-csharp[DP EntityServices Concepts 2#REF3](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref3)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlreftypes)]
 [!code-vb[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlreftypes)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Entity SQL Başvurusu](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Entity Framework için EntityClient Sağlayıcısı](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
