---
title: Özel türler anahtar etkinlikle kullanımı
ms.date: 03/30/2017
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
ms.openlocfilehash: 2b6f3109324064cb5e746de9c61e5a70c4c4d60b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517887"
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a>Özel türler anahtar etkinlikle kullanımı
Bu örnek nasıl etkinleştirileceğini açıklar bir <xref:System.Activities.Statements.Switch%601> çalışma zamanında kullanıcı tarafından tanımlanan karmaşık tür değerlendirmek için etkinlik. Çoğu geleneksel yordam programlama dillerinde, bir [geçiş](http://go.microsoft.com/fwlink/?LinkId=180521) deyimi bir değişkene koşullu değerlendirmeye dayanarak bir yürütme mantığını seçer. Geleneksel olarak, bir `switch` deyimi statik olarak değerlendirilen bir ifade üzerinde çalışır. Örneğin, C# gibi yalnızca basit türler yani <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, ve Numaralandırma türleri desteklenir.  
  
 Özel bir sınıf değiştirmeyi etkinleştirmek için mantığı çalışma zamanında özel karmaşık türün değerlerini değerlendirmek için uygulanmalıdır. Bu örnek adlı bir özel karmaşık tür üzerinde değiştirmeyi etkinleştirmek gösterilmiştir `Person`.  
  
-   Özel bir sınıf içinde `Person`, <xref:System.ComponentModel.TypeConverter> özniteliği özel adıyla bildirilen <xref:System.ComponentModel.TypeConverter>.  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   Özel bir sınıf içinde `Person`, <xref:System.Object.Equals%2A> ve <xref:System.Object.GetHashCode%2A> sınıfları geçersiz kılınır.  
  
    ```  
    public override bool Equals(object obj)  
    {  
        Person person = obj as Person;  
  
        if (person != null)  
        {  
            return string.Equals(this.Name, person.Name);  
        }  
  
        return false;  
    }  
  
    public override int GetHashCode()  
    {  
        if (this.Name != null)  
        {  
            return this.Name.GetHashCode();  
        }  
  
        return 0;  
    }  
    ```  
  
-   Özel bir <xref:System.ComponentModel.TypeConverter> sınıfı bir dize ve özel bir sınıf örneği dizeye özel sınıfının bir örneği dönüştürülmesi gerçekleştiren uygulanır.  
  
    ```  
    public class PersonConverter : TypeConverter  
    {  
        public override bool CanConvertFrom(ITypeDescriptorContext context,  
           Type sourceType)  
        {  
            return (sourceType is string);  
        }  
  
        // Overrides the ConvertFrom method of TypeConverter.  
        public override object ConvertFrom(ITypeDescriptorContext context,  
           CultureInfo culture, object value)  
        {  
            if (value == null)  
            {  
                return null;  
            }  
  
            if (value is string)  
            {  
                return new Person  
                {  
                    Name = (string)value  
                };  
            }  
  
            return base.ConvertFrom(context, culture, value);  
        }  
  
        // Overrides the ConvertTo method of TypeConverter.  
        public override object ConvertTo(ITypeDescriptorContext context,  
           CultureInfo culture, object value, Type destinationType)  
        {  
            if (destinationType == typeof(string))  
            {  
                if (value != null)  
                {  
                    return ((Person) value).Name;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
  
            return base.ConvertTo(context, culture, value, destinationType);  
        }  
    }  
    ```  
  
 Bu örnekte aşağıdaki dosyaları bulunmaktadır:  
  
-   **Person.cs**: tanımlar `Person` sınıfı.  
  
-   **PersonConverter.cs**: için tür dönüştürücüsünü `Person` sınıfı.  
  
-   **Sequence.XAML**: geçer üzerinden bir iş akışı `Person` türü.  
  
-   **Program.cs**: iş akışı çalıştıran ana işlevi.  
  
#### <a name="to-use-this-sample"></a>Bu örneği kullanmak için  
  
1.  İçinde Switch.sln yük [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.  
  
3.  Örneği çalıştırmak için CTRL + F5 tuşuna basın.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerleşik Etkinlik Kitaplığı](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
