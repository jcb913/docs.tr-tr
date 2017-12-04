---
title: "Değişken genel arabirimler oluşturma (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 380af3b29172b1fa13d42d33e574201607cb804b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-variant-generic-interfaces-visual-basic"></a><span data-ttu-id="289a0-102">Değişken genel arabirimler oluşturma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="289a0-102">Creating Variant Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="289a0-103">Genel tür parametreleri eşdeğişken olarak arabirimlerdeki bildirebilir veya karşıtı.</span><span class="sxs-lookup"><span data-stu-id="289a0-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="289a0-104">*Kovaryans* dönüş türleri genel tür parametreleri tarafından tanımlanan daha fazla türetilmiş arabirim yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="289a0-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="289a0-105">*Değişken karşıtı* genel parametreler tarafından belirtilenden daha az türetilmiş bağımsız değişken türleri arabirim yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="289a0-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="289a0-106">Eşdeğişken sahip genel arabirim veya karşıtı genel tür parametreleri çağrılır *değişken*.</span><span class="sxs-lookup"><span data-stu-id="289a0-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="289a0-107">.NET framework 4 birkaç mevcut genel arabirimler sapma desteği sunmuştur.</span><span class="sxs-lookup"><span data-stu-id="289a0-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="289a0-108">.NET Framework'teki değişken arabirimler listesi için bkz: [genel arabirimler (Visual Basic) varyans](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="289a0-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="289a0-109">Bildiren değişken genel arabirimler</span><span class="sxs-lookup"><span data-stu-id="289a0-109">Declaring Variant Generic Interfaces</span></span>  
 <span data-ttu-id="289a0-110">Değişken genel arabirimler kullanarak bildirebilirsiniz `in` ve `out` genel tür parametreleri için anahtar sözcükler.</span><span class="sxs-lookup"><span data-stu-id="289a0-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="289a0-111">`ByRef`Visual Basic'de değişken olamaz.</span><span class="sxs-lookup"><span data-stu-id="289a0-111">`ByRef` parameters in Visual Basic cannot be variant.</span></span> <span data-ttu-id="289a0-112">Türlerin varyans da desteklemez.</span><span class="sxs-lookup"><span data-stu-id="289a0-112">Value types also do not support variance.</span></span>  
  
 <span data-ttu-id="289a0-113">Genel tür parametresi eşdeğişken kullanarak bildirebilirsiniz `out` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="289a0-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="289a0-114">Eşdeğişken türü aşağıdaki koşulları karşılaması gerekir:</span><span class="sxs-lookup"><span data-stu-id="289a0-114">The covariant type must satisfy the following conditions:</span></span>  
  
