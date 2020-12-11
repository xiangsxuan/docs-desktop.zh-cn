---
title: 关联快捷菜单与 NotifyIcon 组件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: 15a4a06726de348745e5eef03217d693db496a42
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971258"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="a0268-102">如何：将快捷菜单与 Windows 窗体 NotifyIcon 组件关联</span><span class="sxs-lookup"><span data-stu-id="a0268-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
> <span data-ttu-id="a0268-103">尽管 <xref:System.Windows.Forms.MenuStrip> 和 <xref:System.Windows.Forms.ContextMenuStrip> 将功能替换为 <xref:System.Windows.Forms.MainMenu> 以前版本的和控件，并将其 <xref:System.Windows.Forms.ContextMenu> 保留以 <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 实现后向兼容性和将来使用（如果你选择）。</span><span class="sxs-lookup"><span data-stu-id="a0268-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="a0268-104"><xref:System.Windows.Forms.NotifyIcon>组件在任务栏的状态通知区域中显示一个图标。</span><span class="sxs-lookup"><span data-stu-id="a0268-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="a0268-105">通常情况下，应用程序允许您右键单击此图标，将命令发送到它代表的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0268-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="a0268-106">通过 <xref:System.Windows.Forms.ContextMenu> 将组件与组件关联 <xref:System.Windows.Forms.NotifyIcon> ，你可以将此功能添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0268-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0268-107">如果希望在启动时最大程度地减少应用程序，同时在 <xref:System.Windows.Forms.NotifyIcon> 任务栏中显示组件的实例，请将主窗体的 <xref:System.Windows.Forms.Form.WindowState%2A> 属性设置为 <xref:System.Windows.Forms.FormWindowState.Minimized> ，并确保 <xref:System.Windows.Forms.NotifyIcon> 组件的 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="a0268-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="a0268-108">在设计时将快捷菜单与 NotifyIcon 组件关联</span><span class="sxs-lookup"><span data-stu-id="a0268-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1. <span data-ttu-id="a0268-109">将 <xref:System.Windows.Forms.NotifyIcon> 组件添加到窗体，并设置重要属性，如 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 和 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a0268-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="a0268-110">有关详细信息，请参阅 [如何：向任务栏添加应用程序图标以及 Windows 窗体 NotifyIcon 组件](app-icons-to-the-taskbar-with-wf-notifyicon.md)。</span><span class="sxs-lookup"><span data-stu-id="a0268-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2. <span data-ttu-id="a0268-111">将 <xref:System.Windows.Forms.ContextMenu> 组件添加到 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="a0268-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="a0268-112">将菜单项添加到快捷菜单，表示要在运行时使用的命令。</span><span class="sxs-lookup"><span data-stu-id="a0268-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="a0268-113">这也是向这些菜单项添加菜单增强功能（如访问密钥）的好时机。</span><span class="sxs-lookup"><span data-stu-id="a0268-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3. <span data-ttu-id="a0268-114">将 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 组件的属性设置 <xref:System.Windows.Forms.NotifyIcon> 为添加的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="a0268-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="a0268-115">设置此属性后，单击任务栏上的图标时，将显示快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="a0268-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="a0268-116">以编程方式将快捷菜单与 NotifyIcon 组件相关联</span><span class="sxs-lookup"><span data-stu-id="a0268-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1. <span data-ttu-id="a0268-117">创建 <xref:System.Windows.Forms.NotifyIcon> 类和类的实例 <xref:System.Windows.Forms.ContextMenu> ，其中包含应用程序所需的任何属性设置 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 、组件) 的 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> <xref:System.Windows.Forms.NotifyIcon> 菜单项 (<xref:System.Windows.Forms.ContextMenu> 。</span><span class="sxs-lookup"><span data-stu-id="a0268-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2. <span data-ttu-id="a0268-118">将 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 组件的属性设置 <xref:System.Windows.Forms.NotifyIcon> 为添加的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="a0268-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="a0268-119">设置此属性后，单击任务栏上的图标时，将显示快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="a0268-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a0268-120">下面的代码示例创建一个基本菜单结构。</span><span class="sxs-lookup"><span data-stu-id="a0268-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="a0268-121">您将需要自定义菜单选项，使其适合您正在开发的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0268-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="a0268-122">此外，您还需要编写代码来处理 <xref:System.Windows.Forms.MenuItem.Click> 这些菜单项的事件。</span><span class="sxs-lookup"><span data-stu-id="a0268-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _
          (System.Environment.GetFolderPath _
          (System.Environment.SpecialFolder.Personal)  _
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
> <span data-ttu-id="a0268-123">您必须 `notifyIcon1` `contextMenu1,` 通过在您的窗体的构造函数中包含以下语句来初始化和可执行的操作：</span><span class="sxs-lookup"><span data-stu-id="a0268-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0268-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0268-124">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="a0268-125">如何：使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标</span><span class="sxs-lookup"><span data-stu-id="a0268-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="a0268-126">NotifyIcon 组件</span><span class="sxs-lookup"><span data-stu-id="a0268-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="a0268-127">NotifyIcon 组件概述</span><span class="sxs-lookup"><span data-stu-id="a0268-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
