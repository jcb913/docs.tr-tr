---
title: '&lt;İzleme&gt; öğesi'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 59d5083632630513d2afc1f8d78400310451e46f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746065"
---
# <a name="lttracegt-element"></a>&lt;İzleme&gt; öğesi
Toplamak, depolamak ve izleme iletilerini yönlendirmek dinleyicileri içerir.  
  
 \<Yapılandırma >  
\<System.Diagnostics >  
\<İzleme >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`autoflush`|İsteğe bağlı öznitelik.<br /><br /> İzleme dinleyicileri çıkış arabelleği sonra her yazma işlemi otomatik olarak temizleme olup olmadığını belirtir.|  
|`indentsize`|İsteğe bağlı öznitelik.<br /><br /> Girinti alanları sayısını belirtir.|  
|`useGlobalLock`|İsteğe bağlı öznitelik.<br /><br /> Genel kilit kullanılması gerekip gerekmediğini gösterir.|  
  
## <a name="autoflush-attribute"></a>AutoFlush özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`false`|Otomatik olarak çıkış arabelleği temizleme değil. Bu varsayılandır.|  
|`true`|Çıkış arabelleği otomatik olarak boşaltır.|  
  
## <a name="usegloballock-attribute"></a>useGlobalLock özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`false`|Dinleyici iş parçacığı içinde korumalı ise genel kilit kullanmaz; Aksi takdirde, genel kilit kullanır.|  
|`true`|Dinleyici iş parçacığı güvenli olmasına bakılmaksızın genel kilit kullanır. Bu varsayılandır.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<dinleyicileri >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Toplar, depolar, bir dinleyici belirtir ve iletileri yönlendirir.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|  
|`system.diagnostics`|Toplamak, depolamak ve iletileri ve izleme anahtarı ayarlandığı düzeyi rota izleme dinleyicilerini belirtir.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `<trace>` dinleyicisi eklemek için öğesi `MyListener` için `Listeners` koleksiyonu. `MyListener` adlı bir dosya oluşturur `MyListener.log` ve çıkış dosyasına yazar. `useGlobalLock` Özniteliği `false`, İzleme dinleyicisi iş parçacığı içinde korumalı ise kullanılmayacak genel kilit neden olur. `autoflush` Özniteliği `true`, bağımsız olarak mı yoksa dosyaya yazmak İzleme dinleyicisi neden olan <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> yöntemi çağrılır. `indentsize` Özniteliği sıfır alanları girinti dinleyicisi neden olan 0 (sıfır) olarak ayarlanmış olduğunda <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> yöntemi çağrılır.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [İzleme ve Hata Ayıklama Ayarları Şeması](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
