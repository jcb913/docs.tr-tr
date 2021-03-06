---
title: Üç Grafik Hizmeti Kategorisi
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: 5621a2c0bba2e922e62006feba9ca0381181c780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525053"
---
# <a name="three-categories-of-graphics-services"></a>Üç Grafik Hizmeti Kategorisi
Windows Forms'ta grafik teklifleri aşağıdaki üç ana kategoriye ayrılır:  
  
-   İki boyutlu (2-D) vektör grafikleri  
  
-   Görüntü oluşturma  
  
-   Tipografi  
  
## <a name="2-d-vector-graphics"></a>2B vektör grafikleri  
 İki boyutlu vektör grafikleri temelleri; yine de uygun istiyor musunuz? çizgiler, eğriler ve şekiller gibi; Bu, koordinat sistemi noktalarında kümesi tarafından belirtilir. Örneğin, bir çizgide kendi iki uç noktaları tarafından belirtilir ve bir dikdörtgen konumu, sol üst köşe ve genişlik ve yükseklik vermiş numaraları çifti vermiş bir noktası tarafından belirtilir. Basit bir yol düz çizgilerle bağlı noktalar dizisi belirtilir. Bir Bézier eğrisi dört denetim noktaları tarafından belirtilen karmaşık bir eğri ' dir.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sınıfları ve temelleri hakkında bilgi depolamak yapıları, temelleri nasıl düzenleneceği hakkında bilgi depolamak sınıfları ve gerçekte çizimi yapmak sınıfları sağlar. Örneğin, <xref:System.Drawing.Rectangle> yapısı depolayan bir dikdörtgen; boyutunu ve konumunu <xref:System.Drawing.Pen> sınıfı çizgi rengi, çizgi genişliğini ve çizgi stilini; hakkında bilgi depolar ve <xref:System.Drawing.Graphics> sınıfına sahip çizim satırlar, dikdörtgenler, yollar, yöntemleri ve diğer şekiller. Vardır de birkaç <xref:System.Drawing.Brush> hakkında bilgi depolamak sınıfları kapalı şekiller ve yollar renk veya desen ile doldurulur.  
  
 Bir dizi grafik komutları da vektör görüntü meta dosyası kaydedebilirsiniz. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sağlar <xref:System.Drawing.Imaging.Metafile> kaydı, görüntüleme ve meta dosyaları kaydetme sınıfı. İle <xref:System.Drawing.Imaging.MetafileHeader> ve <xref:System.Drawing.Imaging.MetaHeader> sınıfları, meta dosyası üstbilgisinde depolanan verileri incelemek.  
  
## <a name="imaging"></a>Görüntü oluşturma  
 Belirli türde bir resim güç veya imkansız vektör grafikleri teknikleri ile görüntülemek. Örneğin, araç çubuğu düğmelerini üzerindeki resimler ve simgeler görünür resimler çizgiler ve eğrilerle koleksiyonları belirtmek zordur. Kalabalık Beyzbol stadyum yüksek çözünürlüklü dijital fotoğrafını vektör teknikleri ile oluşturmak daha da zor olabilir. Görüntüleri bu tür diziler ekranında noktalar tek tek renkleri temsil eden sayı olan bit eşlemler olarak depolanır. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sağlar <xref:System.Drawing.Bitmap> görüntüleme, düzenleme ve bit eşlemleri kaydetme sınıfı.  
  
## <a name="typography"></a>Tipografi  
 Tipografi metni yazı tiplerini, boyutlarını ve stiller çeşitli görüntüdür. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Bu karmaşık görev için kapsamlı destek sağlar. ' Deki yeni özelliklerin biri [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] metin verir piksel düzgünleştirme LCD ekranında daha sorunsuz bir görünüm oluşturulur.  
  
 Ayrıca, Windows Forms ile metin çizme seçeneği sunar [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] yetenekleri kendi <xref:System.Windows.Forms.TextRenderer> sınıfı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafiklere Genel Bakış](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [GDI+ Yönetilen Kodu Hakkında](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [Yönetilen Grafik Sınıflarını Kullanma](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
