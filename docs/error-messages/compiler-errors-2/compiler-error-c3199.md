---
title: 编译器错误 C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 934e980149ad893e6799b0ab119a148fc5652fdc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578953"
---
# <a name="compiler-error-c3199"></a>编译器错误 C3199

使用浮点 pragma 无效： 在非精确模式下不支持异常

[Float_control](../../preprocessor/float-control.md)杂注用于指定的浮点异常模型下[/fp](../../build/reference/fp-specify-floating-point-behavior.md)而不设置 **/fp： 精确**。

下面的示例生成 C3199:

```
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```