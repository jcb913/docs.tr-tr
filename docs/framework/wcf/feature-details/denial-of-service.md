---
title: Hizmet Reddi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: denial of service [WCF]
ms.assetid: dfb150f3-d598-4697-a5e6-6779e4f9b600
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 26b638b81f6402748b261e0766c18a6e9b3489d4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="denial-of-service"></a><span data-ttu-id="f4f24-102">Hizmet Reddi</span><span class="sxs-lookup"><span data-stu-id="f4f24-102">Denial of Service</span></span>
<span data-ttu-id="f4f24-103">Hizmet reddi oluşur. bir sistem iletileri işlenemiyor veya çok yavaş işlenene bir şekilde doludur.</span><span class="sxs-lookup"><span data-stu-id="f4f24-103">Denial of service occurs when a system is overwhelmed in such a way that messages cannot be processed, or they are processed extremely slowly.</span></span>  
  
## <a name="excess-memory-consumption"></a><span data-ttu-id="f4f24-104">Aşırı bellek tüketimi</span><span class="sxs-lookup"><span data-stu-id="f4f24-104">Excess Memory Consumption</span></span>  
 <span data-ttu-id="f4f24-105">Çok sayıda benzersiz yerel adları, ad alanlarını ve önekleri XML belgesiyle okunurken bir sorun oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-105">A problem can occur when reading an XML document with a large number of unique local names, namespaces, or prefixes.</span></span> <span data-ttu-id="f4f24-106">Öğesinden türeyen bir sınıf kullanıyorsanız <xref:System.Xml.XmlReader>, ve ya da çağırın <xref:System.Xml.XmlReader.LocalName%2A>, <xref:System.Xml.XmlReader.Prefix%2A> veya <xref:System.Xml.XmlReader.NamespaceURI%2A> her öğe için özelliği, döndürülen dize eklenen bir <xref:System.Xml.NameTable>.</span><span class="sxs-lookup"><span data-stu-id="f4f24-106">If you are using a class that derives from <xref:System.Xml.XmlReader>, and you call either the <xref:System.Xml.XmlReader.LocalName%2A>, <xref:System.Xml.XmlReader.Prefix%2A> or <xref:System.Xml.XmlReader.NamespaceURI%2A> property for each item, the returned string is added to a <xref:System.Xml.NameTable>.</span></span> <span data-ttu-id="f4f24-107">Tutulan koleksiyonu <xref:System.Xml.NameTable> hiçbir zaman bir sanal oluşturma boyutunda azaltır, dize tanıtıcısı "bellek sızıntısı".</span><span class="sxs-lookup"><span data-stu-id="f4f24-107">The collection held by the <xref:System.Xml.NameTable> never decreases in size, creating a virtual "memory leak" of the string handles.</span></span>  
  
 <span data-ttu-id="f4f24-108">Azaltıcı Etkenler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="f4f24-108">Mitigations include:</span></span>  
  
-   <span data-ttu-id="f4f24-109">Öğesinden türetilen <xref:System.Xml.NameTable> sınıfı ve en büyük boyutu kotası zorlayın.</span><span class="sxs-lookup"><span data-stu-id="f4f24-109">Derive from the <xref:System.Xml.NameTable> class and enforce a maximum size quota.</span></span> <span data-ttu-id="f4f24-110">(Kullanımını engelleyemez bir <xref:System.Xml.NameTable> veya geçiş <xref:System.Xml.NameTable> olduğu zaman tam.)</span><span class="sxs-lookup"><span data-stu-id="f4f24-110">(You cannot prevent the use of a <xref:System.Xml.NameTable> or switch the <xref:System.Xml.NameTable> when it is full.)</span></span>  
  
