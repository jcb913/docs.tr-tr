---
title: "Filtre Seçme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67ab5af9-b9d9-4300-b3b1-41abb5a1fd10
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 973a70fdb655ab069d6ecdafd0e017324720e57a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="choosing-a-filter"></a><span data-ttu-id="15b3d-102">Filtre Seçme</span><span class="sxs-lookup"><span data-stu-id="15b3d-102">Choosing a Filter</span></span>
<span data-ttu-id="15b3d-103">Yönlendirme hizmeti yapılandırırken, doğru ileti filtreleri seçin ve bunları aldığınız iletileri karşı tam eşleşme yapmanıza izin verecek şekilde yapılandırmak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="15b3d-103">When configuring the Routing Service, it is important to select correct message filters and configure them to allow you to make exact matches against the messages you receive.</span></span> <span data-ttu-id="15b3d-104">Seçtiğiniz filtre kendi eşleşmeleri aşırı geniş kapsamlı veya yanlış yapılandırılmış iletiler yanlış yönlendirilir.</span><span class="sxs-lookup"><span data-stu-id="15b3d-104">If the filters you select are overly broad in their matches or are incorrectly configured, messages are routed incorrectly.</span></span> <span data-ttu-id="15b3d-105">Filtreler çok kısıtlayıcı olması durumunda, kullanılabilir tüm geçerli yollar bazı iletilerinizin olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="15b3d-105">If the filters are too restrictive, you may not have any valid routes available for some of your messages.</span></span>  
  
## <a name="filter-types"></a><span data-ttu-id="15b3d-106">Filtre türleri</span><span class="sxs-lookup"><span data-stu-id="15b3d-106">Filter Types</span></span>  
 <span data-ttu-id="15b3d-107">Yönlendirme hizmeti tarafından kullanılan filtreleri seçerken, hangi bilgilerin kullanılabilir yanı sıra her bir filtrenin nasıl çalıştığını anlamak önemlidir gelen iletileri bir parçası olarak.</span><span class="sxs-lookup"><span data-stu-id="15b3d-107">When selecting the filters that are used by the Routing Service, it is important that you understand how each filter works as well as what information is available as part of the incoming messages.</span></span> <span data-ttu-id="15b3d-108">Tüm iletileri aynı uç noktası üzerinden alınırsa, tüm iletileri bu filtreler eşleştiğinden örneği için adres ve EndpointName filtreleri yararlı değildir.</span><span class="sxs-lookup"><span data-stu-id="15b3d-108">For instance, if all messages are received over the same endpoint, the Address and EndpointName filters are not useful because all messages match these filters.</span></span>  
  
### <a name="action"></a><span data-ttu-id="15b3d-109">Eylem</span><span class="sxs-lookup"><span data-stu-id="15b3d-109">Action</span></span>  
 <span data-ttu-id="15b3d-110">Eylem filtresi inceler <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="15b3d-110">The Action filter inspects the <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A> property.</span></span> <span data-ttu-id="15b3d-111">Eylem üst bilgi iletisi içeriği filtre yapılandırmasında belirtilen filtre veri değeri eşleşmesi durumunda bu filtre döndürür `true`.</span><span class="sxs-lookup"><span data-stu-id="15b3d-111">If the contents of the Action header in the message match the filter data value specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="15b3d-112">Aşağıdaki örnek tanımlayan bir `FilterElement` iletileri "http://namespace/contract/operation/" değerini içeren bir eylem üstbilgisi ile eşleşecek şekilde eylem filtresi kullanan.</span><span class="sxs-lookup"><span data-stu-id="15b3d-112">The following example defines a `FilterElement` that uses the Action filter to match messages with an action header that contains a value of "http://namespace/contract/operation/".</span></span>  
  
```xml  
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/" />  
```  
  
```csharp  
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });  
```  
  
 <span data-ttu-id="15b3d-113">Bu filtre, benzersiz bir Action üstbilgisi içeren iletileri yönlendirme kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-113">This filter should be used when routing messages that contain a unique Action header.</span></span>  
  
