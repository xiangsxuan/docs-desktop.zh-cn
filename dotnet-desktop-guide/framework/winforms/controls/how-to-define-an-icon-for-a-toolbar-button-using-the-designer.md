---
title: 如何：使用设计器定义工具栏按钮的图标
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971215"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="57d51-102">如何：使用设计器定义工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="57d51-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="57d51-103"><xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="57d51-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="57d51-104"><xref:System.Windows.Forms.ToolBar> 按钮能够显示它们中的图标，用户可以轻松识别。</span><span class="sxs-lookup"><span data-stu-id="57d51-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="57d51-105">这是通过向组件添加图像 <xref:System.Windows.Forms.ImageList> 并将其与控件相关联实现的 <xref:System.Windows.Forms.ToolBar> 。</span><span class="sxs-lookup"><span data-stu-id="57d51-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>

<span data-ttu-id="57d51-106">下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含 <xref:System.Windows.Forms.ToolBar> 控件和组件的窗体 <xref:System.Windows.Forms.ImageList> 。</span><span class="sxs-lookup"><span data-stu-id="57d51-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="57d51-107">有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="57d51-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="57d51-108">在设计时设置工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="57d51-108">To set an icon for a toolbar button at design time</span></span>

1. <span data-ttu-id="57d51-109">向组件添加映像 <xref:System.Windows.Forms.ImageList> 。</span><span class="sxs-lookup"><span data-stu-id="57d51-109">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="57d51-110">有关详细信息，请参阅 [如何：在设计器中添加或删除 ImageList 映像](how-to-add-or-remove-imagelist-images-with-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="57d51-110">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>

2. <span data-ttu-id="57d51-111">选择 <xref:System.Windows.Forms.ToolBar> 窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="57d51-111">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>

3. <span data-ttu-id="57d51-112">在 " **属性** " 窗口中，将 <xref:System.Windows.Forms.ToolBar> 控件的 <xref:System.Windows.Forms.ToolBar.ImageList%2A> 属性设置为 <xref:System.Windows.Forms.ImageList> 组件。</span><span class="sxs-lookup"><span data-stu-id="57d51-112">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>

4. <span data-ttu-id="57d51-113">单击 <xref:System.Windows.Forms.ToolBar> 控件的 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 属性以将其选中，然后单击省略号按钮 (省略号 ![ 按钮 ( ...) 属性窗口 ) ， ](./media/visual-studio-ellipsis-button.png) 以打开 **ToolBarButton 集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="57d51-113">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

5. <span data-ttu-id="57d51-114">使用 " **添加** " 按钮可将按钮添加到 <xref:System.Windows.Forms.ToolBar> 控件。</span><span class="sxs-lookup"><span data-stu-id="57d51-114">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>

6. <span data-ttu-id="57d51-115">在 **ToolBarButton 集合编辑器** 右侧窗格中显示的 "**属性**" 窗口中，将 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 每个工具栏按钮的属性设置为列表中的某个值，该列表是从添加到组件的图像中提取的 <xref:System.Windows.Forms.ImageList> 。</span><span class="sxs-lookup"><span data-stu-id="57d51-115">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>

## <a name="see-also"></a><span data-ttu-id="57d51-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57d51-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="57d51-117">如何：触发工具栏按钮的菜单事件</span><span class="sxs-lookup"><span data-stu-id="57d51-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="57d51-118">ToolBar 控件</span><span class="sxs-lookup"><span data-stu-id="57d51-118">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="57d51-119">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="57d51-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
