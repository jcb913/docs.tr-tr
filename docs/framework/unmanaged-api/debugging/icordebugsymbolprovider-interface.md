---
title: ICorDebugSymbolProvider arabirimi
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e9f475ee3c46b8abb94ce7f804cc8b4a8054ec2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423214"
---
# <a name="icordebugsymbolprovider-interface"></a>ICorDebugSymbolProvider arabirimi
Hata ayıklama sembol bilgilerini almak için kullanılan yöntemleri sağlar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetAssemblyImageBytes Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|Birleştirilmiş derlemede göreli sanal adres (RVA) verilen birleştirilmiş bir bütünleştirilmiş koddan verileri okur.|  
|[GetAssemblyImageMetadata Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|Birleştirilmiş bir derlemeye ait meta verileri döndürür.|  
|[GetCodeRange Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|Yöntemi başlangıç adresi ve bir yöntem göreli sanal adres (RVA) verilen boyutunu alır.|  
|[GetInstanceFieldSymbols Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|Örnek TypeSpec'te imza karşılık gelen alan simgelerini alır.|  
|[GetMergedAssemblyRecords Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|Sembol kayıtları için tüm birleştirilmiş derlemeleri alır.|  
|[GetMethodLocalSymbols Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|Bu yöntemin göreli sanal adres (RVA) verilen bir yöntemin yerel simgelerini alır.|  
|[GetMethodParameterSymbols Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|Bu yöntemin göreli sanal adres (RVA) verilen bir yöntemin parametre simgelerini alır.|  
|[GetMethodProps Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|Bu yönteme göreli sanal adres (RVA) verilen yöntemin meta veri simgesi ve kendi genel parametreleri hakkında bilgi gibi yöntemi özellikleri hakkında bilgi döndürür.|  
|[GetObjectSize Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|TypeSpec'te imzası dayalı bir nesne için nesne boyutu döndürür.|  
|[GetStaticFieldSymbols Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|TypeSpec'te imza karşılık gelen statik alan simgelerini alır.|  
|[GetTypeProps Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|Göreli sanal adres (RAV) bir vtable verilen imza genel parametrelerinin sayısı gibi bir tür özellikleri hakkında bilgi döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu arabirim yalnızca .NET yerel ile kullanılabilir. Bu arabirim .NET yerel dışında Icordebug senaryoları için uygularsanız, ortak dil çalışma zamanı bu arabirim göz ardı eder.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Hata Ayıklama](../../../../docs/framework/unmanaged-api/debugging/index.md)