### <a name="endpointaddress"></a><span data-ttu-id="15b3d-114">EndpointAddress</span><span class="sxs-lookup"><span data-stu-id="15b3d-114">EndpointAddress</span></span>  
 <span data-ttu-id="15b3d-115">EndpointAddress filtre iletisi alındı EndpointAddress olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="15b3d-115">The EndpointAddress filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="15b3d-116">Filtre yapılandırmasında belirtilen filtre adres iletinin tam olarak ulaştığında adresiyle eşleşen sonra bu filtre döndürür `true`.</span><span class="sxs-lookup"><span data-stu-id="15b3d-116">If the address that the message arrives at exactly matches the filter address specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="15b3d-117">Aşağıdaki örnek tanımlayan bir `FilterElement` gönderilen iletileri eşleşecek şekilde adresi filtresi kullanan "http://\<ana bilgisayar adı > / vdir/s.svc/b".</span><span class="sxs-lookup"><span data-stu-id="15b3d-117">The following example defines a `FilterElement` that uses the Address filter to match any messages addressed to "http://\<hostname>/vdir/s.svc/b".</span></span>  
  
```xml  
<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b" />  
```  
  
```csharp  
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
```  
  
> [!NOTE]
>  <span data-ttu-id="15b3d-118">Bir adresi ana bilgisayar adı bölümü olup tam etki alanı adı, NetBIOS adını, IP adresini veya diğer ad istemcinin göre farklı olabilir dikkate almak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="15b3d-118">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="15b3d-119">Farklı değerleri aynı ana bilgisayarına başvurduğundan bu karşılaştırma için varsayılan davranış adresi ana bilgisayar adı bölümü eşleşmeleri gerçekleştirirken değil kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-119">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>  
>   
>  <span data-ttu-id="15b3d-120">Bu davranış, ana bilgisayar adı yönlendirme hizmeti program aracılığıyla yapılandırırken değerlendirmek karşılaştırma izin verecek şekilde değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="15b3d-120">This behavior can be modified to allow the comparison to evaluate the host name when configuring the Routing Service programmatically.</span></span>  
  
 <span data-ttu-id="15b3d-121">Gelen iletiler için benzersiz bir adresi ele alınan bu filtre kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-121">This filter should be used when the incoming messages are addressed to a unique address.</span></span>  
  
### <a name="endpointaddressprefix"></a><span data-ttu-id="15b3d-122">EndpointAddressPrefix</span><span class="sxs-lookup"><span data-stu-id="15b3d-122">EndpointAddressPrefix</span></span>  
 <span data-ttu-id="15b3d-123">EndpointAddressPrefix filtre EndpointAddress filtre benzer.</span><span class="sxs-lookup"><span data-stu-id="15b3d-123">The EndpointAddressPrefix filter is similar to the EndpointAddress filter.</span></span> <span data-ttu-id="15b3d-124">EndpointAddressPrefix filtre iletisi alındı EndpointAddress olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="15b3d-124">The EndpointAddressPrefix filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="15b3d-125">Ancak EndpointAddressPrefix filtre filtre yapılandırmasında belirtilen değerle başlayan adreslerini eşleştirerek joker karakter olarak işlev görür.</span><span class="sxs-lookup"><span data-stu-id="15b3d-125">However the EndpointAddressPrefix filter acts as a wildcard by matching addresses that begin with the value specified in the filter configuration.</span></span> <span data-ttu-id="15b3d-126">Aşağıdaki örnek tanımlayan bir `FilterElement` gönderilen iletileri eşleşecek şekilde EndpointAddressPrefix filtresi kullanan "http://\<ana bilgisayar adı > / vdir *".</span><span class="sxs-lookup"><span data-stu-id="15b3d-126">The following example defines a `FilterElement` that uses the EndpointAddressPrefix filter to match any messages addressed to "http://\<hostname>/vdir*".</span></span>  
  
```xml  
<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/vdir" />  
```  
  
```csharp  
PrefixEndpointAddressMessageFilter prefix1 = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
```  
  
> [!NOTE]
>  <span data-ttu-id="15b3d-127">Bir adresi ana bilgisayar adı bölümü olup tam etki alanı adı, NetBIOS adını, IP adresini veya diğer ad istemcinin göre farklı olabilir dikkate almak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="15b3d-127">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="15b3d-128">Farklı değerleri aynı ana bilgisayarına başvurduğundan bu karşılaştırma için varsayılan davranış adresi ana bilgisayar adı bölümü eşleşmeleri gerçekleştirirken değil kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-128">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>  
  
 <span data-ttu-id="15b3d-129">Bu filtre, ortak bir adres öneki paylaşan gelen iletileri yönlendirme kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-129">This filter should be used when routing incoming messages that share a common address prefix.</span></span>  
  
