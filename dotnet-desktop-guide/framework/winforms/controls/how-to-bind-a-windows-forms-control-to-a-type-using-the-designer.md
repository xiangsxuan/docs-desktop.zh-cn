---
title: 使用设计器将控件绑定到类型
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 2257489e123ceeea819ad3538952db51b726c7e5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971254"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="eba29-102">如何：使用设计器将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="eba29-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>

<span data-ttu-id="eba29-103">在生成与数据交互的控件时，有时需要将控件绑定到类型而非对象。</span><span class="sxs-lookup"><span data-stu-id="eba29-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="eba29-104">当数据可能不可用，但仍然希望数据绑定控件显示类型的公共接口中的信息时，通常需要在设计时将控件绑定到类型。</span><span class="sxs-lookup"><span data-stu-id="eba29-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="eba29-105">下面的过程演示如何创建一个 <xref:System.Windows.Forms.BindingSource> 绑定到类型的新，然后将该类型的一个属性绑定到的 <xref:System.Windows.Forms.TextBox.Text%2A> 属性 <xref:System.Windows.Forms.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="eba29-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>

### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="eba29-106">将 BindingSource 绑定到类型</span><span class="sxs-lookup"><span data-stu-id="eba29-106">To bind the BindingSource to a type</span></span>

1. <span data-ttu-id="eba29-107">创建 Windows 窗体 **项目 ("**  >  **新建**  >  **项目**" "  >  **Visual c #** " 或 " **Visual Basic**  >  **经典桌面**  >  **Windows 窗体应用程序**) "。</span><span class="sxs-lookup"><span data-stu-id="eba29-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="eba29-108">在 " **设计** " 视图中，将 <xref:System.Windows.Forms.BindingSource> 组件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="eba29-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>

3. <span data-ttu-id="eba29-109">在 " **属性** " 窗口中，单击属性的箭头 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 。</span><span class="sxs-lookup"><span data-stu-id="eba29-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>

4. <span data-ttu-id="eba29-110">在“DataSource UI 类型编辑器”中，单击“添加项目数据源”。</span><span class="sxs-lookup"><span data-stu-id="eba29-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>

5. <span data-ttu-id="eba29-111">在“选择数据源类型”页上，选择“对象”，并单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="eba29-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>

6. <span data-ttu-id="eba29-112">选择要绑定到的类型：</span><span class="sxs-lookup"><span data-stu-id="eba29-112">Select the type to bind to:</span></span>

    - <span data-ttu-id="eba29-113">如果要绑定到的类型位于当前项目，或者包含该类型的程序集已经作为引用添加，请展开节点以找到所需类型，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="eba29-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>

      <span data-ttu-id="eba29-114">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="eba29-114">\-or-</span></span>

    - <span data-ttu-id="eba29-115">如果要绑定到的类型位于另一个程序集中，当前不在引用列表中，请单击 " **添加引用**"，然后单击 " **项目** " 选项卡。选择包含所需业务对象的项目，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="eba29-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="eba29-116">此项目将显示在程序集列表中，因此可以展开节点以查找所需类型，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="eba29-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>

      > [!NOTE]
      > <span data-ttu-id="eba29-117">如果要绑定到框架或 Microsoft 程序集中的类型，请清除“隐藏以 Microsoft 或 System 开头的程序集”复选框。</span><span class="sxs-lookup"><span data-stu-id="eba29-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>

7. <span data-ttu-id="eba29-118">单击“下一步”  ，然后单击“完成”  。</span><span class="sxs-lookup"><span data-stu-id="eba29-118">Click **Next**, and then click **Finish**.</span></span>

### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="eba29-119">将控件绑定到 BindingSource</span><span class="sxs-lookup"><span data-stu-id="eba29-119">To bind the control to the BindingSource</span></span>

1. <span data-ttu-id="eba29-120">在窗体上添加一个 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="eba29-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>

2. <span data-ttu-id="eba29-121">在“属性”窗口中，展开“(DataBindings)”节点。</span><span class="sxs-lookup"><span data-stu-id="eba29-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>

3. <span data-ttu-id="eba29-122">单击属性旁边的箭头 <xref:System.Windows.Forms.TextBox.Text%2A> 。</span><span class="sxs-lookup"><span data-stu-id="eba29-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

4. <span data-ttu-id="eba29-123">在 " **数据源 UI 类型编辑器**" 中，展开 <xref:System.Windows.Forms.BindingSource> 之前添加的节点，并选择要绑定到的属性的绑定类型的属性 <xref:System.Windows.Forms.TextBox.Text%2A> <xref:System.Windows.Forms.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="eba29-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>

## <a name="see-also"></a><span data-ttu-id="eba29-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eba29-124">See also</span></span>

- [<span data-ttu-id="eba29-125">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="eba29-125">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="eba29-126">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="eba29-126">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
- [<span data-ttu-id="eba29-127">在 Visual Studio 中将控件绑定到数据</span><span class="sxs-lookup"><span data-stu-id="eba29-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
