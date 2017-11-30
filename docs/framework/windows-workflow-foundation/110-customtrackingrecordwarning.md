---
title: 110 - CustomTrackingRecordWarning
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bc093de-be47-4ed0-983f-05b4246446fc
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d75ceef6dbe290cafc6127ae007d1dcc3d28b50f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="110---customtrackingrecordwarning"></a>110 - CustomTrackingRecordWarning
## <a name="properties"></a>Özellikler  
  
|||  
|-|-|  
|Kimliği|110|  
|Anahtar Sözcükler|Sorun giderme, ögesi, WFTracking UserEvents, EndToEndMonitoring,|  
|Düzey|Uyarı|  
|Kanal|Microsoft Windows uygulama sunucusu-uygulamalar/analitik|  
  
## <a name="description"></a>Açıklama  
 Bir iş akışı örneği içinde bir etkinlik düzeyi uyarıyla CustomTrackingRecord yayar, bu olay ETW İzleme katılımcı tarafından gösterilen  
  
## <a name="message"></a>İleti  
 TrackRecord CustomTrackingRecord, örnek kimliği = %1, kayıt numarası = = %2, EventTime = %3, ad = %4, ActivityName = %5, etkinlik kimliği = %6, ActivityInstanceId = % 7 ' ye ActivityTypeName = %8, veri = %9, ek açıklamaları = % 10, ProfileName = % 11  
  
## <a name="details"></a>Ayrıntılar  
  
|Veri öğesi adı|Veri öğesi türü|Açıklama|  
|--------------------|--------------------|-----------------|  
|örnek kimliği|xs:GUID|İş akışı için örnek kimliği|  
|Kayıt numarası|xs:Long|Verilmiş kaydı sıra sayısı|  
|EventTime|xs: DateTime|Olay gösterilen zaman UTC zamanı|  
|Ad|xs: String|CustomTrackingRecord adı|  
|activityName|xs: String|CustomTrackingRecord gösterilen etkinlik adı|  
|Etkinlik Kimliği|xs: String|CustomTrackingRecord gösterilen etkinlik kimliği|  
|ActivityInstanceId|xs: String|CustomTrackingRecord gösterilen etkinlik örnek kimliği|  
|ActivityTypeName|xs: String|CustomTrackingRecord gösterilen etkinlik adı|  
|Veri|xs: String|Bu olay ile izlenen verileri.  Değerleri bir xml öğesi biçimde depolanır \<öğeleri >\< öğe adı "dataName" type="System.String =" > dataValue\</Madde > \< /öğelerini >.  Hiçbir veri izlenen sonra dizesini içeren \<öğeleri / >. ETW olay boyutu ETW arabellek boyutu veya bir ETW olayı için en fazla yükü sınırlıdır. Olay boyutu ETW sınırlarını aşıyor sonra olay ek açıklamalar bırakarak ve veri değeri ile değiştirerek kesilir \<öğeleri >...  \< /öğelerini >.  Aşağıdaki türlerden ToString() tarafından döndürülen değer depolanır; String,char,bool,int,short,Long,uint,ushort,ulong,System.Single,float,Double,System.Guid,System.DateTimeOffset,System.DateTime.  Diğer tüm türleri System.Runtime.Serialization.NetDataContractSerializer kullanarak serileştirilir.|  
|Ek Açıklamalar|xs: String|Bu olay için eklenen ek açıklamalar.  Değerleri bir xml öğesi biçimde depolanır \<öğeleri >\< öğe adı "annotationName" type="System.String =" > annotationValue\</Madde > \< /öğelerini >.  Ek açıklama dizesi içeriyorsa belirtilmişse \<öğeleri / >. ETW olay boyutu ETW arabellek boyutu veya bir ETW olayı için en fazla yükü sınırlıdır. Olay boyutu ETW sınırlarını aşıyor sonra olay ek açıklamalar bırakarak ve ek açıklama değeri ile değiştirerek kesilir \<öğeleri >...  \< /öğelerini >.|  
|ProfileName|xs: String|Adı veya gösterilmesini bu olay sonuçlandı izleme profili|  
|HostReference|xs: String|Bu alan, barındırılan web hizmetleri için web hiyerarşi hizmetinde benzersiz olarak tanımlar.  Buna ait biçimi olarak tanımlanır ' Web sitesi adı uygulamanın sanal yolu &#124; Hizmet sanal yolu &#124; ServiceName' örnek: ' varsayılan Web sitesi/CalculatorApplication, #124;/CalculatorService.svc &#124; CalculatorService'|  
|AppDomain|xs: String|AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.|