### <a name="and"></a><span data-ttu-id="15b3d-130">AND</span><span class="sxs-lookup"><span data-stu-id="15b3d-130">AND</span></span>  
 <span data-ttu-id="15b3d-131">VE filtre doğrudan bir ileti içinde bir değerle filtre değil, ancak oluşturmak için iki filtre birleştirmek sağlar bir `AND` burada hem filtreleri eşleşmelidir ileti ve filtresinin önce koşul `true`.</span><span class="sxs-lookup"><span data-stu-id="15b3d-131">The AND filter does not directly filter on a value within a message, but allows you to combine two other filters to create an `AND` condition where both filters must match the message before the AND filter evaluates to `true`.</span></span> <span data-ttu-id="15b3d-132">Bu, tüm alt filtreleri eşleşirse, yalnızca eşleşen karmaşık filtreler oluşturmanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="15b3d-132">This allows you to create complex filters that only match if all the sub-filters match.</span></span> <span data-ttu-id="15b3d-133">Aşağıdaki örnekte bir adres filtresi ve bir eylem filtresi tanımlar ve bir ileti adresi ve eylem filtreleriyle değerlendirir ve filtre tanımlar.</span><span class="sxs-lookup"><span data-stu-id="15b3d-133">The following example defines an address filter and an action filter, and then defines an AND filter that evaluates a message against both the address and action filters.</span></span> <span data-ttu-id="15b3d-134">VE filtre döndürür sonra adres ve eylem filtreleri, eşleşiyorsa `true`.</span><span class="sxs-lookup"><span data-stu-id="15b3d-134">If both the address and the action filters match, then the AND filter returns `true`.</span></span>  
  
```xml  
<filter name="address1" filterType="AddressPrefix" filterData="http://host/vdir"/>  
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/"/>  
<filter name="and1" filterType="And" filter1="address1" filter2="action1" />  
```  
  
```csharp  
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });  
StrictAndMessageFilter and1=new StrictAndMessageFilter(address1, action1);  
```  
  
 <span data-ttu-id="15b3d-135">Bir eşleşme ne zaman yapılması gerektiğini belirlemek için birden çok filtre mantığından birlikte kullandığınızda bu filtre kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-135">This filter should be used when you must combine the logic from multiple filters to determine when a match should be made.</span></span> <span data-ttu-id="15b3d-136">Örneğin, yalnızca belirli eylemler ve birleşimleri belirli adresleri iletileri alması gereken birden çok varış yeri varsa gerekli eylem ve adresi filtrelerini birleştirmeye ve filtre kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="15b3d-136">For example, if you have multiple destinations that must receive only certain combinations of actions and messages to particular addresses, you can use an AND filter to combine the necessary Action and Address filters.</span></span>  
  
### <a name="custom"></a><span data-ttu-id="15b3d-137">Özel</span><span class="sxs-lookup"><span data-stu-id="15b3d-137">Custom</span></span>  
 <span data-ttu-id="15b3d-138">Özel filtre türü seçerken içeren bütünleştirilmiş kodun türünü içeren bir customType değeri sağlamalısınız **MessageFilter** Bu filtre için kullanılacak uygulama.</span><span class="sxs-lookup"><span data-stu-id="15b3d-138">When selecting the Custom filter type, you must provide a customType value that contains the type of the assembly that contains the **MessageFilter** implementation to be used for this filter.</span></span> <span data-ttu-id="15b3d-139">Ayrıca, filterData özel filtre iletileri değerlendirilmesinde gerektirebilecek herhangi bir değeri içermelidir.</span><span class="sxs-lookup"><span data-stu-id="15b3d-139">Additionally, filterData must contain any values that the custom filter may require in its evaluation of messages.</span></span> <span data-ttu-id="15b3d-140">Aşağıdaki örnek tanımlayan bir `FilterElement` kullanan `CustomAssembly.MyCustomMsgFilter` MessageFilter uygulaması.</span><span class="sxs-lookup"><span data-stu-id="15b3d-140">The following example defines a `FilterElement` that uses the `CustomAssembly.MyCustomMsgFilter` MessageFilter implementation.</span></span>  
  
```xml  
<filter name="custom1" filterType="Custom" customType="CustomAssembly.MyCustomMsgFilter, CustomAssembly" filterData="Custom Data" />  
```  
  
