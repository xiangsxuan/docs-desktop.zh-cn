---
title: 在 Windows 窗体应用程序中响应字体方案更改
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973304"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="e43e0-102">如何：在 Windows 窗体应用程序中响应字体方案更改</span><span class="sxs-lookup"><span data-stu-id="e43e0-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="e43e0-103">在 Windows 操作系统中，用户可以更改系统范围的字体设置，使默认字体显得更大或更小。</span><span class="sxs-lookup"><span data-stu-id="e43e0-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="e43e0-104">更改这些字体设置对于视觉障碍的用户非常重要，需要更大的类型才能在屏幕上读取文本。</span><span class="sxs-lookup"><span data-stu-id="e43e0-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="e43e0-105">可以通过增加或减少窗体的大小和所有包含的文本，只要字体方案发生更改，就可以调整 Windows 窗体应用程序来做出这些更改。</span><span class="sxs-lookup"><span data-stu-id="e43e0-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="e43e0-106">如果希望窗体动态地适应字体大小的变化，则可以将代码添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="e43e0-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="e43e0-107">通常情况下，Windows 窗体使用的默认字体是由 <xref:Microsoft.Win32> 命名空间调用返回的字体 `GetStockObject(DEFAULT_GUI_FONT)` 。</span><span class="sxs-lookup"><span data-stu-id="e43e0-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="e43e0-108">此调用返回的字体仅在屏幕分辨率发生更改时才会更改。</span><span class="sxs-lookup"><span data-stu-id="e43e0-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="e43e0-109">如下面的过程所示，你的代码必须将默认字体更改为 <xref:System.Drawing.SystemFonts.IconTitleFont%2A> ，以响应字体大小的变化。</span><span class="sxs-lookup"><span data-stu-id="e43e0-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="e43e0-110">使用桌面字体并响应字体方案更改</span><span class="sxs-lookup"><span data-stu-id="e43e0-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1. <span data-ttu-id="e43e0-111">创建窗体，并向其添加所需的控件。</span><span class="sxs-lookup"><span data-stu-id="e43e0-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="e43e0-112">有关详细信息，请参阅 [如何：从命令行创建 Windows 窗体应用程序](how-to-create-a-windows-forms-application-from-the-command-line.md) 和 [要在 Windows 窗体上使用的控件](./controls/controls-to-use-on-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="e43e0-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="e43e0-113">向代码添加对 <xref:Microsoft.Win32> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="e43e0-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="e43e0-114">将以下代码添加到窗体的构造函数，以挂钩必需的事件处理程序，并更改窗体使用的默认字体。</span><span class="sxs-lookup"><span data-stu-id="e43e0-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="e43e0-115">实现事件的处理程序 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> ，该事件使窗体在类别更改时自动缩放 <xref:Microsoft.Win32.UserPreferenceCategory.Window> 。</span><span class="sxs-lookup"><span data-stu-id="e43e0-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. <span data-ttu-id="e43e0-116">最后，为 <xref:System.Windows.Forms.Form.FormClosing> 分离 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 事件处理程序的事件实现处理程序。</span><span class="sxs-lookup"><span data-stu-id="e43e0-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="e43e0-117">如果不包含此代码，将导致应用程序泄漏内存。</span><span class="sxs-lookup"><span data-stu-id="e43e0-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. <span data-ttu-id="e43e0-118">编译并运行该代码。</span><span class="sxs-lookup"><span data-stu-id="e43e0-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="e43e0-119">在 Windows XP 中手动更改字体方案</span><span class="sxs-lookup"><span data-stu-id="e43e0-119">To manually change the font scheme in Windows XP</span></span>  
  
1. <span data-ttu-id="e43e0-120">在 Windows 窗体应用程序运行时，右键单击 Windows 桌面并从快捷菜单中选择 " **属性** "。</span><span class="sxs-lookup"><span data-stu-id="e43e0-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="e43e0-121">在 " **显示属性** " 对话框中，单击 " **外观** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e43e0-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3. <span data-ttu-id="e43e0-122">从 " **字体大小** " 下拉列表框中，选择新字号。</span><span class="sxs-lookup"><span data-stu-id="e43e0-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="e43e0-123">你会注意到，窗体现在会对桌面字体方案中的运行时更改做出反应。</span><span class="sxs-lookup"><span data-stu-id="e43e0-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="e43e0-124">当用户在 **普通**、 **大型字体** 和 **超大字体** 之间更改时，窗体将更改字体并正确缩放。</span><span class="sxs-lookup"><span data-stu-id="e43e0-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e43e0-125">示例</span><span class="sxs-lookup"><span data-stu-id="e43e0-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="e43e0-126">此代码示例中的构造函数包含对的调用 `InitializeComponent` ，该调用是在 Visual Studio 中创建新 Windows 窗体项目时定义的。</span><span class="sxs-lookup"><span data-stu-id="e43e0-126">The constructor in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="e43e0-127">如果要在命令行上生成应用程序，请删除此代码行。</span><span class="sxs-lookup"><span data-stu-id="e43e0-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43e0-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e43e0-128">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="e43e0-129">Windows 窗体中的自动缩放</span><span class="sxs-lookup"><span data-stu-id="e43e0-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
