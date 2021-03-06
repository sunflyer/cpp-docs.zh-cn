---
title: 编译器警告 C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: 7138f1a3cecaaf75fbab01fd1aee18529b7a3a84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652440"
---
# <a name="compiler-warning-c4485"></a>编译器警告 C4485

override_function： 匹配 ref 基类方法 base_class_function，但不是标记为 new 或 override;假定 new （和 virtual）

取值函数重写，无论`virtual`关键字、 基类访问器函数，但`override`或`new`说明符不是重写的函数签名的一部分。 添加`new`或`override`说明符来解决此警告。

请参阅[重写](../../windows/override-cpp-component-extensions.md)并[新 (新 vtable 中的槽）](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)有关详细信息。

C4485 始终作为错误发出。 使用[警告](../../preprocessor/warning.md)杂注来禁止显示 C4485。

## <a name="example"></a>示例

下面的示例生成 C4485

```
// C4485.cpp
// compile with: /clr
delegate void Del();

ref struct A {
   virtual event Del ^E;
};

ref struct B : A {
   virtual event Del ^E;   // C4485
};

ref struct C : B {
   virtual event Del ^E {
      void raise() override {}
      void add(Del ^) override {}
      void remove(Del^) override {}
   }
};
```