```csharp  
MyCustomMsgFilter custom1=new MyCustomMsgFilter("Custom Data");  
```  
  
 <span data-ttu-id="15b3d-141">İle sağlanan filtreler tarafından kapsanmayan bir ileti karşı özel eşleşen mantık yapmanız gereken [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], uygulamasıdır özel bir filtre oluşturmanız gerekir **MessageFilter** sınıfı.</span><span class="sxs-lookup"><span data-stu-id="15b3d-141">If you need to perform custom matching logic against a message that is not covered by the filters provided with [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], you must create a custom filter that is an implementation of the **MessageFilter** class.</span></span> <span data-ttu-id="15b3d-142">Örneğin, bir alana filtre yapılandırma olarak verilen bilinen değerler listesini karşı gelen ileti karşılaştırır veya belirli ileti öğesi karma hale getirir ve bu değeri belirlemek için inceler özel bir filtre oluşturabilirsiniz olup olmadığını filtresi döndürmelidir `true` veya `false`.</span><span class="sxs-lookup"><span data-stu-id="15b3d-142">For example, you might create a custom filter that compares a field in the incoming message against a list of known values given to the filter as configuration, or that hashes a particular message element and then examines that value to determine whether the filter should return `true` or `false`.</span></span>  
  
### <a name="endpointname"></a><span data-ttu-id="15b3d-143">endpointName</span><span class="sxs-lookup"><span data-stu-id="15b3d-143">EndpointName</span></span>  
 <span data-ttu-id="15b3d-144">EndpointName filtre iletisi aldı uç noktanın adı olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="15b3d-144">The EndpointName filter inspects the name of the endpoint that received the message.</span></span> <span data-ttu-id="15b3d-145">Aşağıdaki örnek tanımlayan bir `FilterElement` EndpointName filtre "SvcEndpoint" alınan iletileri yönlendirmek için kullanır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-145">The following example defines a `FilterElement` that uses the EndpointName filter to route messages received on the "SvcEndpoint".</span></span>  
  
```xml  
<filter name="name1" filterType="Endpoint" filterData="SvcEndpoint" />  
```  
  
```csharp  
EndpointNameMessageFilter name1 = new EndpointNameMessageFilter("SvcEndpoint");  
```  
  
 <span data-ttu-id="15b3d-146">Bu filtre, yönlendirme hizmeti birden fazla adlandırılmış hizmet uç noktasını kullanıma sunar yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-146">This filter is useful when the Routing Service exposes more than one named service endpoint.</span></span> <span data-ttu-id="15b3d-147">Örneğin, yönlendirme hizmeti iletileri almak için kullandığı iki uç nokta açmış olabilirsiniz; gerçek zamanlı diğer uç nokta sırasında iletilerinin işlenmesini duyarlı saat değil iletilerini alır isteyen öncelik müşteriler tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-147">For example, you might expose two endpoints that the Routing Service uses to receive messages; one is used by priority customers who require real-time processing of their messages, while the other endpoint receives messages that are not time sensitive.</span></span>  
  
 <span data-ttu-id="15b3d-148">Genellikle tam kullanabilirsiniz, ancak bir ileti, tanımlanmış uç nokta adı kullanmayı alındı hangi uç noktaya belirlemek için eşleşen daha az hataya, özellikle bir Yapılandırması'nı kullanarak bir yönlendirme hizmeti yapılandırırken görülür kullanışlı bir kısayol adresidir (uç nokta adları gerekli bir öznitelik nerede) dosyası.</span><span class="sxs-lookup"><span data-stu-id="15b3d-148">While you can often use full address matching to determine which endpoint a message was received on, using the defined endpoint name instead is a convenient shortcut that is often less error prone, especially when configuring a Routing Service using a configuration file (where endpoint names are a required attribute).</span></span>  
  
### <a name="matchall"></a><span data-ttu-id="15b3d-149">MatchAll</span><span class="sxs-lookup"><span data-stu-id="15b3d-149">MatchAll</span></span>  
 <span data-ttu-id="15b3d-150">MatchAll filtre ile eşleşen hiçbir alınan ileti.</span><span class="sxs-lookup"><span data-stu-id="15b3d-150">The MatchAll filter matches any received message.</span></span> <span data-ttu-id="15b3d-151">Tüm alınan iletinin bir kopyasını depolayan bir günlük kaydı hizmeti gibi belirli bir uç nokta için tüm alınan iletileri yönlendirmek her zaman gerekir yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-151">It is useful if you must always route all received messages to a specific endpoint, such as a logging service that stores a copy of all received messages.</span></span> <span data-ttu-id="15b3d-152">Aşağıdaki örnek tanımlayan bir `FilterElement` MatchAll filtre kullanır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-152">The following example defines a `FilterElement` that uses the MatchAll filter.</span></span>  
  
