---
title: 'Nasıl yapılır: WSDL Sözleşmeleriyle Hizmet Bilinen Adı Kullanma'
ms.date: 03/30/2017
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
ms.openlocfilehash: 838e7affcf47742c8f372879fcb33946d53ba43f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491049"
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a>Nasıl yapılır: WSDL Sözleşmeleriyle Hizmet Bilinen Adı Kullanma
Tamamen kendi içinde bulunan bir COM birlikte çalışma istemciniz isteyebileceğiniz durumlar vardır. Aramak istediğiniz hizmet MEX bitiş noktası ve DLL COM birlikte çalışma için kaydettirilmemiş olabilir WCF istemcisi getirebilir değil. Bu durumlarda, hizmet açıklayan bir WSDL dosyası oluşturun ve WCF hizmet bilinen adı geçirin. Bu konuda, bir WCF WSDL ad kullanarak alma başlatıldı WCF örnek çağrı açıklar.  
  
### <a name="using-the-wsdl-service-moniker"></a>WSDL hizmet bilinen adı kullanma  
  
1.  Açın ve GettingStarted örnek çözümü oluşturun.  
  
2.  Internet Explorer'ı açın ve http://localhost/ServiceModelSamples/Service.svc hizmetinin çalıştığından emin olmak için.  
  
3.  Adını da dosyasında CalculatorService sınıfında şu özniteliği ekleyin:  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4.  Bir bağlama ad alanı hizmeti App.config ekleyin:  
  
  
  
5.  WSDL dosyası okumak üzere bir uygulama oluşturun. Ad alanları 3 ve 4. adımlarda eklenmiş olduğundan göz atarak hizmetin tüm WSDL açıklamasını sorgulamak için IE kullanabilirsiniz http://localhost/ServiceModelSamples/Service.svc?wsdl. Dosyayı serviceWSDL.xml Internet Explorer'dan kaydedin. Adım 3 ve 4 ad belirtmezseniz, yukarıdaki URL sorgulama döndürülen WSDL belge tam WSDL olmaz. Döndürülen WSDL belge diğer WSDL belgeleri içe birkaç içeri aktarma deyimlerini içerir. Her alma deyimi aracılığıyla gidin ve tam WSDL belgesi oluşturmak, hizmetten içeri WSDL ile döndürülen WSDL birleştirme gerekir.  
  
6.  Visual Basic 6.0 açın ve yeni bir standart .exe dosyası oluşturun. Aşağıdaki kod tıklatın işleyicisine eklemek için düğmesini çift tıklayın ve forma düğme ekleme:  
  
    ```  
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    >  Ad hatalı veya hizmet kullanılamıyor çağrısı `GetObject` "Geçersiz sözdizimi" bildiren bir hata döndürecektir.  Bu hatayı alırsanız, kullanmakta olduğunuz adının doğru olduğundan ve hizmet kullanılabilir olduğundan emin olun.  
  
7.  Visual Basic uygulamasını çalıştırın. Bir ileti kutusu arama çıkarma (145, 76.54) sonuçlarını görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken](../../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [COM Uygulamaları ile Tümleştirme Genel Bakış](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)
