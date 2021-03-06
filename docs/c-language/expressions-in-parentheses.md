---
title: 括号中的表达式
ms.date: 11/04/2016
helpviewer_keywords:
- parentheses
- expression evaluation, evaluation order
- expressions [C++], evaluating
- parentheses, expressions
ms.assetid: b8636147-6982-408c-9e64-29e40678ee43
ms.openlocfilehash: 0b58ed2483b404df957b8e9e95e41442403036c9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505542"
---
# <a name="expressions-in-parentheses"></a>括号中的表达式

可以在不更改封闭表达式的类型或值的情况下，将任何操作数包含在括号中。 例如，在下面的表达式中：

```
( 10 + 5 ) / 5
```

`10 + 5` 两边的括号表示先计算 `10 + 5` 的值，然后它会成为除法 (/) 运算符的左操作数。 `( 10 + 5 ) / 5` 的结果为 3。 如果没有括号，则 `10 + 5 / 5` 的计算结果为 11。

尽管括号会影响操作数在表达式中的分组方式，但它们不能在所有情况下确保按照某个特定顺序进行计算。 例如，下列表达式的括号和从左至右的分组不能确保 `i` 的值将位于下列任一子表达式中：

```
( i++ +1 ) * ( 2 + i )
```

编译器可以按任意顺序随意计算乘法的两边内容。 如果 `i` 的初始值为零，则整个表达式可能会计算为两个语句之一：

```
( 0 + 1 + 1 ) * ( 2 + 1 )
( 0 + 1 + 1 ) * ( 2 + 0 )
```

因副作用产生的异常将在[副作用](../c-language/side-effects.md)中进行讨论。

## <a name="see-also"></a>请参阅

[C 主要表达式](../c-language/c-primary-expressions.md)