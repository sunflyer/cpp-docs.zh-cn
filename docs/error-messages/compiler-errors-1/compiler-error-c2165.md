---
title: 编译器错误 C2165
ms.date: 11/04/2016
f1_keywords:
- C2165
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
ms.openlocfilehash: 1dadc56dafca056db9b4a14ab39127306b797f8a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570386"
---
# <a name="compiler-error-c2165"></a>编译器错误 C2165

“keyword”: 不能修改指向数据的指针

`__stdcall`、 `__cdecl`或 `__fastcall` 关键字尝试修改指向数据的指针。

以下示例生成 C2165：

```
// C2165.cpp
// compile with: /c
char __cdecl *p;   // C2165
char *p;   // OK
```