-   <span data-ttu-id="f4f24-111">Belirtilen özellikleri kullanmaktan kaçının ve bunun yerine kullanın <xref:System.Xml.XmlReader.MoveToAttribute%2A> yöntemiyle <xref:System.Xml.XmlReader.IsStartElement%2A> yöntemi mümkün olduğunca; bu yöntemleri değil dönün dizeler ve böylece overfilling, bir sorunu önlemenize <xref:System.Xml.NameTable> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="f4f24-111">Avoid using the properties mentioned and instead use the <xref:System.Xml.XmlReader.MoveToAttribute%2A> method with the <xref:System.Xml.XmlReader.IsStartElement%2A> method where possible; those methods do not return strings and thus avoid the problem of overfilling the <xref:System.Xml.NameTable> collection.</span></span>  
  
## <a name="malicious-client-sends-excessive-license-requests-to-service"></a><span data-ttu-id="f4f24-112">Kötü amaçlı istemci aşırı lisans istekleri hizmetine gönderir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-112">Malicious Client Sends Excessive License Requests to Service</span></span>  
 <span data-ttu-id="f4f24-113">Kötü amaçlı bir istemci aşırı lisans istekleri hizmetiyle bombards, aşırı bellek kullanmak sunucunun neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-113">If a malicious client bombards a service with excessive license requests, it can cause the server to use excessive memory.</span></span>  
  
 <span data-ttu-id="f4f24-114">Azaltma: aşağıdaki özelliklerini kullanmak <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> sınıfı:</span><span class="sxs-lookup"><span data-stu-id="f4f24-114">Mitigation: Use the following properties of the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class:</span></span>  
  
-   <span data-ttu-id="f4f24-115"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxCachedCookies%2A>: saat ilişkisindeki, maksimum sayısını kontrol `SecurityContextToken`sonra sunucu önbelleğe s `SPNego` veya `SSL` anlaşma.</span><span class="sxs-lookup"><span data-stu-id="f4f24-115"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxCachedCookies%2A>: controls the maximum number of time-bounded `SecurityContextToken`s that the server caches after `SPNego` or `SSL` negotiation.</span></span>  
  
-   <span data-ttu-id="f4f24-116"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.IssuedCookieLifetime%2A>: ömrü denetimleri `SecurityContextTokens` , aşağıdaki sunucu sorunları `SPNego` veya `SSL` anlaşma.</span><span class="sxs-lookup"><span data-stu-id="f4f24-116"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.IssuedCookieLifetime%2A>: controls the lifetime of the `SecurityContextTokens` that the server issues following `SPNego` or `SSL` negotiation.</span></span> <span data-ttu-id="f4f24-117">Sunucu önbelleklerini `SecurityContextToken`s Bu süre.</span><span class="sxs-lookup"><span data-stu-id="f4f24-117">The server caches the `SecurityContextToken`s for this period of time.</span></span>  
  
-   <span data-ttu-id="f4f24-118"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxPendingSessions%2A>: sunucuda ancak hiçbir uygulama ileti işlendikten için kurulmuş güvenli konuşmaları en fazla sayısını denetler.</span><span class="sxs-lookup"><span data-stu-id="f4f24-118"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxPendingSessions%2A>: controls the maximum number of secure conversations that are established at the server but for which no application messages have been processed.</span></span> <span data-ttu-id="f4f24-119">Bu kota istemcilerin konuşması güvenli konuşmaları oluşturma, böylece istemci başına durumunu korumak üzere bir hizmetin neden, ancak hiçbir zaman kullanmadan önler.</span><span class="sxs-lookup"><span data-stu-id="f4f24-119">This quota prevents clients from establishing secure conversations at the service, thereby causing the service to maintain state per client, but never using them.</span></span>  
  
