---
title: 使用 abort
ms.date: 11/04/2016
f1_keywords:
- Abort
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
ms.openlocfilehash: 0961f6f88f5de4d435fa65e50b9dbdbc478e7608
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591823"
---
# <a name="using-abort"></a>使用 abort

调用[中止](../c-runtime-library/reference/abort.md)函数会导致立即中止。 它绕过初始化的全局静态对象的一般析构过程。 它还绕过使用 `atexit` 函数指定的任何特殊处理。

## <a name="see-also"></a>请参阅

[附加终止注意事项](../cpp/additional-termination-considerations.md)