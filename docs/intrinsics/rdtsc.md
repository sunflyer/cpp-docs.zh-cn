---
title: __rdtsc
ms.date: 11/04/2016
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 5f058eaf6587b74f5a75044416d23ac6b64fb415
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582060"
---
# <a name="rdtsc"></a>__rdtsc

**Microsoft 专用**

生成`rdtsc`指令，返回的处理器时间戳。 处理器时间戳记录上次重置后的时钟周期数。

## <a name="syntax"></a>语法

```
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>返回值

表示的计时周期计数的 64 位无符号的整数。

## <a name="requirements"></a>要求

|内部函数|体系结构|
|---------------|------------------|
|`__rdtsc`|x86、x64|

**标头文件** \<intrin.h >

## <a name="remarks"></a>备注

此例程只能用作内部函数。

在这一代硬件 TSC 值的解释不同于在早期版本的 x64。 请参阅硬件手册，以获得详细信息。

## <a name="example"></a>示例

```
// rdtsc.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__rdtsc)

int main()
{
    unsigned __int64 i;
    i = __rdtsc();
    printf_s("%I64d ticks\n", i);
}
```

```Output
3363423610155519 ticks
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)