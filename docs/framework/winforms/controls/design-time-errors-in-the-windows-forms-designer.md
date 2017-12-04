---
title: "Windows Formları Tasarımcısında Tasarım Zamanı Hataları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 819b624e2abac09aea804311d661f78e2a1f5a7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a><span data-ttu-id="8906a-102">Windows Formları Tasarımcısında Tasarım Zamanı Hataları</span><span class="sxs-lookup"><span data-stu-id="8906a-102">Design-Time Errors in the Windows Forms Designer</span></span>
<span data-ttu-id="8906a-103">Bu konuda, Microsoft Visual Studio ile yüklemek Windows Form Tasarımcısı başarısız olduğunda görüntülenen tasarım zamanı hata listesi kullanımını ve anlamı açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="8906a-103">This topic explains the meaning and use of the design-time error list that appears in Microsoft Visual Studio when the Windows Forms Designer fails to load.</span></span> <span data-ttu-id="8906a-104">Bu hata listesi görünüyorsa, bunu Tasarımcısı'nda bir hata, ancak kodunuzdaki hataları düzeltmek için yardımcı yorumlar değil.</span><span class="sxs-lookup"><span data-stu-id="8906a-104">If this error list appears, you should not interpret it as a bug in the designer, but as an aid to correcting errors in your code.</span></span>  
  
 <span data-ttu-id="8906a-105">Bu hata listesi temel bir anlayış hatalarla ilgili ayrıntılı bilgileri sağlayarak ve olası çözümlerini öneren uygulamalarınızda hata ayıklamak yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="8906a-105">A basic understanding of this error list will help you debug your applications by providing detailed information about the errors and suggesting possible solutions.</span></span>  
  
## <a name="the-design-time-error-list-interface"></a><span data-ttu-id="8906a-106">Tasarım zamanı hata listesi arabirimi</span><span class="sxs-lookup"><span data-stu-id="8906a-106">The Design-Time Error List Interface</span></span>  
 <span data-ttu-id="8906a-107">Windows Form Tasarımcısı yüklenmemesi durumunda bir hata listesi Tasarımcısı'nda görünür.</span><span class="sxs-lookup"><span data-stu-id="8906a-107">If the Windows Forms Designer fails to load, an error list will appear in the designer.</span></span> <span data-ttu-id="8906a-108">Hataları kategorilerde gruplanır.</span><span class="sxs-lookup"><span data-stu-id="8906a-108">The errors are grouped into categories.</span></span> <span data-ttu-id="8906a-109">Örneğin, bunlar bildirilmemiş değişkenin dört örneğini varsa, aynı hata kategoriye gruplandırılır.</span><span class="sxs-lookup"><span data-stu-id="8906a-109">For example, if you have four instances of undeclared variables, these will be grouped into the same error category.</span></span> <span data-ttu-id="8906a-110">Her hata kategorisi hata özetler kısa bir açıklama içerir.</span><span class="sxs-lookup"><span data-stu-id="8906a-110">Each error category includes a brief description that summarizes the error.</span></span>  
  
 <span data-ttu-id="8906a-111">Genişletin veya bir hata kategorisi hata kategori başlığını tıklatarak veya Genişlet/Daralt Köşeli Çift Ayraca tıklayarak daraltın.</span><span class="sxs-lookup"><span data-stu-id="8906a-111">You can expand or collapse an error category by either clicking on the error category heading or by clicking the expand/collapse chevron.</span></span> <span data-ttu-id="8906a-112">Bir hata kategorisi genişlettiğinizde, aşağıdaki ek Yardım görüntülenir:</span><span class="sxs-lookup"><span data-stu-id="8906a-112">When you expand an error category, the following additional help is displayed:</span></span>  
  
-   <span data-ttu-id="8906a-113">Bu hata örnekleri.</span><span class="sxs-lookup"><span data-stu-id="8906a-113">Instances of this error.</span></span>  
  
-   <span data-ttu-id="8906a-114">Bu hata ile yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="8906a-114">Help with this error.</span></span>  
  
-   <span data-ttu-id="8906a-115">Forum, bu hata hakkındaki gönderir.</span><span class="sxs-lookup"><span data-stu-id="8906a-115">Forum posts about this error.</span></span>  
  
