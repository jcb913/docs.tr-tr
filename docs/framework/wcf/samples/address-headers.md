---
title: Adres Üstbilgileri
ms.date: 03/30/2017
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
ms.openlocfilehash: 276649c17a04822eb27eb4e3ed9cbe711b384edc
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803796"
---
# <a name="address-headers"></a>Adres Üstbilgileri
Adres üstbilgileri örnek istemciler Windows Communication Foundation (WCF) kullanarak bir hizmet için başvuru parametreleri nasıl geçirebilirsiniz gösterir.  
  
> [!NOTE]
>  Kurulum yordamı ve yapı yönergeleri Bu örnek için bu konunun sonunda yer alır.  
  
 WS-adresleme belirtimi bir uç nokta başvuru kavramı belirli bir Web Hizmeti uç noktası adresi için bir yol olarak tanımlar. Kullanarak uç nokta başvuruları Modellenen WCF içinde `EndpointAddress` sınıfı - `EndpointAddress` adres alanının türü `ServiceEndpoint` sınıfı.  
  
 Uç nokta başvuru modeli her başvuru fazladan tanımlama bilgilerini eklemek bazı başvuru parametreleri taşıyabilir parçasıdır. Örnekleri olarak Modellenen WCF, bu başvuru parametreleri `AddressHeader` sınıfı.  
  
 Bu örnekte, istemci başvuru parametresi ekler `EndpointAddress` istemci uç noktası. Hizmet için bu başvuru parametresi arar ve onun "Hello" hizmet işlemi mantığında değerini kullanır.  
  
## <a name="client"></a>İstemci  
 İstemcinin bir başvuru parametre göndermek, onu eklemelisiniz bir `AddressHeader` için `EndpointAddress` , `ServiceEndpoint`. Çünkü `EndpointAddress` sınıfı değişmez, bir uç nokta adresi değiştirilmesini yapılmalıdır kullanarak `EndpointAddressBuilder` sınıfı. Aşağıdaki kod, ileti bir parçası olarak bir başvuru parametre göndermek için istemci başlatır.  
  
```csharp   
HelloClient client = new HelloClient();  
EndpointAddressBuilder builder =   
    new EndpointAddressBuilder(client.Endpoint.Address);  
AddressHeader header =   
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");  
builder.Headers.Add(header);  
client.Endpoint.Address = builder.ToEndpointAddress();  
```  
  
 Kod oluşturur bir `EndpointAddressBuilder` özgün kullanarak `EndpointAddress` başlangıç değeri olarak. Ardından, yeni oluşturulan adres üstbilgisi ekler; çağrı `CreateAddressHeadercreates` belirli ad, ad ve değere sahip bir üstbilgi. Burada "John" değeridir. Üstbilgi oluşturucuya eklendikten sonra `ToEndpointAddress()` yöntemi (değişebilir) oluşturucu geri istemci uç noktanın bir adres alanına atanan geri bir (değişmez) uç noktası adresi dönüştürür.  
  
 Şimdi istemci çağırdığında `Console.WriteLine(client.Hello());`, istemci elde edilen çıktıda görüldüğü şekilde hizmet bu adresi parametresinin değerini alabilir.  
  
 `Hello, John`  
  
## <a name="server"></a>Sunucu  
 Hizmet işlemi uygulama `Hello()` geçerli kullanan `OperationContext` gelen ileti üstbilgilerinde değerlerini incelemek için.  
  
```csharp   
string id = null;  
// look at headers on incoming message  
for (int i = 0;   
     i < OperationContext.Current.IncomingMessageHeaders.Count;   
     ++i)  
{  
    MessageHeaderInfo h = OperationContext.Current.IncomingMessageHeaders[i];  
    // for any reference parameters with the correct name & namespace  
    if (h.IsReferenceParameter &&   
        h.Name == IDName &&   
        h.Namespace == IDNamespace)  
    {  
        // read the value of that header  
        XmlReader xr = OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);  
        id = xr.ReadElementContentAsString();  
    }  
}  
return "Hello, " + id;  
```  
  
 Başvuru parametreleri belirli adla üstbilgileri arayan gelen ileti üzerinde tüm üstbilgileri üzerinden kodu tekrarlanan ve. Parametresi bulunduğunda parametresinin değeri okur ve "id" değişkeninde depolar.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Ayarlamak için derleme ve örnek çalıştırın  
  
1.  Gerçekleştirmiş emin olun [kerelik Kurulum prosedürü Windows Communication Foundation örnekleri için](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Çözüm C# veya Visual Basic .NET sürümünü oluşturmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Tek veya çapraz makine yapılandırmada örneği çalıştırmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örneklerini çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`  
  
## <a name="see-also"></a>Ayrıca Bkz.
