---
title: _get_output_format
ms.date: 11/04/2016
apiname:
- _get_output_format
apilocation:
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- get_output_format
- _get_output_format
helpviewer_keywords:
- output formatting
- get_output_format function
- _get_output_format function
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
ms.openlocfilehash: a78ffb1c7fd32db3092bcf1d2297a0be6fa9f47b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518789"
---
# <a name="getoutputformat"></a>_get_output_format

获取输出格式标志的当前值。

> [!IMPORTANT]
>  此函数已过时。 从 Visual Studio 2015 开始，CRT 中不再提供此函数。

## <a name="syntax"></a>语法

```
unsigned int _get_output_format();
```

## <a name="return-value"></a>返回值

输出格式标志的当前值。

## <a name="remarks"></a>备注

输出格式标志控制格式化 I/O 的功能。 当前标记有两个可能值：0 和 `_TWO_DIGIT_EXPONENT`。 如果设置了 `_TWO_DIGIT_EXPONENT` ，则输出的浮点数的指数只有两位，除非指数的大小需要第三位数。 如果标志为零，浮点输出将显示指数的三个位，并在必要时使用零将值填充为三个位。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|`_get_output_format`|\<stdio.h>|

有关更多兼容性信息，请参见“简介”中的 [兼容性](../c-runtime-library/compatibility.md) 。

## <a name="see-also"></a>请参阅

[格式规范语法：printf 和 wprintf 函数](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_set_output_format](../c-runtime-library/set-output-format.md)
