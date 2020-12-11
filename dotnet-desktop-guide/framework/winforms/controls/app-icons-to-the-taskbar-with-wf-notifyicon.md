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
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="0977b-102">如何：使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标</span><span class="sxs-lookup"><span data-stu-id="0977b-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>

<span data-ttu-id="0977b-103">Windows 窗体 <xref:System.Windows.Forms.NotifyIcon> 组件在任务栏的状态通知区域中显示一个图标。</span><span class="sxs-lookup"><span data-stu-id="0977b-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="0977b-104">若要在状态区域中显示多个图标，你的 <xref:System.Windows.Forms.NotifyIcon> 窗体上必须有多个组件。</span><span class="sxs-lookup"><span data-stu-id="0977b-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="0977b-105">若要设置为控件显示的图标，请使用 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0977b-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="0977b-106">您还可以在事件处理程序中编写代码， <xref:System.Windows.Forms.NotifyIcon.DoubleClick> 以便用户双击图标时发生某些情况。</span><span class="sxs-lookup"><span data-stu-id="0977b-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="0977b-107">例如，您可以为用户显示一个对话框，以便配置由该图标表示的后台进程。</span><span class="sxs-lookup"><span data-stu-id="0977b-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>

> [!NOTE]
> <span data-ttu-id="0977b-108">该 <xref:System.Windows.Forms.NotifyIcon> 组件仅用于通知目的，以便提醒用户发生了某个操作或事件或某个排序的状态发生更改。</span><span class="sxs-lookup"><span data-stu-id="0977b-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="0977b-109">应使用菜单、工具栏和其他用户界面元素与应用程序进行标准交互。</span><span class="sxs-lookup"><span data-stu-id="0977b-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>

### <a name="to-set-the-icon"></a><span data-ttu-id="0977b-110">设置图标</span><span class="sxs-lookup"><span data-stu-id="0977b-110">To set the icon</span></span>

1. <span data-ttu-id="0977b-111">为 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 属性赋值。</span><span class="sxs-lookup"><span data-stu-id="0977b-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="0977b-112">该值必须为类型 `System.Drawing.Icon` ，并且可从 .ico 文件加载。</span><span class="sxs-lookup"><span data-stu-id="0977b-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="0977b-113">您可以在代码中指定图标文件，或通过单击省略号按钮 (![ Visual) Studio 属性窗口中的省略号按钮 ( ... ) "。在 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.NotifyIcon.Icon%2A> " **属性** "窗口中的属性旁边，然后在出现的" **打开** "对话框中选择该文件。</span><span class="sxs-lookup"><span data-stu-id="0977b-113">You can specify the icon file in code or by clicking the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>

2. <span data-ttu-id="0977b-114">将 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0977b-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>

3. <span data-ttu-id="0977b-115">将 <xref:System.Windows.Forms.NotifyIcon.Text%2A> 属性设置为相应的工具提示字符串。</span><span class="sxs-lookup"><span data-stu-id="0977b-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>

     <span data-ttu-id="0977b-116">在下面的代码示例中，为图标位置设置的路径是 "我的 **文档** " 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0977b-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="0977b-117">使用此位置的原因是，你可以假定大多数运行 Windows 操作系统的计算机都包含此文件夹。</span><span class="sxs-lookup"><span data-stu-id="0977b-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="0977b-118">选择此位置还能使具有最低系统访问级别的用户安全运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="0977b-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="0977b-119">下面的示例要求窗体 <xref:System.Windows.Forms.NotifyIcon> 已添加控件。</span><span class="sxs-lookup"><span data-stu-id="0977b-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="0977b-120">它还需要一个名为的图标文件 `Icon.ico` 。</span><span class="sxs-lookup"><span data-stu-id="0977b-120">It also requires an icon file named `Icon.ico`.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0977b-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0977b-121">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="0977b-122">如何：将快捷菜单与 Windows 窗体 NotifyIcon 组件关联</span><span class="sxs-lookup"><span data-stu-id="0977b-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="0977b-123">NotifyIcon 组件</span><span class="sxs-lookup"><span data-stu-id="0977b-123">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="0977b-124">NotifyIcon 组件概述</span><span class="sxs-lookup"><span data-stu-id="0977b-124">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