### <a name="instances-of-this-error"></a><span data-ttu-id="8906a-116">Bu hata örnekleri</span><span class="sxs-lookup"><span data-stu-id="8906a-116">Instances of This Error</span></span>  
 <span data-ttu-id="8906a-117">Ek hata geçerli projenizdeki tüm örneklerini listelemek Yardım.</span><span class="sxs-lookup"><span data-stu-id="8906a-117">The additional help list all instances of the error in your current project.</span></span> <span data-ttu-id="8906a-118">Birçok hata şu biçimde kesin bir konuma içerir: *[Proje adı]* *[Form adı]* satır:*[satır numarası]* sütun:*[sütun numarası]*.</span><span class="sxs-lookup"><span data-stu-id="8906a-118">Many errors include an exact location in the following format: *[Project Name]* *[Form Name]* Line:*[Line Number]* Column:*[Column Number]*.</span></span> <span data-ttu-id="8906a-119">**Koda gitme olanağı** bağlantı kodunuzu hatanın oluştuğu konum alır.</span><span class="sxs-lookup"><span data-stu-id="8906a-119">The **Go to code** link takes you to the location in your code where the error occurs.</span></span>  
  
 <span data-ttu-id="8906a-120">Çağrı yığını şu hata ile ilişkili ise, tıklayabilirsiniz **çağrı yığını Göster** bağlantı, çağrı yığını göstermek için hata, daha fazla genişletir.</span><span class="sxs-lookup"><span data-stu-id="8906a-120">If a call stack is associated with the error, you can click the **Show Call Stack** link, which further expands the error to show the call stack.</span></span> <span data-ttu-id="8906a-121">Yığın inceleyerek hata ayıklama değerli bilgiler sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="8906a-121">Examining the stack can provide valuable debugging information.</span></span> <span data-ttu-id="8906a-122">Örneğin, bir hata oluştu önce adı veriliyordu işlevleri izleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8906a-122">For example, you can track the functions that were called before the error occurred.</span></span> <span data-ttu-id="8906a-123">Çağrı yığını seçilebilir, böylelikle kopyalayın ve kaydedin.</span><span class="sxs-lookup"><span data-stu-id="8906a-123">The call stack is selectable so that you can copy and save it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8906a-124">Visual Basic'te tasarım zamanı hata listesi birden fazla hata görüntülemez ancak birden çok örneğini aynı hatayı gösteriyor olabilir.</span><span class="sxs-lookup"><span data-stu-id="8906a-124">In Visual Basic, the design-time error list does not display more than one error, but it may display multiple instances of the same error.</span></span> <span data-ttu-id="8906a-125">Visual C++'da, hataları bağlantılar/satır numarası bağlantılar goto kodu yok.</span><span class="sxs-lookup"><span data-stu-id="8906a-125">In Visual C++, the errors do not have goto code links/line number links.</span></span>  
  
### <a name="help-with-this-error"></a><span data-ttu-id="8906a-126">Bu hata ile Yardım</span><span class="sxs-lookup"><span data-stu-id="8906a-126">Help with This Error</span></span>  
 <span data-ttu-id="8906a-127">Hata bir ilişkili MSDN Yardım konusunun bağlantısını içeriyorsa, Ek Yardım Yardım konusunun bağlantısını içerir.</span><span class="sxs-lookup"><span data-stu-id="8906a-127">If the error contains a link to an associated MSDN help topic, the additional help will include a link to the help topic.</span></span> <span data-ttu-id="8906a-128">Bağlantıya tıkladığında, ilişkili Yardım konusu Visual Studio'da görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="8906a-128">When you click the link, the associated help topic appears in Visual Studio.</span></span>  
  
### <a name="forum-posts-about-this-error"></a><span data-ttu-id="8906a-129">Bu hata hakkındaki Forumu gönderir</span><span class="sxs-lookup"><span data-stu-id="8906a-129">Forum posts about this error</span></span>  
 <span data-ttu-id="8906a-130">Ek Yardım hata ile ilgili MSDN Forumu gönderileri bağlantısını içerir.</span><span class="sxs-lookup"><span data-stu-id="8906a-130">The additional help will include a link to MSDN forum posts related to the error.</span></span> <span data-ttu-id="8906a-131">Forum, hata iletisi dizesi göre aranır.</span><span class="sxs-lookup"><span data-stu-id="8906a-131">The forums are searched based on the string of the error message.</span></span> <span data-ttu-id="8906a-132">Ayrıca, aşağıdaki forumları arama deneyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="8906a-132">You can also try searching the following forums:</span></span>  
  
-   [<span data-ttu-id="8906a-133">Windows Forms Tasarımcısı Forumu</span><span class="sxs-lookup"><span data-stu-id="8906a-133">Windows Forms Designer Forum</span></span>](http://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [<span data-ttu-id="8906a-134">Windows Forms forumları</span><span class="sxs-lookup"><span data-stu-id="8906a-134">Windows Forms Forums</span></span>](http://go.microsoft.com/fwlink/?LinkId=203523)  
  
### <a name="ignore-and-continue"></a><span data-ttu-id="8906a-135">Yoksay ve devam et</span><span class="sxs-lookup"><span data-stu-id="8906a-135">Ignore and Continue</span></span>  
 <span data-ttu-id="8906a-136">Hata koşulu yoksayıp Tasarımcı yüklemeye devam etmek seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8906a-136">You can choose to ignore the error condition and continue loading the designer.</span></span> <span data-ttu-id="8906a-137">Bu eylem seçme beklenmeyen davranışlara neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="8906a-137">Choosing this action may result in unexpected behavior.</span></span> <span data-ttu-id="8906a-138">Örneğin, denetimleri tasarım yüzeyine görünmeyebilir.</span><span class="sxs-lookup"><span data-stu-id="8906a-138">For example, controls may not appear on the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8906a-139">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8906a-139">See Also</span></span>  
 [<span data-ttu-id="8906a-140">Tasarım zamanı geliştirme sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="8906a-140">Troubleshooting Design-Time Development</span></span>](http://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [<span data-ttu-id="8906a-141">Denetim ve bileşen yazmada sorun giderme</span><span class="sxs-lookup"><span data-stu-id="8906a-141">Troubleshooting Control and Component Authoring</span></span>](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 [<span data-ttu-id="8906a-142">Windows Forms denetimleri geliştirme tasarım zamanında</span><span class="sxs-lookup"><span data-stu-id="8906a-142">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="8906a-143">Windows Form Tasarımcısı hata iletileri</span><span class="sxs-lookup"><span data-stu-id="8906a-143">Windows Forms Designer Error Messages</span></span>](http://msdn.microsoft.com/en-us/cf610bf4-5fe4-471c-bce7-6a05ece07bd2)