-   <span data-ttu-id="f4f24-120"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.InactivityTimeout%2A>: hizmet tutar güvenli bir konuşma Canlı istemcisinden konuşma için bir uygulama iletisi almadan en fazla süreyi denetler.</span><span class="sxs-lookup"><span data-stu-id="f4f24-120"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.InactivityTimeout%2A>:  controls the maximum time the service keeps a secure conversation alive without receiving an application message from the client for the conversation.</span></span> <span data-ttu-id="f4f24-121">Bu kota istemcilerin konuşması güvenli konuşmaları oluşturma, böylece istemci başına durumunu korumak üzere bir hizmetin neden, ancak hiçbir zaman kullanmadan önler.</span><span class="sxs-lookup"><span data-stu-id="f4f24-121">This quota prevents clients from establishing secure conversations at the service, thereby causing the service to maintain state per client, but never using them.</span></span>  
  
## <a name="wsdualhttpbinding-or-dual-custom-bindings-require-client-authentication"></a><span data-ttu-id="f4f24-122">WSDualHttpBinding veya özel çift bağlamalarını istemci kimlik doğrulaması gerektirir</span><span class="sxs-lookup"><span data-stu-id="f4f24-122">WSDualHttpBinding or Dual Custom Bindings Require Client Authentication</span></span>  
 <span data-ttu-id="f4f24-123">Varsayılan olarak, <xref:System.ServiceModel.WSDualHttpBinding> sahip güvenliği etkinleştirilmiş.</span><span class="sxs-lookup"><span data-stu-id="f4f24-123">By default, the <xref:System.ServiceModel.WSDualHttpBinding> has security enabled.</span></span> <span data-ttu-id="f4f24-124">Mümkündür, ancak, bu istemci kimlik doğrulaması tarafından devre dışı ayarı <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> özelliğine <xref:System.ServiceModel.MessageCredentialType.None>, kötü niyetli bir kullanıcı bir hizmet reddi saldırısına üçüncü bir hizmete neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-124">It is possible, however, that if the client authentication is disabled by setting the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to <xref:System.ServiceModel.MessageCredentialType.None>, a malicious user can cause a denial of service attack on a third service.</span></span> <span data-ttu-id="f4f24-125">Kötü amaçlı bir istemci bir akış üçüncü hizmet iletilerinin göndermek üzere hizmetini yönlendirebilirsiniz olduğundan bu durum oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-125">This can occur because a malicious client can direct the service to send a stream of messages to a third service.</span></span>  
  
 <span data-ttu-id="f4f24-126">Bunu azaltmak için özellik ayarlanmamışsa `None`.</span><span class="sxs-lookup"><span data-stu-id="f4f24-126">To mitigate this, do not set the property to `None`.</span></span> <span data-ttu-id="f4f24-127">Özel bağlama oluşturma bir ikili ileti deseni sahip olduğunda bu olasılığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="f4f24-127">Also be aware of this possibility when creating a custom binding that has a dual message pattern.</span></span>  
  
