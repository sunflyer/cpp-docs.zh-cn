---
title: C++ 位域
ms.date: 11/19/2018
helpviewer_keywords:
- bitfields [C++]
- fields [C++], bit
- bit fields
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
ms.openlocfilehash: 747920378472cc091928a080e303a0543e287aaa
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175088"
---
# <a name="c-bit-fields"></a>C++ 位域

类和结构可包含比整型类型占用更少存储空间的成员。 这些成员被指定为位域。 位域的语法*成员声明符*规范如下所示：

## <a name="syntax"></a>语法

*声明符* **:** *常量表达式*

## <a name="remarks"></a>备注

（可选）*声明符*是在程序中访问该成员的名称。 它必须是整型类型（包括枚举类型）。 *常数表达式*结构中指定的成员所占据的位数。 匿名位域 — 即不带标识符的位域成员，可用于填充。

> [!NOTE]
> 宽度为 0 的未命名的位域强制对齐方式的下一个位域到下一步**类型**边界，其中**类型**是成员的类型。

下面的示例声明包含位域的结构：

```cpp
// bit_fields1.cpp
// compile with: /LD
struct Date {
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)
   unsigned short nMonth    : 5;    // 0..12  (5 bits)
   unsigned short nYear     : 8;    // 0..100 (8 bits)
};
```

`Date` 类型的对象的概念上的内存布局如下图所示。

![Date 对象的内存布局](../cpp/media/vc38uq1.png "date 对象的内存布局") <br/>
数据对象的内容布局

请注意，`nYear`长度为 8 位，并且会溢出声明类型的字边界**无符号****短**。 因此，开始一个新的开头**无符号****短**。 并不必使所有位域均适合基础类型的对象；根据声明中请求的位数来分配新的存储单元。

**Microsoft 专用**

声明为位域的数据从低位到高位进行排序，如上图所示。

**结束 Microsoft 专用**

如果结构的声明包含长度为 0 的未命名字段（如以下示例所示），

```cpp
// bit_fields2.cpp
// compile with: /LD
struct Date {
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)
   unsigned nMonthDay : 6;    // 0..31  (6 bits)
   unsigned           : 0;    // Force alignment to next boundary.
   unsigned nMonth    : 5;    // 0..12  (5 bits)
   unsigned nYear     : 8;    // 0..100 (8 bits)
};
```

则内存布局将如下图中所示：

![带零日期对象的布局&#45;长度位域](../cpp/media/vc38uq2.png "带零日期布局对象&#45;长度位域") <br/>
带有零长度位域的数据对象的布局

位域的基础类型必须是一种整型类型，如中所述[基本类型](../cpp/fundamental-types-cpp.md)。

如果类型的引用的初始值设定项`const T&`是左值引用类型的位域`T`，引用未绑定到位域直接。 相反，该引用绑定到临时初始化为保存位字段的值。

## <a name="restrictions-on-bit-fields"></a>位域的限制

以下列表详述了位域的错误操作：

- 采用位域的地址。

- 初始化非**const**使用位域的引用。

## <a name="see-also"></a>请参阅

[类和结构](../cpp/classes-and-structs-cpp.md)