---
title: 100 - WorkflowInstanceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed4d1851-b378-489b-a22d-c1db09571fb4
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b22ccea1130b4f2c9a1d60d8e4e0218fecaf7afb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="100---workflowinstancerecord"></a><span data-ttu-id="11a86-102">100 - WorkflowInstanceRecord</span><span class="sxs-lookup"><span data-stu-id="11a86-102">100 - WorkflowInstanceRecord</span></span>
## <a name="properties"></a><span data-ttu-id="11a86-103">Özellikler</span><span class="sxs-lookup"><span data-stu-id="11a86-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11a86-104">Kimliği</span><span class="sxs-lookup"><span data-stu-id="11a86-104">Id</span></span>|<span data-ttu-id="11a86-105">100</span><span class="sxs-lookup"><span data-stu-id="11a86-105">100</span></span>|  
|<span data-ttu-id="11a86-106">Anahtar Sözcükler</span><span class="sxs-lookup"><span data-stu-id="11a86-106">Keywords</span></span>|<span data-ttu-id="11a86-107">Sorun giderme, ögesi, WFTracking EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="11a86-107">EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="11a86-108">Düzey</span><span class="sxs-lookup"><span data-stu-id="11a86-108">Level</span></span>|<span data-ttu-id="11a86-109">Bilgiler</span><span class="sxs-lookup"><span data-stu-id="11a86-109">Information</span></span>|  
|<span data-ttu-id="11a86-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="11a86-110">Channel</span></span>|<span data-ttu-id="11a86-111">Microsoft Windows uygulama sunucusu-uygulamalar/analitik</span><span class="sxs-lookup"><span data-stu-id="11a86-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="11a86-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="11a86-112">Description</span></span>  
 <span data-ttu-id="11a86-113">Bir iş akışı örneği iş akışı durumlarını WorkflowInstanceRecord yayar, bu olay ETW İzleme katılımcı tarafından gösterilen: başlatıldı, sürdürüldü, kalıcı, boşta, silinen, tamamlandı, iptal, kaldırıldığında, Unsuspended.</span><span class="sxs-lookup"><span data-stu-id="11a86-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceRecord for workflow states : Started, Resumed, Persisted, Idle, Deleted, Completed, Canceled, Unloaded, Unsuspended.</span></span>  
  
## <a name="message"></a><span data-ttu-id="11a86-114">İleti</span><span class="sxs-lookup"><span data-stu-id="11a86-114">Message</span></span>  
 <span data-ttu-id="11a86-115">TrackRecord WorkflowInstanceRecord, örnek kimliği = %1, kayıt numarası = = %2, EventTime = %3, ActivityDefinitionId = %4, durum = %5, ek açıklamaları = %6, ProfileName = %7</span><span class="sxs-lookup"><span data-stu-id="11a86-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7</span></span>  
  
## <a name="details"></a><span data-ttu-id="11a86-116">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="11a86-116">Details</span></span>  
  
