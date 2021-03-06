---
title: 图标的图像编辑器
ms.date: 10/17/2018
f1_keywords:
- vc.editors.cursor.F1
- vc.editors.icon.F1
- vc.editors.cursor
- vc.editors.bitmap.F1
helpviewer_keywords:
- editors, images
- resource editors [C++], graphics
- Image editor [C++]
- resource editors [C++], Image editor
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
ms.openlocfilehash: 4f27b4582da340d401c3ecf10b502453d80b6e7d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561507"
---
# <a name="image-editor-for-icons"></a>图标的图像编辑器

单击解决方案资源管理器的图像文件 （如.ico、.bmp、.png），图像将图像编辑器中打开方式在代码编辑器中打开代码文件完全相同。 图像编辑器选项卡处于活动状态，可以看到与用于创建和编辑映像的许多工具工具栏。 除了位图、图标和光标，你还可以使用 **“图像”** 菜单上的命令和 **“图像编辑器”** 工具栏上的工具来编辑 GIF 或 JPEG 格式的图像。

使用图像编辑器，可以执行下列操作：

- [编辑图形资源](../windows/editing-graphical-resources-image-editor-for-icons.md)

- [处理颜色](../windows/working-with-color-image-editor-for-icons.md)

- [处理图标和光标：显示设备的图像资源](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

- [使用图像编辑器命令的快捷键](../windows/accelerator-keys-image-editor-for-icons.md)

**的图像编辑器**窗口中显示的图像，并用一个拆分条分隔两个窗格的两个视图。 你可以将拆分条从一端拖动到另一端来更改窗格的相对大小。 活动窗格将显示选择边框。

**的图像编辑器**窗口可以进行调整以适合您的需要和首选项。 你可以 [更改放大因子](../windows/changing-the-magnification-factor-image-editor-for-icons.md) 以及 [显示或隐藏像素网格](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md)。

> [!NOTE]
> 使用**的图像编辑器**，可以查看 32 位映像，但不能编辑这些。

## <a name="visual-studio-image-library"></a>Visual Studio 图像库

可以免费下载**Visual Studio 图像库**其中包含许多动画、 位图和图标可以在你的应用程序中使用。 有关如何下载库的详细信息，请参阅 [Visual Studio 图像库](/visualstudio/designers/the-visual-studio-image-library)。

## <a name="managed-resources"></a>托管资源

可以使用**图像**编辑器并[二进制编辑器](binary-editor.md)来处理托管项目中的资源文件。 你要编辑的任何托管资源都必须是链接的资源。 Visual Studio 资源编辑器不支持编辑嵌入的资源。

有关将资源添加到托管项目的信息，请参阅[桌面应用中的资源](/dotnet/framework/resources/index)中 *.NET Framework 开发人员指南*。 有关手动将资源文件添加到托管项目、 访问资源、 显示静态资源和将资源字符串分配给属性的信息，请参阅[桌面应用中创建资源文件](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)。 全球化和本地化的托管应用中的资源的信息，请参阅[Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)。

## <a name="requirements"></a>要求

无

## <a name="see-also"></a>请参阅

[资源编辑器](../windows/resource-editors.md)<br/>
[图标](https://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)