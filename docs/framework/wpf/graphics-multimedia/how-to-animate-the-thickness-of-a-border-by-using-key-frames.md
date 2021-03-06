---
title: 'Nasıl yapılır: Anahtar Çerçeveler Kullanarak Kenarlık Kalınlığına Animasyon Ekleme'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 3081bff4cc3f05593d644121fbaff58bb652151b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560808"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Nasıl yapılır: Anahtar Çerçeveler Kullanarak Kenarlık Kalınlığına Animasyon Ekleme
Bu örnek animasyon gösterilmektedir <xref:System.Windows.Controls.Control.BorderThickness%2A> özelliği bir <xref:System.Windows.Controls.Border>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> animasyon sınıfı <xref:System.Windows.Controls.Control.BorderThickness%2A> özelliği bir <xref:System.Windows.Controls.Border>. Bu animasyon üç ana kare aşağıdaki şekilde kullanır:  
  
1.  Birinci yarım saniye boyunca bir örneğini kullanan <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> kenarlığın kalınlığı aşamalı olarak artırmak için sınıf. Örnek kullanır <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> değerler arasında yumuşak doğrusal bir artış oluşturmak için.  
  
2.  Sonraki sonunda yarım ikinci bir örneğini kullanır <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> aniden kenarlığın kalınlığı artırmak için sınıf. Bu gibi ayrık anahtar çerçeveler türetilen <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> değerler arasında ani atlar oluşturur, animasyonun hareketi düzensiz olur.  
  
3.  Son iki saniye boyunca bir örneğini kullanan <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> kenarlığın kalınlığı azaltmak için sınıf. Eğri anahtar çerçeveler olanlar gibi türetilen <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> değerlerine göre değerler arasında değişken geçiş oluşturmak <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> özelliği. Bu anahtar çerçeve animasyon yavaş başlar ve zaman diliminin sonuna doğru katlanarak hızlanır.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Tam bir örnek için bkz: [ana kare animasyon örneği](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>  
 [Anahtar-Çerçeve Animasyonlara Genel Bakış](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Anahtar Çerçeve ile İlgili Nasıl Yapılır Konuları](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [BorderThickness Değerine Animasyon Ekleme](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)
