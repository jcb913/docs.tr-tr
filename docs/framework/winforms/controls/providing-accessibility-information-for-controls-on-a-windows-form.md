---
title: "Bir Windows Formundaki Denetimler için Erişilebilirlik Bilgileri Sağlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d7afc8cc67dc3a428e4995230345938075fbcc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="b18f2-102">Bir Windows Formundaki Denetimler için Erişilebilirlik Bilgileri Sağlama</span><span class="sxs-lookup"><span data-stu-id="b18f2-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="b18f2-103">Erişilebilirlik yardımları özelleştirilmiş programlardır ve engelli kişilere yardımcı aygıtları bilgisayarlar daha etkili bir şekilde kullanın.</span><span class="sxs-lookup"><span data-stu-id="b18f2-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="b18f2-104">Örnek ekran okuyucular blind ve ses giriş yardımcı programları klavye ve fare kullanmak yerine sözlü komutları sağlayan kişiler için birden çok kişi için verilebilir.</span><span class="sxs-lookup"><span data-stu-id="b18f2-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="b18f2-105">Windows Forms denetimleri tarafından kullanıma sunulan erişilebilirlik özelliklerini bu erişilebilirlik yardımları etkileşim.</span><span class="sxs-lookup"><span data-stu-id="b18f2-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="b18f2-106">Bu özellikleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="b18f2-106">These properties are:</span></span>  
  
-   <span data-ttu-id="b18f2-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="b18f2-107">**AccessibilityObject**</span></span>  
  
-   <span data-ttu-id="b18f2-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="b18f2-108">**AccessibleDefaultActionDescription**</span></span>  
  
-   <span data-ttu-id="b18f2-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="b18f2-109">**AccessibleDescription**</span></span>  
  
-   <span data-ttu-id="b18f2-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="b18f2-110">**AccessibleName**</span></span>  
  
-   <span data-ttu-id="b18f2-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="b18f2-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="b18f2-112">AccessibilityObject özelliği</span><span class="sxs-lookup"><span data-stu-id="b18f2-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="b18f2-113">Bu salt okunur özelliği içeren bir <xref:System.Windows.Forms.AccessibleObject> örneği.</span><span class="sxs-lookup"><span data-stu-id="b18f2-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="b18f2-114">**AccessibleObject** uygulayan <xref:Accessibility.IAccessible> denetimin açıklaması, ekran konumu, gezinme yeteneklerini ve değer hakkında bilgi sağlayan arabirim.</span><span class="sxs-lookup"><span data-stu-id="b18f2-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="b18f2-115">Forma denetim eklendiğinde Tasarımcı bu değeri ayarlar.</span><span class="sxs-lookup"><span data-stu-id="b18f2-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="b18f2-116">AccessibleDefaultActionDescription özelliği</span><span class="sxs-lookup"><span data-stu-id="b18f2-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="b18f2-117">Bu dize denetiminin eylemi açıklar.</span><span class="sxs-lookup"><span data-stu-id="b18f2-117">This string describes the action of the control.</span></span> <span data-ttu-id="b18f2-118">Özellikler penceresinde görüntülenmez ve kodda yalnızca ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="b18f2-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="b18f2-119">Aşağıdaki örnek, bu özellik bir düğme denetimi için ayarlar:</span><span class="sxs-lookup"><span data-stu-id="b18f2-119">The following example sets this property for a button control:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
  
// C#  
Button1.AccessibleDefaultActionDescription =   
   "Closes the application.";  
  
// C++  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a><span data-ttu-id="b18f2-120">AccessibleDescription özelliği</span><span class="sxs-lookup"><span data-stu-id="b18f2-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="b18f2-121">Bu dize denetimi açıklar.</span><span class="sxs-lookup"><span data-stu-id="b18f2-121">This string describes the control.</span></span> <span data-ttu-id="b18f2-122">Bu özellikler penceresini veya kod aşağıdaki gibi ayarlanabilir:</span><span class="sxs-lookup"><span data-stu-id="b18f2-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="b18f2-123">AccessibleName özelliği</span><span class="sxs-lookup"><span data-stu-id="b18f2-123">AccessibleName Property</span></span>  
 <span data-ttu-id="b18f2-124">Erişilebilirlik yardımları bildirilen bir denetimin adıdır.</span><span class="sxs-lookup"><span data-stu-id="b18f2-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="b18f2-125">Bu özellikler penceresini veya kod aşağıdaki gibi ayarlanabilir:</span><span class="sxs-lookup"><span data-stu-id="b18f2-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="b18f2-126">AccessibleRole özelliği</span><span class="sxs-lookup"><span data-stu-id="b18f2-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="b18f2-127">Bu özellik içeren bir <xref:System.Windows.Forms.AccessibleRole> numaralandırma, denetimi kullanıcı arabirimi rolünü açıklar.</span><span class="sxs-lookup"><span data-stu-id="b18f2-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="b18f2-128">Yeni bir denetim ayarlamak değere sahip `Default`.</span><span class="sxs-lookup"><span data-stu-id="b18f2-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="b18f2-129">Bu, varsayılan olarak, anlamına gelir bir **düğmesini** denetimi olarak görev yapan bir **düğmesini**.</span><span class="sxs-lookup"><span data-stu-id="b18f2-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="b18f2-130">Başka bir rol bir denetim varsa, bu özellik sıfırlamak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b18f2-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="b18f2-131">Örneğin, kullanıyor olabileceğiniz bir **PictureBox** olarak kontrol bir **grafik**, ve rol olarak bildirmek için erişilebilirlik yardımları isteyebilirsiniz bir **grafik**, olarak değil bir **PictureBox** .</span><span class="sxs-lookup"><span data-stu-id="b18f2-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="b18f2-132">Bu özellik, geliştirdiğiniz özel denetimler için belirtmek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b18f2-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="b18f2-133">Bu özelliği Özellikler penceresini veya kod aşağıdaki gibi ayarlanabilir:</span><span class="sxs-lookup"><span data-stu-id="b18f2-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b18f2-134">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b18f2-134">See Also</span></span>  
 <xref:System.Windows.Forms.AccessibleObject>  
 <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.AccessibleRole>