|<span data-ttu-id="11a86-117">Veri öğesi adı</span><span class="sxs-lookup"><span data-stu-id="11a86-117">Data Item Name</span></span>|<span data-ttu-id="11a86-118">Veri öğesi türü</span><span class="sxs-lookup"><span data-stu-id="11a86-118">Data Item Type</span></span>|<span data-ttu-id="11a86-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="11a86-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="11a86-120">örnek kimliği</span><span class="sxs-lookup"><span data-stu-id="11a86-120">InstanceId</span></span>|<span data-ttu-id="11a86-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="11a86-121">xs:GUID</span></span>|<span data-ttu-id="11a86-122">İş akışı için örnek kimliği</span><span class="sxs-lookup"><span data-stu-id="11a86-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="11a86-123">Kayıt numarası</span><span class="sxs-lookup"><span data-stu-id="11a86-123">RecordNumber</span></span>|<span data-ttu-id="11a86-124">xs:Long</span><span class="sxs-lookup"><span data-stu-id="11a86-124">xs:long</span></span>|<span data-ttu-id="11a86-125">Verilmiş kaydı sıra sayısı</span><span class="sxs-lookup"><span data-stu-id="11a86-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="11a86-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="11a86-126">EventTime</span></span>|<span data-ttu-id="11a86-127">xs: DateTime</span><span class="sxs-lookup"><span data-stu-id="11a86-127">xs:dateTime</span></span>|<span data-ttu-id="11a86-128">Olay gösterilen zaman UTC zamanı</span><span class="sxs-lookup"><span data-stu-id="11a86-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="11a86-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="11a86-129">ActivityDefinitionId</span></span>|<span data-ttu-id="11a86-130">xs: String</span><span class="sxs-lookup"><span data-stu-id="11a86-130">xs:string</span></span>|<span data-ttu-id="11a86-131">İş akışı Kök etkinlik adı</span><span class="sxs-lookup"><span data-stu-id="11a86-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="11a86-132">Durum</span><span class="sxs-lookup"><span data-stu-id="11a86-132">State</span></span>|<span data-ttu-id="11a86-133">xs: String</span><span class="sxs-lookup"><span data-stu-id="11a86-133">xs:string</span></span>|<span data-ttu-id="11a86-134">İş akışının geçerli durumu.</span><span class="sxs-lookup"><span data-stu-id="11a86-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="11a86-135">Ek Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="11a86-135">Annotations</span></span>|<span data-ttu-id="11a86-136">xs: String</span><span class="sxs-lookup"><span data-stu-id="11a86-136">xs:string</span></span>|<span data-ttu-id="11a86-137">Bu olay için eklenen ek açıklamalar.</span><span class="sxs-lookup"><span data-stu-id="11a86-137">The annotations that were added to this event.</span></span>  <span data-ttu-id="11a86-138">Değerleri bir xml öğesi biçimde depolanır \<öğeleri >\< öğe adı "annotationName" type="System.String =" > annotationValue\</Madde > \< /öğelerini >.</span><span class="sxs-lookup"><span data-stu-id="11a86-138">The values are stored in an xml element in the format \<items>\< item  name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span>  <span data-ttu-id="11a86-139">Ek açıklama dizesi içeriyorsa belirtilmişse \<öğeleri / >.</span><span class="sxs-lookup"><span data-stu-id="11a86-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="11a86-140">ETW olay boyutu ETW arabellek boyutu veya bir ETW olayı için en fazla yükü sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="11a86-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="11a86-141">Olay boyutu ETW sınırlarını aşıyor sonra olay ek açıklamalar bırakarak ve ek açıklama değeri ile değiştirerek kesilir \<öğeleri >...  \< /öğelerini >.</span><span class="sxs-lookup"><span data-stu-id="11a86-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="11a86-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="11a86-142">ProfileName</span></span>|<span data-ttu-id="11a86-143">xs: String</span><span class="sxs-lookup"><span data-stu-id="11a86-143">xs:string</span></span>|<span data-ttu-id="11a86-144">Adı veya gösterilmesini bu olay sonuçlandı izleme profili</span><span class="sxs-lookup"><span data-stu-id="11a86-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="11a86-145">HostReference</span><span class="sxs-lookup"><span data-stu-id="11a86-145">HostReference</span></span>|<span data-ttu-id="11a86-146">xs: String</span><span class="sxs-lookup"><span data-stu-id="11a86-146">xs:string</span></span>|<span data-ttu-id="11a86-147">Bu alan, barındırılan web hizmetleri için web hiyerarşi hizmetinde benzersiz olarak tanımlar.</span><span class="sxs-lookup"><span data-stu-id="11a86-147">For web hosted services, this field uniquely identifies the service in the web hierarchy.</span></span>  <span data-ttu-id="11a86-148">Biçimi olarak tanımlanan ' Web sitesi adı uygulamanın sanal yolu &#124; Hizmet sanal yolu &#124; ServiceName' örnek: ' varsayılan Web sitesi/CalculatorApplication, #124;/CalculatorService.svc &#124; CalculatorService'</span><span class="sxs-lookup"><span data-stu-id="11a86-148">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName' Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'</span></span>|  
|<span data-ttu-id="11a86-149">AppDomain</span><span class="sxs-lookup"><span data-stu-id="11a86-149">AppDomain</span></span>|<span data-ttu-id="11a86-150">xs: String</span><span class="sxs-lookup"><span data-stu-id="11a86-150">xs:string</span></span>|<span data-ttu-id="11a86-151">AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.</span><span class="sxs-lookup"><span data-stu-id="11a86-151">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|