```xml  
<filter name="matchAll1" filterType="MatchAll" />  
```  
  
```csharp  
MatchAllMessageFilter matchAll1 = new MatchAllMessageFilter();  
```  
  
### <a name="xpath"></a><span data-ttu-id="15b3d-153">XPath</span><span class="sxs-lookup"><span data-stu-id="15b3d-153">XPath</span></span>  
 <span data-ttu-id="15b3d-154">XPath filtresi iletisi içinde belirli bir öğenin incelemek için kullanılan bir XPath sorgusu belirtmenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-154">The XPath filter allows you to specify an XPath query that is used to inspect a specific element within the message.</span></span> <span data-ttu-id="15b3d-155">XPath filtresi doğrudan herhangi bir XML adreslenebilir giriş iletisindeki incelemek izin veren bir güçlü filtreleme seçenektir; ancak aldığınız iletileri yapısını belirli bilgisine sahip olmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="15b3d-155">XPath filtering is a powerful filtering option that allows you to directly inspect any XML addressable entry within the message; however it requires that you have specific knowledge of the structure of the messages that you are receiving.</span></span> <span data-ttu-id="15b3d-156">Aşağıdaki örnek tanımlayan bir `FilterElement` ileti "ns" ad alanı öneki'tarafından başvurulan ad alanı içindeki "öğesi" adlı bir öğe için incelemek için XPath filtresi kullanan.</span><span class="sxs-lookup"><span data-stu-id="15b3d-156">The following example defines a `FilterElement` that uses the XPath filter to inspect the message for an element named "element" within the namespace referenced by the "ns" namespace prefix.</span></span>  
  
```xml  
<filter name="xpath1" filterType="XPath" filterData="//ns:element" />  
```  
  
```csharp  
XPathMessageFilter xpath1=new XPathMessageFilter("//ns:element");  
```  
  
 <span data-ttu-id="15b3d-157">Bu filtre, aldığınız iletileri belirli bir değer içeren biliyorsanız yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="15b3d-157">This filter is useful if you know that the messages you are receiving contain a specific value.</span></span> <span data-ttu-id="15b3d-158">Örneğin, hizmetinin daha yeni sürümünü gönderilen iletiler özel üstbilgisinde benzersiz bir değer içermesi bildiğiniz iki sürümü aynı hizmet barındırma bu başlığı gitmek için XPath kullanır ve değer pres karşılaştırır bir filtresi oluşturabilirsiniz başka bir filtre eşleşip eşleşmediğini belirlemek için filtre yapılandırmada verilen üstbilgisinde ent.</span><span class="sxs-lookup"><span data-stu-id="15b3d-158">For example, if you are hosting two versions of the same service and you know that messages addressed to the newer version of the service contain a unique value in a custom header, you can create a filter that uses XPath to navigate to this header and compares the value present in the header to another given in the filter configuration to determine if the filter matches.</span></span>  
  
 <span data-ttu-id="15b3d-159">XPath sorguları genellikle uzun benzersiz ad alanları genellikle içerir veya karmaşık dize değerlerini XPath filtresi ad alanı tablosu, ad alanları için benzersiz önekleri belirlemek için kullanılır olanak tanıyan çünkü.</span><span class="sxs-lookup"><span data-stu-id="15b3d-159">Because XPath queries often contain unique namespaces, which are often lengthy or complex string values, the XPath filter allows you to use the namespace table to define unique prefixes for your namespaces.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="15b3d-160">ad alanı tablo bkz [ileti filtreleri](../../../../docs/framework/wcf/feature-details/message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="15b3d-160"> the namespace table, see [Message Filters](../../../../docs/framework/wcf/feature-details/message-filters.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="15b3d-161">XPath sorguları tasarlama, bkz: [XPath sözdizimi](http://go.microsoft.com/fwlink/?LinkId=164592).</span><span class="sxs-lookup"><span data-stu-id="15b3d-161"> designing XPath queries, see [XPath Syntax](http://go.microsoft.com/fwlink/?LinkId=164592).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15b3d-162">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="15b3d-162">See Also</span></span>  
 [<span data-ttu-id="15b3d-163">İleti filtreleri</span><span class="sxs-lookup"><span data-stu-id="15b3d-163">Message Filters</span></span>](../../../../docs/framework/wcf/feature-details/message-filters.md)  
 [<span data-ttu-id="15b3d-164">Nasıl yapılır: Filtreleri kullanma</span><span class="sxs-lookup"><span data-stu-id="15b3d-164">How To: Use Filters</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-filters.md)