---
title: 如何：从 UserControl 类继承
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5c278cfadd1bb0c9720718c08791a37f90d964d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972521"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a>如何：从 UserControl 类继承

若要通过自定义代码将一个或多个 Windows 窗体控件的功能进行组合，可以创建一个用户控件。 用户控件将快速控件开发、标准 Windows 窗体控件功能以及自定义属性和方法的多功能组合在一起。 开始创建用户控件时，系统将为你提供一个可见的设计器，可以将标准 Windows 窗体控件放置在该设计器中。 这些控件保留其所有继承的功能以及标准控件的外观和行为。 但是，一旦将这些控件内置到用户控件中，便不能再通过代码来使用。 用户控件执行其自身的绘图工作，同时也处理与控件相关联的所有基本功能。

## <a name="to-create-a-user-control"></a>创建用户控件

1. 在 Visual Studio 中创建新的 **Windows 控件库** 项目。

   新创建的项目中将包含一个空白用户控件。

2. 将控件从“工具箱”的“Windows 窗体”选项卡中拖到设计器上。

3. 应对这些控件进行定位并设计成你希望它们显示在最终用户控件中的样子。 如果要允许开发人员访问构成控件，则必须将这些控件声明为公共的，或有选择地公开构成控件的属性。 有关详细信息，请参阅[如何：公开构成控件的属性](how-to-expose-properties-of-constituent-controls.md)。

4. 实现控件将纳入的任何自定义方法或属性。

5. 按 **F5** 生成项目并在 " **UserControl 测试容器**" 中运行控件。 有关详细信息，请参阅 [如何：测试 UserControl 的 Run-Time 行为](how-to-test-the-run-time-behavior-of-a-usercontrol.md)。

## <a name="see-also"></a>另请参阅

- [各种自定义控件](varieties-of-custom-controls.md)
- [如何：从 Control 类继承](how-to-inherit-from-the-control-class.md)
- [如何：从现有 Windows 窗体控件继承](how-to-inherit-from-existing-windows-forms-controls.md)
- [如何：创作 Windows 窗体的控件](how-to-author-controls-for-windows-forms.md)
- [排查 Visual Basic 中继承的事件处理程序问题](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)
- [如何：测试 UserControl 的运行时行为](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
