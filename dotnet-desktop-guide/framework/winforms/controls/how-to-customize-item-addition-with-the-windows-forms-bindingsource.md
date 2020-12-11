---
title: 自定义项添加到 BindingSource 组件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
ms.openlocfilehash: 7d74fe6b4bbb1ddb94b359f5ba3ae32ed398d1dd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971216"
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a><span data-ttu-id="bb1bf-102">如何：使用 Windows 窗体 BindingSource 自定义项添加</span><span class="sxs-lookup"><span data-stu-id="bb1bf-102">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>
<span data-ttu-id="bb1bf-103">使用 <xref:System.Windows.Forms.BindingSource> 组件将 Windows 窗体控件绑定到数据源时，可能会发现需要自定义新项目的创建。</span><span class="sxs-lookup"><span data-stu-id="bb1bf-103">When you use a <xref:System.Windows.Forms.BindingSource> component to bind a Windows Forms control to a data source, you may find it necessary to customize the creation of new items.</span></span> <span data-ttu-id="bb1bf-104"><xref:System.Windows.Forms.BindingSource> 组件通过提供 <xref:System.Windows.Forms.BindingSource.AddingNew> 事件（通常在绑定的控件需要创建新项目时引发）使这种情况简单明了。</span><span class="sxs-lookup"><span data-stu-id="bb1bf-104">The <xref:System.Windows.Forms.BindingSource> component makes this straightforward by providing the <xref:System.Windows.Forms.BindingSource.AddingNew> event, which is typically raised when the bound control needs to create a new item.</span></span> <span data-ttu-id="bb1bf-105">事件处理程序可以提供所需的任何自定义行为（例如，在 Web 服务上调用方法或从类工厂中获取新对象）。</span><span class="sxs-lookup"><span data-stu-id="bb1bf-105">Your event handler can provide whatever custom behavior is required (for example, calling a method on a Web service or getting a new object from a class factory).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb1bf-106">通过处理 <xref:System.Windows.Forms.BindingSource.AddingNew> 事件添加项时，无法取消该添加。</span><span class="sxs-lookup"><span data-stu-id="bb1bf-106">When an item is added by handling the <xref:System.Windows.Forms.BindingSource.AddingNew> event, the addition cannot be canceled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb1bf-107">示例</span><span class="sxs-lookup"><span data-stu-id="bb1bf-107">Example</span></span>  
 <span data-ttu-id="bb1bf-108">下面的示例演示如何使用 <xref:System.Windows.Forms.DataGridView> 组件将 <xref:System.Windows.Forms.BindingSource> 控件绑定到类工厂。</span><span class="sxs-lookup"><span data-stu-id="bb1bf-108">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a class factory by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="bb1bf-109">用户单击 <xref:System.Windows.Forms.DataGridView> 控件的新行时，引发 <xref:System.Windows.Forms.BindingSource.AddingNew> 事件。</span><span class="sxs-lookup"><span data-stu-id="bb1bf-109">When the user clicks the <xref:System.Windows.Forms.DataGridView> control's new row, the <xref:System.Windows.Forms.BindingSource.AddingNew> event is raised.</span></span> <span data-ttu-id="bb1bf-110">事件处理程序创建一个新 `DemoCustomer` 对象，该对象被分配至 <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="bb1bf-110">The event handler creates a new `DemoCustomer` object, which is assigned to the <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="bb1bf-111">这将导致新 `DemoCustomer` 对象被添加到 <xref:System.Windows.Forms.BindingSource> 组件的列表中和显示在 <xref:System.Windows.Forms.DataGridView> 控件的新行中。</span><span class="sxs-lookup"><span data-stu-id="bb1bf-111">This causes the new `DemoCustomer` object to be added to the <xref:System.Windows.Forms.BindingSource> component's list and to be displayed in the new row of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bb1bf-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="bb1bf-112">Compiling the Code</span></span>  
 <span data-ttu-id="bb1bf-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="bb1bf-113">This example requires:</span></span>  
  
- <span data-ttu-id="bb1bf-114">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="bb1bf-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb1bf-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb1bf-115">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="bb1bf-116">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="bb1bf-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="bb1bf-117">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="bb1bf-117">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
