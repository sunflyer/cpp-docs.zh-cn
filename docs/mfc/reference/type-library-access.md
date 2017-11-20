---
title: "类型库访问 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 8f05738c02fd70fde5fc2d92c5ee1e823747797c
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="type-library-access"></a>类型库访问
类型库向其他 OLE 感知的应用程序公开 OLE 控件的接口。 如果将公开一个或多个接口，则每个 OLE 控件都必须具有类型库。  
  
 下列宏允许 OLE 控件提供对其自己的类型库的访问：  
  
### <a name="type-library-access"></a>类型库访问  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|声明 OLE 控件（必须用于类声明中）的 `GetTypeLib` 成员函数。|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|实现 OLE 控件（必须用于类实现中）的 `GetTypeLib` 成员函数。|  
  
##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
 声明`GetTypeLib`控件类的成员函数。  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>参数  
 *class_name*  
 与类型库相关的控件类名称。  
  
### <a name="remarks"></a>备注  
 在控件类标头文件中使用此宏。  

### <a name="requirements"></a>要求  
 **标头：** afxdisp.h  

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
 实现控件的`GetTypeLib`成员函数。  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>参数  
 *class_name*  
 与类型库相关的控件类名称。  
  
 *tlid*  
 类型库 ID 号。  
  
 `wVerMajor`  
 类型库主版本号。  
  
 `wVerMinor`  
 类型库次版本号。  
  
### <a name="remarks"></a>备注  
 此宏必须出现在任何使用的控件类的实现文件`DECLARE_OLETYPELIB`宏。  

### <a name="requirements"></a>要求  
 **标头：** afxdisp.h  
   
## <a name="see-also"></a>另请参阅  
 [宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)
