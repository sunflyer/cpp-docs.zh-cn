---
title: 日期和时间：SYSTEMTIME 支持
ms.date: 11/04/2016
f1_keywords:
- SYSTEMTIME
helpviewer_keywords:
- system time
- FILETIME structure, with CTime class
- time [C++], formatting
- SYSTEMTIME structure
- dates [C++], MFC
- formatting [C++], time
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
ms.openlocfilehash: db19d236d0f0d8672f08c808237de471bf5bc64d
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53177728"
---
# <a name="date-and-time-systemtime-support"></a>日期和时间：SYSTEMTIME 支持

[CTime](../atl-mfc-shared/reference/ctime-class.md)类具有构造函数接受来自 Win32 的系统和文件时间。 如果你将 `CTime` 对象用于这些目的，你必须相应地修改它们的初始化，如本文所述。

有关 SYSTEMTIME 结构的信息，请参阅[SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950)。 有关 FILETIME 结构的信息，请参阅[FILETIME](https://msdn.microsoft.com/library/windows/desktop/ms724284)。

MFC 仍然提供采用 MS-DOS 样式的时间自变量的 `CTime` 构造函数，但是，从 MFC 版本 3.0 开始，`CTime` 类还支持采用 Win32 `SYSTEMTIME` 结构的构造函数和另一个采用 Win32 `FILETIME` 结构的构造函数。

新的 `CTime` 构造函数是：

- CTime (const SYSTEMTIME & `sysTime`);

- CTime (const FILETIME & `fileTime`);

*FileTime*参数是对 Win32 引用`FILETIME`结构，它表示时间作为 64 位值，用于内部存储比以更方便格式`SYSTEMTIME`结构和 Win32 到使用的格式表示文件的创建时间。

如果你的代码包含使用系统时间初始化的 `CTime` 对象，你应该使用 Win32 中的 `SYSTEMTIME` 构造函数。

您很可能不会使用`CTime``FILETIME`直接初始化。 如果您使用`CFile`对象来处理一个文件， [cfile:: Getstatus](../mfc/reference/cfile-class.md#getstatus)为您通过检索文件时间戳`CTime`初始化对象，`FILETIME`结构。

## <a name="what-do-you-want-to-know-more-about"></a>你想要了解更多信息

- [常规日期和时间编程 MFC 中](../atl-mfc-shared/date-and-time.md)

- [自动化的日期和时间编程的支持](../atl-mfc-shared/date-and-time-automation-support.md)

## <a name="see-also"></a>请参阅

[日期和时间](../atl-mfc-shared/date-and-time.md)
