---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Metodu
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 343cedcf26112f0f2bcc7943ea5ee9f302329a15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457483"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Metodu
Alır `FunctionID` sınıfı içeren belirtilen meta veri simgesi kullanarak bir işlevin ve `ClassID` değerleri herhangi tür bağımsız değişkenleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `moduleID`  
 [in] İşlev bulunduğu modül kimliği.  
  
 `funcDef`  
 [in] Bir `mdMethodDef` işlevi başvuran meta veri simgesi.  
  
 `classId`  
 [in] İşlevin içeren sınıf kimliği.  
  
 `cTypeArgs`  
 [in] Belirtilen işlev için tür parametreleri sayısı. Bu değer, genel olmayan işlevler için sıfır olmalıdır.  
  
 `typeArgs`  
 [in] Bir dizi `ClassID` her biri olduğunda işlevi bağımsız değişkeninin değerleri. Değeri `typeArgs` NULL olabilir `cTypeArgs` sıfır olarak ayarlanır.  
  
 `pFunctionID`  
 [out] Bir işaretçi `FunctionID` belirtilen işlev.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağırma `GetFunctionFromTokenAndTypeArgs` yöntemi ile bir `mdMethodRef` meta verileri yerine bir `mdMethodDef` meta veri simgesi öngörülemeyen sonuçlara sahip olabilir. Arayanlar çözümlemelidir `mdMethodRef` için bir `mdMethodDef` onu geçirilirken.  
  
 İşlevi zaten yüklü değilse, çağırma `GetFunctionFromTokenAndTypeArgs` birçok bağlamlarında tehlikeli olabilecek bir işlemi gerçekleşmesi, yükleme neden olur. Örneğin, çalışma zamanı döngüsel şeyler yükleme girişiminde modülleri veya türlerini yüklemesi sırasında bu yöntemi çağırmadan sonsuz bir döngüye neden olabilir.  
  
 Genel olarak, kullanımı `GetFunctionFromTokenAndTypeArgs` önerilmez. Profil oluşturucular belirli bir işlev için olaylarda ilgileniyorsanız depolamanız gerekir `ModuleID` ve `mdMethodDef` ve bu işlevi kullanın [Icorprofilerınfo2::getfunctionınfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) denetlemek için olup olmadığını bir verilen `FunctionID` değil İstenen işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICorProfilerInfo Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
