---
title: nameof (C# Başvurusu)
ms.date: 06/16/2017
f1_keywords:
- nameof_CSharpKeyword
- nameof
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 2695095aa4bf2035d8766f3cbcb82f4fbb290e22
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208409"
---
# <a name="nameof-c-reference"></a>nameof (C# Başvurusu)

Değişken, tür veya üye basit (nitelenmemiş) dize adını almak için kullanılır.  

Model-view-controller (MVC) bağlantıları, takma kodundaki bildirilirken tetikleme özellik değişti olayları, vb., genellikle bir yöntem dize adını yakalamak istediğiniz.  Kullanarak `nameof` tutan kodunuzu geçerli tanımları adlandırırken.  Önce dize değişmez değerleri tanımları için başvurmak için kullanmanız Bu dize değişmez değerleri denetlemek için Araçlar bilmiyorsanız çünkü kod öğeleri adlandırırken kırılır gerekiyordu.  
  
 A `nameof` ifadesi bu formu vardır:  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a>Anahtar kullanım örnekleri  
 Anahtar kullanım durumları için bu örnekler `nameof`.  
  
 Parametreleri doğrulayın:  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 MVC eylemi bağlantıları:  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 INotifyPropertyChanged:  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 XAML bağımlılık özelliği:  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 Günlüğe kaydetme:  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 Öznitelikleri:  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a>Örnekler  
 Bazı C# örnekleri:  
  
```csharp  
using Stuff = Some.Cool.Functionality  
class C {  
    static int Method1 (string x, int y) {}  
    static int Method1 (string x, string y) {}  
    int Method2 (int z) {}  
    string f<T>() => nameof(T);  
}  
  
var c = new C()  
  
class Test {  
    static void Main (string[] args) {  
        Console.WriteLine(nameof(C)); // -> "C"  
        Console.WriteLine(nameof(C.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(C.Method2)); // -> "Method2"  
        Console.WriteLine(nameof(c.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(c.Method2)); // -> "Method2"  
        // Console.WriteLine(nameof(z)); -> "z" [inside of Method2 ok, inside Method1 is a compiler error]  
        Console.WriteLine(nameof(Stuff)); // -> "Stuff"  
        // Console.WriteLine(nameof(T)); -> "T" [works inside of method but not in attributes on the method]  
        Console.WriteLine(nameof(f)); // -> "f"  
        // Console.WriteLine(nameof(f<T>)); -> [syntax error]  
        // Console.WriteLine(nameof(f<>)); -> [syntax error]  
        // Console.WriteLine(nameof(Method2())); -> [error "This expression does not have a name"]  
    }
}
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişkeni `nameof` basit bir ad, tam adı, üye erişimi, belirtilen üyenin temel erişimle veya belirtilen üyeyle bu erişimi olması gerekir.  Kod tanımı bağımsız değişken ifadesi tanımlar, ancak hiçbir zaman değerlendirilir.  
  
 Bağımsız değişkeni bir ifade sözdizimsel olarak olması gerektiğinden vardır listelemek yararlı değildir pek çok şeyi izin verilmiyor.  Hataları üretmek tümleştirilmediği şunlardır: türleri önceden tanımlanmış (örneğin, `int` veya `void`), boş değer atanabilir türler (`Point?`), dizi türleri (`Customer[,]`), işaretçi türleri (`Buffer*`), diğer ad tam (`A::B` ) ve genel türler ilişkisiz (`Dictionary<,>`), simgeler ön işleme (`DEBUG`) ve etiketler (`loop:`).  
  
 Tam adını almak gerekiyorsa, kullanabileceğiniz `typeof` ifade ile birlikte `nameof`.  Örneğin:
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 Ne yazık ki `typeof` gibi sabit bir ifade değil `nameof`, bu nedenle `typeof` ile birlikte kullanılamaz `nameof` hepsi aynı olarak yerleştirir `nameof`.  Örneğin, aşağıdaki CS0182 derleme hatasına neden olur:
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 Örneklerde, bir tür adı kullanın ve bir örnek yöntemi adı erişim görürsünüz.  Türünün bir örneği için gereken değerlendirilen ifadeleri olarak olması gerekmez.  Tür adı kullanarak, yalnızca adına başvuran ve örnek verileri kullanarak değil, bir örnek değişkeni ya da ifade contrive gerekmez bazı durumlarda ve çok kullanışlı olabilir.  
  
 Bir sınıf özniteliği ifadelerde sınıfı üyeleri başvuruda bulunabilir.  
  
 Gibi bir imza bilgileri almak için bir yolu yoktur "`Method1 (str, str)`".  Bunu yapmanın bir yolu, bir ifade kullanmaktır `Expression e = () => A.B.Method1("s1", "s2")`ve sonuçta elde edilen ifadesi ağacından MemberInfo çeker.  
  
## <a name="language-specifications"></a>Dil belirtimleri  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# başvurusu](../../../csharp/language-reference/index.md)  
 [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
 [typeof](../../../csharp/language-reference/keywords/typeof.md)  
 
