---
title: "Ortak kapsayıcı tasarım ilkeleri"
description: "Microsoft Platformu ve araçları ile kapsayıcılı Docker uygulama yaşam döngüsü"
keywords: "Docker, mikro, ASP.NET, kapsayıcı"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: d7186ae3b768384fe5c6b269578de8db5ef6064c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="common-container-design-principles"></a><span data-ttu-id="f7ef4-104">Ortak kapsayıcı tasarım ilkeleri</span><span class="sxs-lookup"><span data-stu-id="f7ef4-104">Common container design principles</span></span>

<span data-ttu-id="f7ef4-105">Şimdi geliştirme işlemine alma kapsayıcıları kullanma açısından söz değerinde birkaç temel kavram vardır.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-105">Ahead of getting into the development process there are a few basic concepts worth mentioning with regard to how you use containers.</span></span>

## <a name="container-equals-a-process"></a><span data-ttu-id="f7ef4-106">Kapsayıcı bir işlem eşittir</span><span class="sxs-lookup"><span data-stu-id="f7ef4-106">Container equals a process</span></span>

<span data-ttu-id="f7ef4-107">Kapsayıcı modelinde, tek bir işlem bir kapsayıcıyı temsil eder.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-107">In the container model, a container represents a single process.</span></span> <span data-ttu-id="f7ef4-108">İşlem sınır olarak bir kapsayıcı tanımlayarak, Ölçek veya toplu kapalı, işlemleri için kullanılan temelleri oluşturmak başlayın.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-108">By defining a container as a process boundary, you begin to create the primitives used to scale, or batch-off, processes.</span></span> <span data-ttu-id="f7ef4-109">Docker kapsayıcısı çalıştırdığınızda göreceğiniz bir [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) tanımı.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-109">When you run a Docker container, you'll see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definition.</span></span> <span data-ttu-id="f7ef4-110">Bu işlem ve kapsayıcı ömrü tanımlar.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-110">This defines the process and the lifetime of the container.</span></span> <span data-ttu-id="f7ef4-111">İşlem tamamlandığında, kapsayıcı ömrü sona erer.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-111">When the process completes, the container life cycle ends.</span></span> <span data-ttu-id="f7ef4-112">Web sunucuları ve Microsoft Azure uygulanmamış toplu işler gibi kısa süreli bir işlem gibi uzun süre çalışan işlemlerin [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/).</span><span class="sxs-lookup"><span data-stu-id="f7ef4-112">There are long-running processes, such as web servers, and short-lived processes, such as batch jobs, which might have been implemented as Microsoft Azure [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/).</span></span> <span data-ttu-id="f7ef4-113">İşlem başarısız olur, kapsayıcı sona erer ve orchestrator devreye girer durumunda.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-113">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="f7ef4-114">Orchestrator beş örnek çalışıyor tutmak için istendi ve biri başarısız olursa, orchestrator başarısız işlem değiştirmek için başka bir kapsayıcı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-114">If the orchestrator was instructed to keep five instances running and one fails, the orchestrator will create another container to replace the failed process.</span></span> <span data-ttu-id="f7ef4-115">Bir toplu işlemde parametrelerle işlemi başlatıldı.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-115">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="f7ef4-116">İşlem tamamlandığında, iş tamamlanır.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-116">When the process completes, the work is complete.</span></span>

<span data-ttu-id="f7ef4-117">Tek bir kapsayıcıda çalışan birden çok işlemler istediğiniz bir senaryo bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-117">You might find a scenario in which you want multiple processes running in a single container.</span></span> <span data-ttu-id="f7ef4-118">Herhangi bir mimari belgesinde hiçbir zaman bir "hiçbir değildir," ya da her zaman olduğu bir "her zaman."</span><span class="sxs-lookup"><span data-stu-id="f7ef4-118">In any architecture document, there's never a "never," nor is there always an "always."</span></span> <span data-ttu-id="f7ef4-119">Birden çok işlem gerektiren senaryolar için genel bir desen kullanmaktır [Supervisor](http://supervisord.org/).</span><span class="sxs-lookup"><span data-stu-id="f7ef4-119">For scenarios requiring multiple processes, a common pattern is to use [Supervisor](http://supervisord.org/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f7ef4-120">[Önceki] (Tasarım-docker-applications.md) [sonraki] (applications.md tek yapılı)</span><span class="sxs-lookup"><span data-stu-id="f7ef4-120">[Previous] (design-docker-applications.md) [Next] (monolithic-applications.md)</span></span>