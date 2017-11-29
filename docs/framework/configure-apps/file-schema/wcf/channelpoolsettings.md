---
title: '&lt;channelPoolSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 44e79c7af470cefead8bcfb0ef96606ecde30383
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltchannelpoolsettingsgt"></a><span data-ttu-id="0ce40-102">&lt;channelPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="0ce40-102">&lt;channelPoolSettings&gt;</span></span>
<span data-ttu-id="0ce40-103">Özel bağlama için kanal havuzu ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0ce40-103">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="0ce40-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0ce40-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0ce40-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="0ce40-105">\<bindings></span></span>  
<span data-ttu-id="0ce40-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0ce40-106">\<customBinding></span></span>  
<span data-ttu-id="0ce40-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="0ce40-107">\<binding></span></span>  
<span data-ttu-id="0ce40-108">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="0ce40-108">\<oneWay></span></span>  
<span data-ttu-id="0ce40-109">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="0ce40-109">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ce40-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0ce40-110">Syntax</span></span>  
  
```xml  
<channelPoolSettings  
    idleTimeout"TimeSpan"  
        leaseTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ce40-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="0ce40-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0ce40-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0ce40-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ce40-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="0ce40-113">Attributes</span></span>  
  
|<span data-ttu-id="0ce40-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="0ce40-114">Attribute</span></span>|<span data-ttu-id="0ce40-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0ce40-115">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="0ce40-116">Bir pozitif <xref:System.TimeSpan> kanalları havuzunda boşta kalabileceği kesilmeden önce en uzun süreyi belirtir.</span><span class="sxs-lookup"><span data-stu-id="0ce40-116">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="0ce40-117">Varsayılan değer 00:02:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="0ce40-117">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="0ce40-118">A <xref:System.TimeSpan> sonra havuza geri döner olduğunda bir kanal kapalı zaman aralığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0ce40-118">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="0ce40-119">Varsayılan değer 00:10: 00'dır.</span><span class="sxs-lookup"><span data-stu-id="0ce40-119">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="0ce40-120">Her uzak uç nokta için havuzunda saklanan kanalları en fazla sayısını belirtir pozitif bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="0ce40-120">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="0ce40-121">Varsayılan değer 10'dur.</span><span class="sxs-lookup"><span data-stu-id="0ce40-121">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ce40-122">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="0ce40-122">Child Elements</span></span>  
 <span data-ttu-id="0ce40-123">Yok.</span><span class="sxs-lookup"><span data-stu-id="0ce40-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ce40-124">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="0ce40-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0ce40-125">Öğe</span><span class="sxs-lookup"><span data-stu-id="0ce40-125">Element</span></span>|<span data-ttu-id="0ce40-126">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0ce40-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ce40-127">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="0ce40-127">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="0ce40-128">Paket için özel bir bağlama yönlendirmesini etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="0ce40-128">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ce40-129">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0ce40-129">Remarks</span></span>  
 <span data-ttu-id="0ce40-130">Kotalar aşırı kaynaklarının kullanımını engellemek için bir ilke mekanizması olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="0ce40-130">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="0ce40-131">Bunlar kötü amaçlı veya istenmeyen hizmet reddi (DOS) saldırılarını önler.</span><span class="sxs-lookup"><span data-stu-id="0ce40-131">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="0ce40-132">Bu öğe kanal kotaları özel bir kanalda ayarlarken kullanın.</span><span class="sxs-lookup"><span data-stu-id="0ce40-132">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="0ce40-133">`ChannelPoolSettings`üç kotaları belirtir:</span><span class="sxs-lookup"><span data-stu-id="0ce40-133">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
-   <span data-ttu-id="0ce40-134">`idleTimeout` Kota sunucusundaki kaynakları uzun bir süre için bağlamadan kullanan hizmet reddi (DOS) saldırıları azaltmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="0ce40-134">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="0ce40-135">İstemci üzerinde doğru değeri ayarı hizmetiyle bağlayan güvenilirliğini artırabilir.</span><span class="sxs-lookup"><span data-stu-id="0ce40-135">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="0ce40-136">Varsayılan değer ölçülü uygun tahsis edilen kaynakların temel alır.</span><span class="sxs-lookup"><span data-stu-id="0ce40-136">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="0ce40-137">Bir geliştirme ortamı ve küçük yükleme senaryoları için uygun olan.</span><span class="sxs-lookup"><span data-stu-id="0ce40-137">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="0ce40-138">Hizmet yöneticileri, yüklemenin kaynakları tükendi çalıştırıyorsa veya ek kaynaklar kullanılabilirlik rağmen bağlantıları sınırlı değeri gözden geçirmelidir.</span><span class="sxs-lookup"><span data-stu-id="0ce40-138">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="0ce40-139">`leaseTimeout` Kotası için kullanılan yük dengeleyici ile tümleştirme için ve güvenilirlik geliştirmek için.</span><span class="sxs-lookup"><span data-stu-id="0ce40-139">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="0ce40-140">Varsayılan değer koruyucu tahsis edilen kaynakların temel alır.</span><span class="sxs-lookup"><span data-stu-id="0ce40-140">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="0ce40-141">Bir geliştirme ortamı ve küçük yükleme senaryoları için uygun olan.</span><span class="sxs-lookup"><span data-stu-id="0ce40-141">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="0ce40-142">Hizmet yöneticileri, yüklemenin kaynakları tükendi çalıştırıyorsa veya ek kaynaklar kullanılabilirlik rağmen bağlantıları sınırlı değeri gözden geçirmelidir.</span><span class="sxs-lookup"><span data-stu-id="0ce40-142">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="0ce40-143">`maxOutboundChannelsPerEndpoint` Kota hem sunucu hem de istemci önbellek sınırlarını ayarlar ve güvenilirliğini artırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="0ce40-143">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="0ce40-144">Varsayılan değer bir geliştirme ortamı ve küçük yükleme senaryoları için uygun bir ölçülü uygun ayırma kaynakların temel alır.</span><span class="sxs-lookup"><span data-stu-id="0ce40-144">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="0ce40-145">Hizmet yöneticileri, yüklemenin kaynakları tükendi çalıştırıyorsa veya ek kaynaklar kullanılabilirlik rağmen bağlantıları sınırlı değeri gözden geçirmelidir.</span><span class="sxs-lookup"><span data-stu-id="0ce40-145">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce40-146">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0ce40-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>  
 <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="0ce40-147">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="0ce40-147">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)  
 [<span data-ttu-id="0ce40-148">Bağlamaları</span><span class="sxs-lookup"><span data-stu-id="0ce40-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="0ce40-149">Bağlamaları genişletme</span><span class="sxs-lookup"><span data-stu-id="0ce40-149">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="0ce40-150">Özel bağlamalar</span><span class="sxs-lookup"><span data-stu-id="0ce40-150">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="0ce40-151">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0ce40-151">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)