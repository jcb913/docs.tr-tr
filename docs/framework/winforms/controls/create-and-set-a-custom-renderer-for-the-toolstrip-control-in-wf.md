---
title: "Nasıl yapılır: Windows Forms'ta ToolStrip Denetimi için Özel Oluşturucu Oluşturma ve Ayarlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f63ff0a7336ae80ce5652cf3e4c6c7dd409882a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="1b1bd-102">Nasıl yapılır: Windows Forms'ta ToolStrip Denetimi için Özel Oluşturucu Oluşturma ve Ayarlama</span><span class="sxs-lookup"><span data-stu-id="1b1bd-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="1b1bd-103"><xref:System.Windows.Forms.ToolStrip>denetimleri, temalar ve stiller kolay destek verin.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="1b1bd-104">Ya da ayarlayarak tamamen özel görünüm ve davranış (Görünüm) gerçekleştirebilirsiniz <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> özelliği veya <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> özel Oluşturucu özelliğine.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="1b1bd-105">Her kişi için işleyiciler atayabilirsiniz <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, veya <xref:System.Windows.Forms.StatusStrip> denetim veya kullanabilirsiniz <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> ayarlayarak tüm nesneleri etkilemek için özellik <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> özelliğine <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b1bd-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>döndürür <xref:System.Windows.Forms.ToolStripRenderMode.Custom> yalnızca değerini <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> değil `null`.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="1b1bd-107">Özel oluşturucu oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="1b1bd-107">To create a custom renderer</span></span>  
  
1.  <span data-ttu-id="1b1bd-108">Genişletme <xref:System.Windows.Forms.ToolStripRenderer> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2.  <span data-ttu-id="1b1bd-109">Uygulama istenen özel işleme kılarak uygun *üzerinde...*</span><span class="sxs-lookup"><span data-stu-id="1b1bd-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="1b1bd-110">üyeler</span><span class="sxs-lookup"><span data-stu-id="1b1bd-110">members</span></span>  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="1b1bd-111">Geçerli oluşturucusu olması için özel Oluşturucu ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="1b1bd-111">To set the custom renderer to be the current renderer</span></span>  
  
1.  <span data-ttu-id="1b1bd-112">Bir özel Oluşturucu ayarlamak için <xref:System.Windows.Forms.ToolStrip>ayarlayın <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> özel Oluşturucu özelliğine.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  <span data-ttu-id="1b1bd-113">Veya tümü için özel Oluşturucu ayarlamak için <xref:System.Windows.Forms.ToolStrip> uygulamanızda bulunan sınıflar: ayarlamak <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> kümesi ve özel Oluşturucu özelliğine <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> özelliğine <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1b1bd-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>  
 [<span data-ttu-id="1b1bd-115">ToolStrip denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="1b1bd-115">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="1b1bd-116">ToolStrip denetim mimarisi</span><span class="sxs-lookup"><span data-stu-id="1b1bd-116">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="1b1bd-117">ToolStrip Teknoloiji özeti</span><span class="sxs-lookup"><span data-stu-id="1b1bd-117">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)