---
title: 向任务栏添加应用程序图标，其中包含 NotifyIcon 组件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: 46b50ecaabe75dba08fea922d7b5639031692269
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971326"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>如何：使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标

Windows 窗体 <xref:System.Windows.Forms.NotifyIcon> 组件在任务栏的状态通知区域中显示一个图标。 若要在状态区域中显示多个图标，你的 <xref:System.Windows.Forms.NotifyIcon> 窗体上必须有多个组件。 若要设置为控件显示的图标，请使用 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 属性。 您还可以在事件处理程序中编写代码， <xref:System.Windows.Forms.NotifyIcon.DoubleClick> 以便用户双击图标时发生某些情况。 例如，您可以为用户显示一个对话框，以便配置由该图标表示的后台进程。

> [!NOTE]
> 该 <xref:System.Windows.Forms.NotifyIcon> 组件仅用于通知目的，以便提醒用户发生了某个操作或事件或某个排序的状态发生更改。 应使用菜单、工具栏和其他用户界面元素与应用程序进行标准交互。

### <a name="to-set-the-icon"></a>设置图标

1. 为 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 属性赋值。 该值必须为类型 `System.Drawing.Icon` ，并且可从 .ico 文件加载。 您可以在代码中指定图标文件，或通过单击省略号按钮 (![ Visual) Studio 属性窗口中的省略号按钮 ( ... ) "。在 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.NotifyIcon.Icon%2A> " **属性** "窗口中的属性旁边，然后在出现的" **打开** "对话框中选择该文件。

2. 将 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性设置为 `true`。

3. 将 <xref:System.Windows.Forms.NotifyIcon.Text%2A> 属性设置为相应的工具提示字符串。

     在下面的代码示例中，为图标位置设置的路径是 "我的 **文档** " 文件夹。 使用此位置的原因是，你可以假定大多数运行 Windows 操作系统的计算机都包含此文件夹。 选择此位置还能使具有最低系统访问级别的用户安全运行该应用程序。 下面的示例要求窗体 <xref:System.Windows.Forms.NotifyIcon> 已添加控件。 它还需要一个名为的图标文件 `Icon.ico` 。

    ```vb
    ' You should replace the bold icon in the sample below
    ' with an icon of your own choosing.
    NotifyIcon1.Icon = New _
       System.Drawing.Icon(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Icon.ico")
    NotifyIcon1.Visible = True
    NotifyIcon1.Text = "Antivirus program"
    ```

    ```csharp
    // You should replace the bold icon in the sample below
    // with an icon of your own choosing.
    // Note the escape character used (@) when specifying the path.
    notifyIcon1.Icon =
       new System.Drawing.Icon (System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Icon.ico");
    notifyIcon1.Visible = true;
    notifyIcon1.Text = "Antivirus program";
    ```

    ```cpp
    // You should replace the bold icon in the sample below
    // with an icon of your own choosing.
    notifyIcon1->Icon = gcnew
       System::Drawing::Icon(String::Concat
       (System::Environment::GetFolderPath
       (System::Environment::SpecialFolder::Personal),
       "\\Icon.ico"));
    notifyIcon1->Visible = true;
    notifyIcon1->Text = "Antivirus program";
    ```

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [如何：将快捷菜单与 Windows 窗体 NotifyIcon 组件关联](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [NotifyIcon 组件](notifyicon-component-windows-forms.md)
- [NotifyIcon 组件概述](notifyicon-component-overview-windows-forms.md)
