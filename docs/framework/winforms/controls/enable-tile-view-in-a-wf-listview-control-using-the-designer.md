---
title: 'Nasıl yapılır: Tasarımcı Kullanarak Windows Formları ListView Denetiminde Döşeme Görünümünü Etkinleştirme'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 836d82930c7ff41e7a4ae64a577baa5f1ba780c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528924"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Nasıl yapılır: Tasarımcı Kullanarak Windows Formları ListView Denetiminde Döşeme Görünümünü Etkinleştirme
Döşeme görünümü özelliği <xref:System.Windows.Forms.ListView> denetim, grafik ve metin bilgi arasında görsel bir denge sağlamanıza olanak tanır. Döşeme görünümde bir öğe için görüntülenen metin bilgileri, ayrıntı görünümü için tanımlanan sütun bilgileri ile aynıdır. Döşeme görünümü işlevleri gruplandırma veya ekleme ile birlikte işaretlemek özelliklerinde <xref:System.Windows.Forms.ListView> denetim.  
  
 Döşeme görünümü 32 x 32 bir simge ve birkaç satırlık metin, aşağıdaki görüntüde gösterildiği gibi kullanır.  
  
 ![Görünüm ListView denetiminde döşeme](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Döşeme görünümü özellikleri ve yöntemleri, her öğe için görüntülenecek ve topluca boyutunu ve döşeme görünümü penceresi içindeki tüm öğeler görünümünü denetlemek için hangi sütun alanlarını belirtmenize olanak verir. Daha anlaşılır olması için bir kutucukta metnin ilk satırını her zaman öğesi'nin adıdır; değiştirilemez.  
  
 Aşağıdaki yordam gerektiren bir **Windows uygulaması** içeren bir form ile proje bir <xref:System.Windows.Forms.ListView> denetim. Böyle bir proje ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir Windows uygulaması projesi oluşturduğunuzda](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) ve [nasıl yapılır: Windows Forms denetimlerine ekleme](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Döşeme görünümü yalnızca kullanılabilir [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] uygulamanızı çağırdığında <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> yöntemi. Önceki işletim sistemlerinde döşeme görünümüne ilgili herhangi bir kod herhangi bir etkisi olmaz ve <xref:System.Windows.Forms.ListView> denetimi büyük simge görünümünü görüntüler. Daha fazla bilgi için bkz. <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.  
>   
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-tile-view-in-the-designer"></a>Döşeme görünümü Tasarımcısı'nda ayarlamak için  
  
1.  Seçin <xref:System.Windows.Forms.ListView> formunuzda denetim.  
  
2.  İçinde **özellikleri** penceresinde, seçin <xref:System.Windows.Forms.ListView.View%2A> özelliği ve **döşeme**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [Windows XP özellikleri ve Windows Forms denetimleri](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [ListView Denetimine Genel Bakış](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
