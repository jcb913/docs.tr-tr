---
title: -pathmap (C# Derleyici Seçenekleri)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 36196ffea19cfde7ff5f830ea358d2bd83edf419
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
# <a name="-pathmap-c-compiler-options"></a><span data-ttu-id="a1bfd-102">-pathmap (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="a1bfd-102">-pathmap (C# Compiler Options)</span></span>

<span data-ttu-id="a1bfd-103">**- Pathmap** derleyici seçeneği nasıl derleyici tarafından kaynak yolu adları çıktısına fiziksel yollar eşleneceğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="a1bfd-103">The **-pathmap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1bfd-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a1bfd-104">Syntax</span></span>

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a><span data-ttu-id="a1bfd-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="a1bfd-105">Arguments</span></span>

 <span data-ttu-id="a1bfd-106">`path1` Geçerli ortamda kaynak dosyalarının tam yolu</span><span class="sxs-lookup"><span data-stu-id="a1bfd-106">`path1` The full path to the source files in the current environment</span></span>

 <span data-ttu-id="a1bfd-107">`sourcePath1` Kaynak yolu için yerine `path1` hiçbir çıktı dosyalarında.</span><span class="sxs-lookup"><span data-stu-id="a1bfd-107">`sourcePath1` The source path substituted for `path1` in any output files.</span></span>

<span data-ttu-id="a1bfd-108">Birden çok eşleşen kaynak yolları belirlemek için her bir virgül ile ayırın.</span><span class="sxs-lookup"><span data-stu-id="a1bfd-108">To specify multiple mapped source paths, separate each with a comma.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1bfd-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a1bfd-109">Remarks</span></span>

<span data-ttu-id="a1bfd-110">Derleyici kaynak yolu yolu aşağıdaki nedenlerle çıktısını Yazar:</span><span class="sxs-lookup"><span data-stu-id="a1bfd-110">The compiler writes the source path path into its output for the following reasons:</span></span>

1. <span data-ttu-id="a1bfd-111">Kaynak yolu için bağımsız değişken yerine zaman <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> isteğe bağlı bir parametre uygulanır.</span><span class="sxs-lookup"><span data-stu-id="a1bfd-111">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="a1bfd-112">Kaynak yolu PDB dosyasında katıştırılır.</span><span class="sxs-lookup"><span data-stu-id="a1bfd-112">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="a1bfd-113">PDB dosyasının yolunu PE (taşınabilir yürütülebilir) dosyasına katıştırılır.</span><span class="sxs-lookup"><span data-stu-id="a1bfd-113">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

<span data-ttu-id="a1bfd-114">Bu seçenek her fiziksel yolu derleyici çıktı dosyaları yazılması gereken karşılık gelen bir yola çalıştığı makinede eşler.</span><span class="sxs-lookup"><span data-stu-id="a1bfd-114">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span>

## <a name="example"></a><span data-ttu-id="a1bfd-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="a1bfd-115">Example</span></span>

<span data-ttu-id="a1bfd-116">Derleme `t.cs` dizininde **C:\\iş\\testleri** ve bu dizine eşleme **\publish** çıkışı:</span><span class="sxs-lookup"><span data-stu-id="a1bfd-116">Compile `t.cs` in the directory **C:\\work\\tests** and map that directory to **\publish** in the output:</span></span>

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a><span data-ttu-id="a1bfd-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a1bfd-117">See also</span></span>

 [<span data-ttu-id="a1bfd-118">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="a1bfd-118">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="a1bfd-119">Proje ve Çözüm Özelliklerini Yönetme</span><span class="sxs-lookup"><span data-stu-id="a1bfd-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)