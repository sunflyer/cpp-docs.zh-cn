---
title: 编译器错误 C2645
ms.date: 11/04/2016
f1_keywords:
- C2645
helpviewer_keywords:
- C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
ms.openlocfilehash: 9df9f41da3d4cbef97511b979845c5a6b404614b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511158"
---
# <a name="compiler-error-c2645"></a>编译器错误 C2645

指向成员的指针没有限定的名 (找到:: *)

指向成员的指针的声明未指定一个类。

下面的示例生成 C2645:

```
// C2645.cpp
class A {};
int main() {
   int B::* bp;   // C2645 B not defined
   int A::* ap;   // OK
}
```