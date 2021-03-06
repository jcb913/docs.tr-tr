---
title: 'Nasıl yapılır: yansıma sağlayıcısı (WCF Veri Hizmetleri) kullanarak bir veri hizmeti oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 44ba47deaf803f8a911b5a76d7e93f09b47e677a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363192"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a>Nasıl yapılır: yansıma sağlayıcısı (WCF Veri Hizmetleri) kullanarak bir veri hizmeti oluşturma
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Bu sınıfların uygulayan nesneler sunulan sürece, rasgele sınıflara göre bir veri modeli tanımlamanızı sağlar <xref:System.Linq.IQueryable%601> arabirimi. Daha fazla bilgi için bkz: [Veri Hizmetleri sağlayıcıları](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek içeren bir veri modeli tanımlar `Orders` ve `Items`. Varlık kapsayıcı sınıfı `OrderItemData` dönüş iki genel yöntemi vardır <xref:System.Linq.IQueryable%601> arabirimleri. Bu arabirimleri varlık kümeleridir `Orders` ve `Items` varlık türleri. Bir `Order` birden çok içerebilir `Items`, böylece `Orders` varlık türüne sahip bir `Items` koleksiyonu döndüren bir gezinti özelliği `Items` nesneleri. `OrderItemData` Varlık kapsayıcı sınıftır genel türü <xref:System.Data.Services.DataService%601> sınıfı `OrderItems` veri hizmeti elde edilmiştir.  
  
> [!NOTE]
>  Bu örnek, bir bellek içi veri sağlayıcısı gösterir ve değişiklikleri geçerli nesne örneklerini dışında kalıcı değildir çünkü uygulama öğesinden türetilen fayda yoktur <xref:System.Data.Services.IUpdatable> arabirimi. Uygulayan bir örnek <xref:System.Data.Services.IUpdatable> arabirim için bkz: [nasıl yapılır: bir LINQ to SQL veri kaynağı kullanarak bir veri hizmeti oluşturmak](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria reflection provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria reflection provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: LINQ to SQL Veri Kaynağı Kullanarak Veri Hizmeti Oluşturma](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)  
 [Veri Hizmetleri Sağlayıcıları](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Nasıl yapılır: ADO.NET Entity Framework Veri Kaynağı Kullanarak Veri Hizmeti Oluşturma](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