## <a name="auditing-event-log-can-be-filled"></a><span data-ttu-id="f4f24-128">Olay günlüğü denetleme doldurulabilir</span><span class="sxs-lookup"><span data-stu-id="f4f24-128">Auditing Event Log Can Be Filled</span></span>  
 <span data-ttu-id="f4f24-129">Kötü niyetli bir kullanıcı denetimi etkinleştirildiğini bilirse, bu saldırgan denetim girişlerini yazılmasına neden geçersiz iletileri gönderebilir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-129">If a malicious user understands that auditing is enabled, that attacker can send invalid messages that cause audit entries to be written.</span></span> <span data-ttu-id="f4f24-130">Bu şekilde denetim günlüğü dolu denetim sistemi başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="f4f24-130">If the audit log is filled in this manner, the auditing system fails.</span></span>  
  
 <span data-ttu-id="f4f24-131">Bu durumu iyileştirmek için ayarlanmış <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> özelliğine `true` ve Denetim davranışını denetlemek için Olay Görüntüleyicisi'ni özelliklerini kullanın.</span><span class="sxs-lookup"><span data-stu-id="f4f24-131">To mitigate this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true` and use the properties of the Event Viewer to control the auditing behavior.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f4f24-132">Olay günlükleri görüntüleme ve yönetme için Olay Görüntüleyicisi'ni kullanarak bkz [Olay Görüntüleyicisi'ni](http://go.microsoft.com/fwlink/?LinkId=186123).</span><span class="sxs-lookup"><span data-stu-id="f4f24-132"> using the Event Viewer to view and manage event logs, see [Event Viewer](http://go.microsoft.com/fwlink/?LinkId=186123).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f4f24-133">[Denetim](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span><span class="sxs-lookup"><span data-stu-id="f4f24-133"> [Auditing](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span></span>  
  
## <a name="invalid-implementations-of-iauthorizationpolicy-can-cause-service-hangs"></a><span data-ttu-id="f4f24-134">Geçersiz uygulamaları IAuthorizationPolicy Can neden Hizmeti kilitleniyor</span><span class="sxs-lookup"><span data-stu-id="f4f24-134">Invalid Implementations of IAuthorizationPolicy Can Cause Service Hangs</span></span>  
 <span data-ttu-id="f4f24-135">Çağırma <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> hatalı uyarlamasını yöntemi <xref:System.IdentityModel.Policy.IAuthorizationPolicy> arabirimi hizmet askıda kalmasına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-135">Calling the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> method on a faulty implementation of the <xref:System.IdentityModel.Policy.IAuthorizationPolicy> interface can cause the service to hang.</span></span>  
  
 <span data-ttu-id="f4f24-136">Azaltma: yalnızca güvenilir kodunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="f4f24-136">Mitigation: Use only trusted code.</span></span> <span data-ttu-id="f4f24-137">Diğer bir deyişle, kullanan yazılmış ve test kod veya güvenilen bir sağlayıcı gelir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-137">That is, use only code that you have written and tested, or that comes from a trusted provider.</span></span> <span data-ttu-id="f4f24-138">Güvenilmeyen uzantılarını izin verme <xref:System.IdentityModel.Policy.IAuthorizationPolicy> kodunuzu son olmadan takılı için göz önünde bulundurarak.</span><span class="sxs-lookup"><span data-stu-id="f4f24-138">Do not allow untrusted extensions of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> to be plugged into your code without due consideration.</span></span> <span data-ttu-id="f4f24-139">Bu, bir hizmet uygulamasında kullanılan tüm uzantıları uygular.</span><span class="sxs-lookup"><span data-stu-id="f4f24-139">This applies to all extensions used in a service implementation.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f4f24-140">Genişletilebilirlik noktaları kullanarak uygulama kodu ve takılı yabancı kodu arasında hiçbir ayrım yapmaz.</span><span class="sxs-lookup"><span data-stu-id="f4f24-140"> does not make any distinction between application code and foreign code that is plugged in using extensibility points.</span></span>  
  
## <a name="kerberos-maximum-token-size-may-need-resizing"></a><span data-ttu-id="f4f24-141">Yeniden boyutlandırma Kerberos en büyük simge boyutu gerekebilir</span><span class="sxs-lookup"><span data-stu-id="f4f24-141">Kerberos Maximum Token Size May Need Resizing</span></span>  
 <span data-ttu-id="f4f24-142">Bir istemci çok sayıda grupları ait olup olmadığını (yaklaşık 900 gerçek sayı grupları bağlı olarak değişir rağmen), ileti üst bilginin blok 64 kilobayt aştığında bir sorun ortaya çıkabilir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-142">If a client belongs to a large number of groups (approximately 900, although the actual number varies depending on the groups), a problem may occur when a message header's block exceeds 64 kilobytes.</span></span> <span data-ttu-id="f4f24-143">Bu durumda, Microsoft Support makalesini içinde açıklandığı gibi en yüksek Kerberos belirteci boyutunu artırabilirsiniz "[Internet Explorer Kerberos kimlik doğrulaması için IIS bağlanan bir yetersiz arabellek nedeniyle çalışmıyor](http://go.microsoft.com/fwlink/?LinkId=89176)."</span><span class="sxs-lookup"><span data-stu-id="f4f24-143">In that case, you can increase the maximum Kerberos token size, as described in the Microsoft Support article "[Internet Explorer Kerberos authentication does not work because of an insufficient buffer connecting to IIS](http://go.microsoft.com/fwlink/?LinkId=89176)."</span></span> <span data-ttu-id="f4f24-144">Ayrıca en fazla artırmanız gerekebilir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ileti büyük Kerberos belirteci uyum sağlayacak şekilde boyutu.</span><span class="sxs-lookup"><span data-stu-id="f4f24-144">You may also need to increase the maximum [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message size to accommodate the larger Kerberos token.</span></span>  
  
## <a name="autoenrollment-results-in-multiple-certificates-with-same-subject-name-for-machine"></a><span data-ttu-id="f4f24-145">Makine için aynı konu adına sahip birden çok sertifika otomatik kaydını sonuçları</span><span class="sxs-lookup"><span data-stu-id="f4f24-145">Autoenrollment Results in Multiple Certificates with Same Subject Name for Machine</span></span>  
 <span data-ttu-id="f4f24-146">*Otomatik kayıt* yeteneğini olduğu [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] kullanıcıları ve bilgisayarları sertifikalar için otomatik olarak kaydedilecek.</span><span class="sxs-lookup"><span data-stu-id="f4f24-146">*Autoenrollment* is the capability of [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] to automatically enroll users and computers for certificates.</span></span> <span data-ttu-id="f4f24-147">Bir makine özelliği etkinleştirilmiş bir etki alanında olduğunda, istemci kimlik doğrulaması hedeflenen amacı olan bir X.509 sertifikası otomatik olarak oluşturulur ve yeni bir makine katıldığı her yerel bilgisayarın kişisel sertifika deposuna eklendi Ağ.</span><span class="sxs-lookup"><span data-stu-id="f4f24-147">When a machine is on a domain with the feature enabled, an X.509 certificate with the intended purpose of client authentication is automatically created and inserted into the local computer's Personal certificates store whenever a new machine is joined to the network.</span></span> <span data-ttu-id="f4f24-148">Ancak, otomatik kayıt önbellekte oluşturduğu tüm sertifikalar aynı konu adı kullanır.</span><span class="sxs-lookup"><span data-stu-id="f4f24-148">However, autoenrollment uses the same subject name for all certificates it creates in the cache.</span></span>  
  
 <span data-ttu-id="f4f24-149">Etkisi olan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmetleri autoenrollment etki alanlarıyla açmak başarısız olabilir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-149">The impact is that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services may fail to open on domains with autoenrollment.</span></span> <span data-ttu-id="f4f24-150">Bu durum, makine tam olarak nitelenmiş etki alanı adı sistemi (DNS) adıyla birden fazla sertifika var olduğundan varsayılan hizmet X.509 kimlik bilgisi arama ölçütlerini belirsiz olabilir kaynaklanır.</span><span class="sxs-lookup"><span data-stu-id="f4f24-150">This occurs because the default service X.509 credential search criteria might be ambiguous because multiple certificates with the machine's fully qualified Domain Name System (DNS) name exist.</span></span> <span data-ttu-id="f4f24-151">Bir sertifika otomatik kaydını kaynaklanan; diğer bir kendi kendine sertifikayı olabilir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-151">One certificate originates from autoenrollment; the other might be a self-issued certificate.</span></span>  
  
 <span data-ttu-id="f4f24-152">Bunu azaltmak için üzerinde daha kesin bir arama ölçütü kullanarak tam sertifika başvuru [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="f4f24-152">To mitigate this, reference the exact certificate to use by using a more precise search criterion on the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span> <span data-ttu-id="f4f24-153">Örneğin, <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> seçeneği ve kendi benzersiz parmak izi tarafından (karma) sertifikasını belirtin.</span><span class="sxs-lookup"><span data-stu-id="f4f24-153">For example, use the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> option, and specify the certificate by its unique thumbprint (hash).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f4f24-154">Otomatik kayıt özelliğini bkz [Windows Server 2003'te sertifika otomatik kaydını](http://go.microsoft.com/fwlink/?LinkId=95166).</span><span class="sxs-lookup"><span data-stu-id="f4f24-154"> the autoenrollment feature, see [Certificate Autoenrollment in Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=95166).</span></span>  
  
## <a name="last-of-multiple-alternative-subject-names-used-for-authorization"></a><span data-ttu-id="f4f24-155">Son yetkilendirme için kullanılan birden fazla alternatif konu adları</span><span class="sxs-lookup"><span data-stu-id="f4f24-155">Last of Multiple Alternative Subject Names Used for Authorization</span></span>  
 <span data-ttu-id="f4f24-156">Birden çok alternatif konu adı, bir X.509 sertifikası içerir ve alternatif konu adı kullanarak yetkilendirmek, yetkilendirme başarısız olabileceği ender durumda.</span><span class="sxs-lookup"><span data-stu-id="f4f24-156">In the rare case when an X.509 certificate contains multiple alternative subject names, and you authorize using the alternative subject name, authorization may fail.</span></span>  
  
## <a name="protect-configuration-files-with-acls"></a><span data-ttu-id="f4f24-157">ACL'ler ile yapılandırma dosyalarını koruyun</span><span class="sxs-lookup"><span data-stu-id="f4f24-157">Protect Configuration Files with ACLs</span></span>  
 <span data-ttu-id="f4f24-158">Kod ve yapılandırma dosyaları için gerekli ve isteğe bağlı talep belirtebilirsiniz [!INCLUDE[infocard](../../../../includes/infocard-md.md)] verilen belirteçler.</span><span class="sxs-lookup"><span data-stu-id="f4f24-158">You can specify required and optional claims in code and configuration files for [!INCLUDE[infocard](../../../../includes/infocard-md.md)] issued tokens.</span></span> <span data-ttu-id="f4f24-159">Bu ilgili öğeleri de gösterilmesini sonuçlanır `RequestSecurityToken` güvenlik gönderilen iletileri hizmet belirteci.</span><span class="sxs-lookup"><span data-stu-id="f4f24-159">This results in corresponding elements being emitted in `RequestSecurityToken` messages that are sent to the security token service.</span></span> <span data-ttu-id="f4f24-160">Bir saldırgan kod veya yapılandırma gerekli veya isteğe bağlı talep kaldırmak için potansiyel olarak hedef hizmete erişim izni olmayan bir belirteç vermek için güvenlik belirteci hizmeti alma değişiklik yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f4f24-160">An attacker can modify code or configuration to remove required or optional claims, potentially getting the security token service to issue a token that does not allow access to the target service.</span></span>  
  
 <span data-ttu-id="f4f24-161">Azaltmak için: yapılandırma dosyasını değiştirmek için bilgisayara erişimi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-161">To mitigate: Require access to the computer to modify the configuration file.</span></span> <span data-ttu-id="f4f24-162">Dosya erişimi denetimi kullan yapılandırma dosyalarını güvenli hale getirmek için listeleri (ACL'ler).</span><span class="sxs-lookup"><span data-stu-id="f4f24-162">Use file access control lists (ACLs) to secure configuration files.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f4f24-163">yapılandırmasından yüklenmesi gibi kodu sağlayacak önce kodu uygulama dizini veya genel derleme önbelleği olmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-163"> requires that code be in the application directory or the global assembly cache before it will allow such code to be loaded from configuration.</span></span> <span data-ttu-id="f4f24-164">Dizin ACL dizinleri güvenliğini sağlamak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="f4f24-164">Use directory ACLs to secure directories.</span></span>  
  
## <a name="maximum-number-of-secure-sessions-for-a-service-is-reached"></a><span data-ttu-id="f4f24-165">Bir hizmet için güvenli oturumlar sayısı üst sınırına</span><span class="sxs-lookup"><span data-stu-id="f4f24-165">Maximum Number of Secure Sessions for a Service Is Reached</span></span>  
 <span data-ttu-id="f4f24-166">Bir istemci bir hizmet tarafından başarıyla doğrulandıktan ve güvenli bir oturum hizmetiyle kurulan hizmeti istemci iptal eder veya oturum süresinin sona kadar oturum izler.</span><span class="sxs-lookup"><span data-stu-id="f4f24-166">When a client is successfully authenticated by a service and a secure session is established with the service, the service keeps track of the session until the client cancels it or the session expires.</span></span> <span data-ttu-id="f4f24-167">Her kurulan oturum sınırınızı için en fazla bir hizmetle etkin eşzamanlı oturum sayısını sayar.</span><span class="sxs-lookup"><span data-stu-id="f4f24-167">Every established session counts against the limit for the maximum number of active simultaneous sessions with a service.</span></span> <span data-ttu-id="f4f24-168">Bu sınıra ulaşıldığında, yeni bir oturum hizmetle oluşturma denemesi istemcileri kadar reddedilir veya fazla etkin oturum sona veya istemci tarafından iptal edildi.</span><span class="sxs-lookup"><span data-stu-id="f4f24-168">When this limit is reached, clients that attempt to create a new session with that service are rejected until one or more active sessions expire or are canceled by a client.</span></span> <span data-ttu-id="f4f24-169">Bir istemci bir hizmet ile birden çok oturumu olabilir ve her biri bu oturumlar, sınırında sayılır.</span><span class="sxs-lookup"><span data-stu-id="f4f24-169">A client can have multiple sessions with a service, and each one of those sessions counts toward the limit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4f24-170">Durum bilgisi olan oturumlar kullandığınızda, önceki paragrafta geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="f4f24-170">When you use stateful sessions, the previous paragraph does not apply.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f4f24-171">durum bilgisi olan oturumlar, bkz: [nasıl yapılır: güvenli oturum açmak için bir güvenlik bağlamı belirteci oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="f4f24-171"> stateful sessions, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
 <span data-ttu-id="f4f24-172">Bunu azaltmak için bir oturum için en uzun kullanım ömrünü ve en fazla etkin oturum sayısı sınırı ayarlamak için <xref:System.ServiceModel.Channels.SecurityBindingElement> özelliği <xref:System.ServiceModel.Channels.SecurityBindingElement> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="f4f24-172">To mitigate this, set the limit for the maximum number of active sessions and the maximum lifetime for a session by setting the <xref:System.ServiceModel.Channels.SecurityBindingElement> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f24-173">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f4f24-173">See Also</span></span>  
 [<span data-ttu-id="f4f24-174">Güvenlik konuları</span><span class="sxs-lookup"><span data-stu-id="f4f24-174">Security Considerations</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [<span data-ttu-id="f4f24-175">Bilgilerin açığa çıkmasına</span><span class="sxs-lookup"><span data-stu-id="f4f24-175">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [<span data-ttu-id="f4f24-176">Ayrıcalık yükseltme</span><span class="sxs-lookup"><span data-stu-id="f4f24-176">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [<span data-ttu-id="f4f24-177">Hizmet reddi</span><span class="sxs-lookup"><span data-stu-id="f4f24-177">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [<span data-ttu-id="f4f24-178">Yeniden yürütme saldırıları</span><span class="sxs-lookup"><span data-stu-id="f4f24-178">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [<span data-ttu-id="f4f24-179">Oynama</span><span class="sxs-lookup"><span data-stu-id="f4f24-179">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 [<span data-ttu-id="f4f24-180">Desteklenmeyen senaryolar</span><span class="sxs-lookup"><span data-stu-id="f4f24-180">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)