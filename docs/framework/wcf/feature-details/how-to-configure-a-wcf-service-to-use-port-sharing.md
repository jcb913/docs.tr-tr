---
title: 'Nasıl yapılır: Bağlantı Noktası Paylaşımı Kullanarak Bir Windows Communication Foundation Hizmetini Yapılandırma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6400bc71-a858-4ac2-8d5a-caa72d3b5482
ms.openlocfilehash: 0a3aca2bac546c9142137afc025133bc1154ff90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495248"
---
# <a name="how-to-configure-a-windows-communication-foundation-service-to-use-port-sharing"></a>Nasıl yapılır: Bağlantı Noktası Paylaşımı Kullanarak Bir Windows Communication Foundation Hizmetini Yapılandırma
Kullanarak hizmet kullanıma sunmak için Windows Communication Foundation (WCF) uygulamanızda net.tcp:// bağlantı noktası kullanmak için en kolay yolu olan <xref:System.ServiceModel.NetTcpBinding>.  
  
 Bu bağlama sağlayan bir <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> net.tcp:// bağlantı noktası paylaşımı bu bağlama ile yapılandırılan hizmet için etkinleştirilip etkinleştirilmediğini denetler özelliği.  
  
 Aşağıdaki yordam nasıl kullanılacağını gösterir <xref:System.ServiceModel.NetTcpBinding> sınıfı bir uç noktada Tekdüzen Kaynak Tanımlayıcısı (URI) net.tcp://localhost/MyService önce kodda ve ardından yapılandırma öğelerini kullanarak açın.  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-code"></a>Bir NetTcpBinding üzerinde kodda net.tcp:// bağlantı noktası etkinleştirmek için  
  
1.  Adlı bir sözleşme uygulamak için bir hizmet oluşturma `IMyService` ve çağrısından `MyService`,.  
  
     [!code-csharp[c_ConfigurePortSharing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#1)]
     [!code-vb[c_ConfigurePortSharing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#1)]  
  
2.  Bir örneğini oluşturmak <xref:System.ServiceModel.NetTcpBinding> sınıfı ve ayarlayın <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> özelliğine `true`.  
  
     [!code-csharp[c_ConfigurePortSharing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#2)]
     [!code-vb[c_ConfigurePortSharing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#2)]  
  
3.  Oluşturma bir <xref:System.ServiceModel.ServiceHost> ve bunun için hizmet uç noktası eklemek `MyService` paylaşımı etkin bağlantı noktası kullanan <xref:System.ServiceModel.NetTcpBinding> ve dinlediği uç noktada URI "net.tcp://localhost/MyService" adres.  
  
     [!code-csharp[c_ConfigurePortSharing#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#3)]
     [!code-vb[c_ConfigurePortSharing#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#3)]  
  
    > [!NOTE]
    >  Bu örnek, uç nokta adresi URI farklı bir bağlantı noktası belirtmediğinden 808 varsayılan TCP bağlantı noktasını kullanır. Bağlantı noktası paylaşımı açıkça aktarım bağlama üzerinde etkin olduğundan, bu hizmet bağlantı noktası 808 diğer işlemlerinde diğer hizmetlerle paylaşabilirsiniz. Bu hizmet bağlantı noktası paylaşımı verilmez ve başka bir uygulama 808 numaralı bağlantı noktasını zaten kullanıyor, throw bir <xref:System.ServiceModel.AddressAlreadyInUseException> zaman erişimiyle açıldı.  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-configuration"></a>Bir NetTcpBinding yapılandırmasında net.tcp:// bağlantı noktası etkinleştirmek için  
  
1.  Aşağıdaki örnekte, bağlantı noktası paylaşımı etkinleştirme ve yapılandırma öğeleri kullanılarak hizmet uç noktası eklemek gösterilmiştir.  
  
```xml  
<system.serviceModel>  
  <bindings>  
    <netTcpBinding name="portSharingBinding"   
                   portSharingEnabled="true" />  
  </bindings>  
  <services>  
    <service name="MyService">  
        <endpoint address="net.tcp://localhost/MyService"  
                  binding="netTcpBinding"  
                  contract="IMyService"  
                  bindingConfiguration="portSharingBinding" />  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Net.TCP Bağlantı Noktası Paylaşımı](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [Nasıl yapılır: Net.TCP Bağlantı Noktası Paylaşım Hizmetini Etkinleştirme](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)
