---
title: 多内联文件
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: ec531e5716098725782010927201ef57e2a8aa24
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558153"
---
# <a name="multiple-inline-files"></a>多内联文件

命令可以创建多个内联文件。

## <a name="syntax"></a>语法

```
command << <<
inlinetext
<<[KEEP | NOKEEP]
inlinetext
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>备注

对于每个文件，请指定一个或多个行包含分隔符的结束行后跟的内联文本。 开始后的第一个文件的分隔行的行上的第二个文件的文本。

## <a name="see-also"></a>请参阅

[生成文件中的内联文件](../build/inline-files-in-a-makefile.md)