---
title: 'Nasıl yapılır: Durum Çubuğu Panellerinin Boyutunu Ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- StatusBar control [Windows Forms], panel size
- status bars [Windows Forms], setting panel size
- panels [Windows Forms], setting size in status bars
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
ms.openlocfilehash: d708b94d02b4f1c1e2f00101e6e394043a6057ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533786"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a>Nasıl yapılır: Durum Çubuğu Panellerinin Boyutunu Ayarlama
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripStatusLabel> Denetimi değiştirir ve işlevlerini ekler <xref:System.Windows.Forms.StatusBar> kontrol; ancak, <xref:System.Windows.Forms.StatusBar> denetim tutulur geriye dönük uyumluluk ve gelecekte kullanım için seçerseniz.  
  
 Her örneği <xref:System.Windows.Forms.StatusBarPanel> içinde sınıf bir [StatusBar denetimi](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) kontrolünde genişliğini belirlemek ve çalışma zamanında yeniden boyutlandırma davranışı dinamik özellik sayısı.  
  
### <a name="to-set-the-size-of-a-panel"></a>Bir panel boyutunu ayarlamak için  
  
1.  Bir yordamda ayarladığınız <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, ve <xref:System.Windows.Forms.StatusBarPanel.Width%2A> özellikleri (veya bunların bir alt okuduğunuzu) için durum çubuğunu kendi dizini kullanılarak paneller geçtiğini <xref:System.Windows.Forms.StatusBar.Panels%2A> özelliği <xref:System.Windows.Forms.StatusBarPanel> koleksiyonu.  
  
    ```vb  
    Public Sub SetStatusBarPanelSize()  
    ' Create panel and set text property.  
       StatusBar1.Panels.Add("One")  
    ' Set properties of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(0).Width = 200  
    ' Enable the StatusBar control to display panels.  
       StatusBar1.ShowPanels = True  
        End Sub  
    ```  
  
    ```csharp  
    public void SetStatusBarPanelSize()  
    {  
       // Create panel and set text property.  
       statusBar1.Panels.Add("One");  
       // Set properties of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[0].Width = 200;  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void SetStatusBarPanelSize()  
       {  
          // Create panel and set text property.  
          statusBar1->Panels->Add("One");  
          // Set properties of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[0]->Width = 200;  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [İzlenecek yol: Çalışma Zamanında Durum Çubuğu Bilgilerini Güncelleştirme](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [Nasıl yapılır: Windows Forms StatusBar Denetiminde Hangi Panele Tıklandığını Belirleme](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [StatusBar Denetimine Genel Bakış](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
