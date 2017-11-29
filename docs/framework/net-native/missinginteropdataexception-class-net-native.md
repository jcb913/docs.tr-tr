---
title: "MissingInteropDataException Sınıfı (.NET Yerel)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: eab4bcf8-9f5f-4731-87d8-842748a6062a
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0a7e1c02b6404f9511032d18f260726d1493d202
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="missinginteropdataexception-class-net-native"></a><span data-ttu-id="e7a97-102">MissingInteropDataException Sınıfı (.NET Yerel)</span><span class="sxs-lookup"><span data-stu-id="e7a97-102">MissingInteropDataException Class (.NET Native)</span></span>
<span data-ttu-id="e7a97-103">**Windows 10, Windows uygulamaları için .NET [!INCLUDE[net_native](../../../includes/net-native-md.md)] yalnızca**</span><span class="sxs-lookup"><span data-stu-id="e7a97-103">**.NET for Windows apps for Windows 10, [!INCLUDE[net_native](../../../includes/net-native-md.md)] only**</span></span>  
  
 <span data-ttu-id="e7a97-104">Yöntemi hazırlama el ile çağrıldı, ancak meta veri türü için statik çözümleme tarafından veya bir çalışma zamanı yönergeleri dosyasında bulunamadığını zaman oluşturulur özel durum.</span><span class="sxs-lookup"><span data-stu-id="e7a97-104">The exception that is thrown when a manual marshaling method is called, but metadata for a type isn't found by static analysis or in a runtime directives file.</span></span>  
  
 <span data-ttu-id="e7a97-105">**Namespace:** System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="e7a97-105">**Namespace:** System.Runtime.CompilerServices</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e7a97-106">`MissingInteropDataException` Sınıfı içindir yalnızca tarafından dahili kullanımla [!INCLUDE[net_native](../../../includes/net-native-md.md)] araç zinciri.</span><span class="sxs-lookup"><span data-stu-id="e7a97-106">The `MissingInteropDataException` class is intended solely for internal use by the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain.</span></span> <span data-ttu-id="e7a97-107">Üçüncü taraf kodu kullanmak için hedeflenmemiş ya da özel durum, uygulama kodunuzda işlemelidir.</span><span class="sxs-lookup"><span data-stu-id="e7a97-107">It is not intended for use in third-party code, nor should you handle the exception in your application code.</span></span> <span data-ttu-id="e7a97-108">Bunun yerine, girişlere ekleyerek özel durum ortadan, [çalışma zamanı yönergeleri dosya](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="e7a97-108">Instead, you eliminate the exception by adding entries to your [runtime directives file](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span> <span data-ttu-id="e7a97-109">Daha fazla bilgi için Açıklamalar bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="e7a97-109">For more information, see the Remarks section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a97-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e7a97-110">Syntax</span></span>  
 [!code-csharp[ProjectN#21](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missinginteropdataexception_syntax1.cs#21)]
 [!code-vb[ProjectN#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/projectn/vb/missinginteropdataexception_syntax1.vb#21)]  
  
 <span data-ttu-id="e7a97-111">`MissingInteropDataException` Sınıfı aşağıdaki üyeleri sahiptir:</span><span class="sxs-lookup"><span data-stu-id="e7a97-111">The `MissingInteropDataException` class has the following members:</span></span>  
  
## <a name="constructors"></a><span data-ttu-id="e7a97-112">Oluşturucular</span><span class="sxs-lookup"><span data-stu-id="e7a97-112">Constructors</span></span>  
  
|<span data-ttu-id="e7a97-113">Oluşturucu</span><span class="sxs-lookup"><span data-stu-id="e7a97-113">Constructor</span></span>|<span data-ttu-id="e7a97-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e7a97-114">Description</span></span>|  
|-----------------|-----------------|  
|`public MissingInteropDataException(String resourceId, Type pertinentType)`|<span data-ttu-id="e7a97-115">Yeni bir örneğini başlatır `MissingInteropDataException` hata ve verileri eksik türü açıklayan sistem tarafından sağlanmış bir ileti kimliği kullanarak sınıfı.</span><span class="sxs-lookup"><span data-stu-id="e7a97-115">Initializes a new instance of the `MissingInteropDataException` class by using the ID of a system-supplied message that describes the error and the type whose data is missing.</span></span> <span data-ttu-id="e7a97-116">Bu oluşturucu tarafından dahili kullanımla ilgili olduğu [!INCLUDE[net_native](../../../includes/net-native-md.md)] aracı yalnızca zinciri.</span><span class="sxs-lookup"><span data-stu-id="e7a97-116">This constructor is for internal use by the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain only.</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="e7a97-117">Özellikler</span><span class="sxs-lookup"><span data-stu-id="e7a97-117">Properties</span></span>  
  
|<span data-ttu-id="e7a97-118">Özellik</span><span class="sxs-lookup"><span data-stu-id="e7a97-118">Property</span></span>|<span data-ttu-id="e7a97-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e7a97-119">Description</span></span>|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|<span data-ttu-id="e7a97-120">Ek kullanıcı tanımlı özel durumla ilgili bilgiler anahtar/değer çiftleri koleksiyonu alır.</span><span class="sxs-lookup"><span data-stu-id="e7a97-120">Gets a collection of key/value pairs that provide additional user-defined information about the exception.</span></span> <span data-ttu-id="e7a97-121">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-121">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public string HelpLink { get; set; }`|<span data-ttu-id="e7a97-122">Alır veya bu özel durumla ilgili Yardım dosyası için bir bağlantı ayarlar.</span><span class="sxs-lookup"><span data-stu-id="e7a97-122">Gets or sets a link to the help file associated with this exception.</span></span> <span data-ttu-id="e7a97-123">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-123">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public int HResult { get; protected set; }`|<span data-ttu-id="e7a97-124">Alır veya ayarlar `HRESULT`, belirli bir özel durum atanan kodlanmış bir sayısal değer olduğu.</span><span class="sxs-lookup"><span data-stu-id="e7a97-124">Gets or sets the `HRESULT`, which is a coded numeric value that is assigned to a specific exception.</span></span> <span data-ttu-id="e7a97-125">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-125">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public Exception InnerException { get; }`|<span data-ttu-id="e7a97-126">Geçerli özel durumun nedeni özel durumu alır.</span><span class="sxs-lookup"><span data-stu-id="e7a97-126">Gets the exception that caused the current exception.</span></span> <span data-ttu-id="e7a97-127">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-127">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public string Message { get; }`|<span data-ttu-id="e7a97-128">Geçerli özel durumu açıklayan bir ileti alır.</span><span class="sxs-lookup"><span data-stu-id="e7a97-128">Gets a message that describes the current exception.</span></span> <span data-ttu-id="e7a97-129">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-129">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public Type MissingType { get; private set; }`|<span data-ttu-id="e7a97-130">Türünü alır veya verileri eksik ayarlar.</span><span class="sxs-lookup"><span data-stu-id="e7a97-130">Gets or sets the type whose data is missing.</span></span>|  
|`public string Source { get; set; }`|<span data-ttu-id="e7a97-131">Alır veya uygulama veya hataya nesnesinin adını ayarlar.</span><span class="sxs-lookup"><span data-stu-id="e7a97-131">Gets or sets the name of the app or object that caused the error.</span></span> <span data-ttu-id="e7a97-132">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-132">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public string StackTrace { get; }`|<span data-ttu-id="e7a97-133">Çağrı yığınındaki hemen çerçeveler dize gösterimini alır.</span><span class="sxs-lookup"><span data-stu-id="e7a97-133">Gets a string representation of the immediate frames on the call stack.</span></span> <span data-ttu-id="e7a97-134">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-134">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public MethodBase TargetSite { get; }`|<span data-ttu-id="e7a97-135">Geçerli bir özel durum belirtti yöntemi alır.</span><span class="sxs-lookup"><span data-stu-id="e7a97-135">Gets the method that threw the current exception.</span></span> <span data-ttu-id="e7a97-136">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-136">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
  
## <a name="methods"></a><span data-ttu-id="e7a97-137">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="e7a97-137">Methods</span></span>  
  
|<span data-ttu-id="e7a97-138">Yöntem</span><span class="sxs-lookup"><span data-stu-id="e7a97-138">Method</span></span>|<span data-ttu-id="e7a97-139">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e7a97-139">Description</span></span>|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|<span data-ttu-id="e7a97-140">Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.</span><span class="sxs-lookup"><span data-stu-id="e7a97-140">Determines whether the specified object is equal to the current object.</span></span>  <span data-ttu-id="e7a97-141">(Devralınan <xref:System.Object>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-141">(Inherited from <xref:System.Object>.)</span></span>|  
|`protected void Finalize()`|<span data-ttu-id="e7a97-142">Kaynakları serbest ve atık toplama tarafından alınmadan önce diğer temizleme işlemleri gerçekleştirmek denemek bir nesne sağlar.</span><span class="sxs-lookup"><span data-stu-id="e7a97-142">Allows an object to try to free resources and perform other cleanup operations before it is reclaimed by garbage collection.</span></span> <span data-ttu-id="e7a97-143">(Devralınan <xref:System.Object>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-143">(Inherited from <xref:System.Object>.)</span></span>|  
|`public Exception GetBaseException()`|<span data-ttu-id="e7a97-144">Bir veya daha fazla sonraki özel kök nedenini özel durum döndürür.</span><span class="sxs-lookup"><span data-stu-id="e7a97-144">Returns the exception that is the root cause of one or more subsequent exceptions.</span></span> <span data-ttu-id="e7a97-145">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-145">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public int GetHashCode()`|<span data-ttu-id="e7a97-146">Bir karma kodu döndürür bir `MissingInteropDataException` örneği.</span><span class="sxs-lookup"><span data-stu-id="e7a97-146">Returns a hash code for a `MissingInteropDataException` instance.</span></span>   <span data-ttu-id="e7a97-147">(Devralınan <xref:System.Object>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-147">(Inherited from <xref:System.Object>.)</span></span>|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|<span data-ttu-id="e7a97-148">Ayarlar bir <xref:System.Runtime.Serialization.SerializationInfo> özel durum hakkında bilgi içeren nesne.</span><span class="sxs-lookup"><span data-stu-id="e7a97-148">Sets a <xref:System.Runtime.Serialization.SerializationInfo> object with information about the exception.</span></span>  <span data-ttu-id="e7a97-149">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-149">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`public Type GetType()`|<span data-ttu-id="e7a97-150">Geçerli örneğin çalışma zamanı türünü alır.</span><span class="sxs-lookup"><span data-stu-id="e7a97-150">Gets the runtime type of the current instance.</span></span> <span data-ttu-id="e7a97-151">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-151">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
|`protected Object MemberwiseClone()`|<span data-ttu-id="e7a97-152">Geçerli nesne basit bir kopyasını oluşturur.</span><span class="sxs-lookup"><span data-stu-id="e7a97-152">Creates a shallow copy of the current object.</span></span> <span data-ttu-id="e7a97-153">(Devralınan <xref:System.Object>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-153">(Inherited from <xref:System.Object>.)</span></span>|  
|`public string ToString()`|<span data-ttu-id="e7a97-154">Geçerli özel durumun dize gösterimini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e7a97-154">Returns the string representation of the current exception.</span></span> <span data-ttu-id="e7a97-155">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-155">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
  
## <a name="events"></a><span data-ttu-id="e7a97-156">Olaylar</span><span class="sxs-lookup"><span data-stu-id="e7a97-156">Events</span></span>  
  
|<span data-ttu-id="e7a97-157">Olay</span><span class="sxs-lookup"><span data-stu-id="e7a97-157">Event</span></span>|<span data-ttu-id="e7a97-158">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e7a97-158">Description</span></span>|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|<span data-ttu-id="e7a97-159">Bir özel durum seri içeren bir özel durum nesnesi oluşturmak için veri özel durumla ilgili serileştirilmiş oluşur.</span><span class="sxs-lookup"><span data-stu-id="e7a97-159">Occurs when an exception is serialized to create an exception state object that contains serialized data about the exception.</span></span> <span data-ttu-id="e7a97-160">(Devralınan <xref:System.Exception?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e7a97-160">(Inherited from <xref:System.Exception?displayProperty=nameWithType>.)</span></span>|  
  
## <a name="usage-details"></a><span data-ttu-id="e7a97-161">Kullanım ayrıntıları</span><span class="sxs-lookup"><span data-stu-id="e7a97-161">Usage Details</span></span>  
 <span data-ttu-id="e7a97-162">`MissingInteropDataException` Türü bilgileri kullanılamadığı için bir COM veya Windows çalışma zamanı bileşeni için bir yöntem çağrısı başarıyla yapılamaz, özel durum.</span><span class="sxs-lookup"><span data-stu-id="e7a97-162">The `MissingInteropDataException` exception is thrown when a method call to a COM or Windows Runtime component cannot be made successfully because type information isn't available.</span></span>  
  
 <span data-ttu-id="e7a97-163">Çalışma zamanında bir uygulama için kullanılabilir meta veri çalışma zamanı yönergeleri (XML yapılandırması) dosyası tarafından tanımlanan *. rd.xml.</span><span class="sxs-lookup"><span data-stu-id="e7a97-163">The metadata that is available to an app at run time is defined by the runtime directives (XML configuration) file, *.rd.xml.</span></span> <span data-ttu-id="e7a97-164">Bu özel durum atma uygulamanızı önlemek için çalışma zamanında bulunmalıdır meta verileri tanımlamak için bu dosyayı değiştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e7a97-164">To prevent your app from throwing this exception, you must modify this file to define the metadata that must be present at run time.</span></span> <span data-ttu-id="e7a97-165">En yaygın olarak ekleyerek bu hatayı gidermek bir `MarshalObject`, `MarshalDelegate`, veya `MarshalStructure` uygun bir program öğesi çalışma zamanı yönergeleri dosyasında özniteliği.</span><span class="sxs-lookup"><span data-stu-id="e7a97-165">Most commonly, you address this error by adding a `MarshalObject`, `MarshalDelegate`, or `MarshalStructure` attribute to an appropriate program element in the runtime directives file.</span></span> <span data-ttu-id="e7a97-166">Bu dosya biçimi hakkında daha fazla bilgi için bkz: [çalışma zamanı yönergeleri (rd.xml) yapılandırma dosyası başvurusu](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="e7a97-166">For information about the format of this file, see [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e7a97-167">Bu durum, uygulamanız tarafından gerekli meta verilerin çalışma zamanında kullanılamaz gösterir olduğundan, bu özel durum işleme döndürmemelidir bir `try` / `catch` bloğu.</span><span class="sxs-lookup"><span data-stu-id="e7a97-167">Because this exception indicates that metadata needed by your application isn’t available at run time, you shouldn’t handle this exception in a `try`/`catch` block.</span></span> <span data-ttu-id="e7a97-168">Bunun yerine, özel durumun nedeni tanılamanıza ve uygun girdiyi bir çalışma zamanı yönergeleri dosyasına ekleyerek ortadan kaldırmak.</span><span class="sxs-lookup"><span data-stu-id="e7a97-168">Instead, you should diagnose the cause of the exception and eliminate it by adding the appropriate entry to a runtime directives file.</span></span>  
  
 <span data-ttu-id="e7a97-169">`MissingInteropDataException` Sınıfı içeren tek bir benzersiz üye `MissingType` olan meta veri başarılı yöntem çağrısı için gereken türünü gösteren özelliği.</span><span class="sxs-lookup"><span data-stu-id="e7a97-169">The `MissingInteropDataException` class contains a single unique member, the `MissingType` property, that indicates the type whose metadata is needed for a successful method call.</span></span> <span data-ttu-id="e7a97-170">Tüm kalan üyeleri taban sınıfından devralınır <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7a97-170">All remaining members are inherited from the base class, <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a97-171">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e7a97-171">See Also</span></span>  
 <xref:System.Exception?displayProperty=nameWithType>  
 [<span data-ttu-id="e7a97-172">MissingMetadataException sınıfı</span><span class="sxs-lookup"><span data-stu-id="e7a97-172">MissingMetadataException Class</span></span>](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)  
 [<span data-ttu-id="e7a97-173">Çalışma zamanı yönergeleri (rd.xml) yapılandırma dosyası başvurusu</span><span class="sxs-lookup"><span data-stu-id="e7a97-173">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)