-   <span data-ttu-id="289a0-115">Türü yalnızca bir dönüş türü arabirim yöntemleri olarak kullanılan ve yöntem bağımsız değişkenleri bir tür olarak kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="289a0-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="289a0-116">Bu, aşağıdaki örnekte gösterilmiştir türü `R` eşdeğişken bildirilir.</span><span class="sxs-lookup"><span data-stu-id="289a0-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     <span data-ttu-id="289a0-117">Bu kural için bir istisna vardır.</span><span class="sxs-lookup"><span data-stu-id="289a0-117">There is one exception to this rule.</span></span> <span data-ttu-id="289a0-118">Karşıtı Genel temsilci bir yöntem parametresi olarak varsa, türü için temsilci genel tür parametresi olarak kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="289a0-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="289a0-119">Bu türü tarafından gösterilen `R` aşağıdaki örnekte.</span><span class="sxs-lookup"><span data-stu-id="289a0-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="289a0-120">Daha fazla bilgi için bkz: [Temsilcilerde varyans (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) ve [işlev ve eylem genel temsilciler (Visual Basic) kullanarak varyansını](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="289a0-120">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   <span data-ttu-id="289a0-121">Türü, arabirim yöntemleri için genel bir kısıtlama olarak kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="289a0-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="289a0-122">Bu aşağıdaki kodda gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="289a0-122">This is illustrated in the following code.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 <span data-ttu-id="289a0-123">Genel tür parametresi karşıtı kullanarak bildirebilirsiniz `in` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="289a0-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="289a0-124">Karşıtı türü arabirim yöntemleri dönüş türü olarak değil de yalnızca yöntem bağımsız değişkenleri bir tür olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="289a0-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="289a0-125">Karşıtı türü, genel kısıtlamalar için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="289a0-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="289a0-126">Aşağıdaki kod karşıtı arabirimi bildirin ve genel bir kısıtlama yöntemlerinden biri için nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="289a0-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 <span data-ttu-id="289a0-127">Ayrıca aşağıdaki kod örneğinde gösterildiği gibi farklı tür parametreleri yanı sıra, aynı arabiriminde Kovaryans ve kontravaryans desteklemek mümkündür.</span><span class="sxs-lookup"><span data-stu-id="289a0-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 <span data-ttu-id="289a0-128">Visual Basic'te temsilci türü belirtmeden değişken arabirimler olayları bildiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="289a0-128">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="289a0-129">Ayrıca, bir değişken arabirimi sınıfları, numaralandırmaları ve yapıları iç içe geçmiş olamaz, ancak arabirimleri içe.</span><span class="sxs-lookup"><span data-stu-id="289a0-129">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span></span> <span data-ttu-id="289a0-130">Bu aşağıdaki kodda gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="289a0-130">This is illustrated in the following code.</span></span>  
  
```vb  
Interface ICovariant(Of Out R)  
    ' The following statement generates a compiler error.  
    ' Event SampleEvent()  
    ' The following statement specifies the delegate type and   
    ' does not generate an error.  
    Event AnotherEvent As EventHandler  
  
    ' The following statements generate compiler errors,  
    ' because a variant interface cannot have  
    ' nested enums, classes, or structures.  
  
    'Enum SampleEnum : test : End Enum  
    'Class SampleClass : End Class  
    'Structure SampleStructure : Dim value As Integer : End Structure  
  
    ' Variant interfaces can have nested interfaces.  
    Interface INested : End Interface  
End Interface  
```  
  
## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="289a0-131">Uygulama değişken genel arabirimler</span><span class="sxs-lookup"><span data-stu-id="289a0-131">Implementing Variant Generic Interfaces</span></span>  
 <span data-ttu-id="289a0-132">Değişken genel arabirimler değişmez arabirimleri için kullanılan aynı sözdizimini kullanarak sınıflarda uygulayın.</span><span class="sxs-lookup"><span data-stu-id="289a0-132">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="289a0-133">Aşağıdaki kod örneğinde, genel bir sınıf bir eşdeğişken arabirimini uygulayan gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="289a0-133">The following code example shows how to implement a covariant interface in a generic class.</span></span>  
  
```vb  
Interface ICovariant(Of Out R)  
    Function GetSomething() As R  
End Interface  
  
Class SampleImplementation(Of R)  
    Implements ICovariant(Of R)  
    Public Function GetSomething() As R _  
    Implements ICovariant(Of R).GetSomething  
        ' Some code.  
    End Function  
End Class  
```  
  
 <span data-ttu-id="289a0-134">Değişken arabirimler uygulayan sınıflar değişmez.</span><span class="sxs-lookup"><span data-stu-id="289a0-134">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="289a0-135">Örneğin, aşağıdaki kodu göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="289a0-135">For example, consider the following code.</span></span>  
  
```vb  
 The interface is covariant.  
Dim ibutton As ICovariant(Of Button) =  
    New SampleImplementation(Of Button)  
Dim iobj As ICovariant(Of Object) = ibutton  
  
' The class is invariant.  
Dim button As SampleImplementation(Of Button) =  
    New SampleImplementation(Of Button)  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim obj As SampleImplementation(Of Object) = button  
```  
  
## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="289a0-136">Genişletme değişken genel arabirimler</span><span class="sxs-lookup"><span data-stu-id="289a0-136">Extending Variant Generic Interfaces</span></span>  
 <span data-ttu-id="289a0-137">Değişken genel bir arabirim genişlettiğinizde kullanmak zorunda `in` ve `out` açıkça türetilmiş bir arabirim farkı destekleyip desteklemediğini belirlemek için anahtar sözcükler.</span><span class="sxs-lookup"><span data-stu-id="289a0-137">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="289a0-138">Derleyici genişletilen arabiriminden varyansı Infer değil.</span><span class="sxs-lookup"><span data-stu-id="289a0-138">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="289a0-139">Örneğin, aşağıdaki arabirimleri göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="289a0-139">For example, consider the following interfaces.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T)  
End Interface  
  
Interface IExtCovariant(Of Out T)  
    Inherits ICovariant(Of T)  
End Interface  
```  
  
 <span data-ttu-id="289a0-140">İçinde `Invariant(Of T)` arabirim, genel tür parametresi `T` değişmez, olan ancak içinde `IExtCovariant (Of Out T)`aynı arabirimi her iki arabirimde genişletmek rağmen tür parametresi değişkendir.</span><span class="sxs-lookup"><span data-stu-id="289a0-140">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="289a0-141">Aynı kural karşıtı genel tür parametreleri için uygulanır.</span><span class="sxs-lookup"><span data-stu-id="289a0-141">The same rule is applied to contravariant generic type parameters.</span></span>  
  
 <span data-ttu-id="289a0-142">Genel parametre girildiği iki arabirim genişleten bir arabirim oluşturabilirsiniz `T` değişkendir ve varsa genişletme içinde karşıtı olduğu arabirimi arabirim genel tür parametresi `T` sabit değil.</span><span class="sxs-lookup"><span data-stu-id="289a0-142">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="289a0-143">Bu aşağıdaki kod örneğinde gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="289a0-143">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 <span data-ttu-id="289a0-144">Ancak, genel türde bir parametre değilse `T` olan bir arabiriminde eşdeğişken bildirilen, siz onu karşıtı bildiremezsiniz genişletme arabiriminde veya tersi.</span><span class="sxs-lookup"><span data-stu-id="289a0-144">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="289a0-145">Bu aşağıdaki kod örneğinde gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="289a0-145">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a><span data-ttu-id="289a0-146">Belirsizliği önleme</span><span class="sxs-lookup"><span data-stu-id="289a0-146">Avoiding Ambiguity</span></span>  
 <span data-ttu-id="289a0-147">Değişken genel arabirimler uyguladığınızda farkı bazen belirsizlik için yol açabilir.</span><span class="sxs-lookup"><span data-stu-id="289a0-147">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="289a0-148">Bu kaçınılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="289a0-148">This should be avoided.</span></span>  
  
 <span data-ttu-id="289a0-149">Örneğin, bir sınıf tarafından açıkça farklı genel tür parametreleri ile aynı değişken genel arabirim uygularsanız, belirsizlik oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="289a0-149">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="289a0-150">Derleyici bir hata bu durumda üretmez, ancak çalışma zamanında hangi arabirim uygulamasına seçilir belirtilmedi.</span><span class="sxs-lookup"><span data-stu-id="289a0-150">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="289a0-151">Bu, kodunuzda Zarif hataları neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="289a0-151">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="289a0-152">Aşağıdaki kod örneği göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="289a0-152">Consider the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="289a0-153">İle `Option Strict Off`, Visual Basic belirsiz arabirim uygulamasına olduğunda bir derleyici uyarı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="289a0-153">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span></span> <span data-ttu-id="289a0-154">İle `Option Strict On`, Visual Basic derleyici hatası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="289a0-154">With `Option Strict On`, Visual Basic generates a compiler error.</span></span>  
  
```vb  
' Simple class hierarchy.  
Class Animal  
End Class  
  
Class Cat  
    Inherits Animal  
End Class  
  
Class Dog  
    Inherits Animal  
End Class  
  
' This class introduces ambiguity  
' because IEnumerable(Of Out T) is covariant.  
Class Pets  
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)  
  
    Public Function GetEnumerator() As IEnumerator(Of Cat) _  
        Implements IEnumerable(Of Cat).GetEnumerator  
        Console.WriteLine("Cat")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator(Of Dog) _  
        Implements IEnumerable(Of Dog).GetEnumerator  
        Console.WriteLine("Dog")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator2() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
        ' Some code.  
    End Function  
End Class  
  
Sub Main()  
    Dim pets As IEnumerable(Of Animal) = New Pets()  
    pets.GetEnumerator()  
End Sub  
```  
  
 <span data-ttu-id="289a0-155">Bu örnekte, belirtilmeyen nasıl `pets.GetEnumerator` ücretlerinin arasında `Cat` ve `Dog`.</span><span class="sxs-lookup"><span data-stu-id="289a0-155">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="289a0-156">Bu, kodunuzda sorunlara neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="289a0-156">This could cause problems in your code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="289a0-157">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="289a0-157">See Also</span></span>  
 [<span data-ttu-id="289a0-158">Genel arabirimler (Visual Basic) varyans</span><span class="sxs-lookup"><span data-stu-id="289a0-158">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [<span data-ttu-id="289a0-159">İşlev ve eylem genel temsilciler (Visual Basic) için varyans kullanma</span><span class="sxs-lookup"><span data-stu-id="289a0-159">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)