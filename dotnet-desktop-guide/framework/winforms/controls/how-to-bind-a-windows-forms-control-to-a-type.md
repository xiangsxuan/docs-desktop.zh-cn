---
title: 将控件绑定到类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: 0bc1f92ee8922990bd0e461655168f5618ba39a6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971895"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a><span data-ttu-id="b599a-102">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="b599a-102">How to: Bind a Windows Forms Control to a Type</span></span>
<span data-ttu-id="b599a-103">在生成与数据交互的控件时，有时需要将控件绑定到类型而非对象。</span><span class="sxs-lookup"><span data-stu-id="b599a-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="b599a-104">在设计时，如果数据不可用但数据绑定控件仍需要显示类型的公共接口中的信息，则尤其可能出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="b599a-104">This situation arises especially at design time, when data may not be available, but your data-bound controls still need to display information from a type's public interface.</span></span> <span data-ttu-id="b599a-105">例如，你可以将 <xref:System.Windows.Forms.DataGridView> 控件绑定到由 Web 服务公开的对象，并希望 <xref:System.Windows.Forms.DataGridView> 控件在设计时用自定义类型的成员名称标记其列。</span><span class="sxs-lookup"><span data-stu-id="b599a-105">For example, you may bind a <xref:System.Windows.Forms.DataGridView> control to an object exposed by a Web service and want the <xref:System.Windows.Forms.DataGridView> control to label its columns at design time with the member names of a custom type.</span></span>  
  
 <span data-ttu-id="b599a-106">你可以使用 <xref:System.Windows.Forms.BindingSource> 组件轻松将控件绑定到某一类型。</span><span class="sxs-lookup"><span data-stu-id="b599a-106">You can easily bind a control to a type with the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b599a-107">示例</span><span class="sxs-lookup"><span data-stu-id="b599a-107">Example</span></span>  
 <span data-ttu-id="b599a-108">下面的代码示例演示如何利用 <xref:System.Windows.Forms.BindingSource> 组件将 <xref:System.Windows.Forms.DataGridView> 控件绑定到一个自定义类型。</span><span class="sxs-lookup"><span data-stu-id="b599a-108">The following code example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a custom type by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="b599a-109">运行该示例时，你会注意到，在用数据填充控件之前，<xref:System.Windows.Forms.DataGridView> 具有反映 `Customer` 对象属性的标记列。</span><span class="sxs-lookup"><span data-stu-id="b599a-109">When you run the example, you'll notice the <xref:System.Windows.Forms.DataGridView> has labeled columns that reflect the properties of a `Customer` object, before the control is populated with data.</span></span> <span data-ttu-id="b599a-110">本示例具有“添加客户”按钮，用于将数据添加到 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="b599a-110">The example has an Add Customer button to add data to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b599a-111">单击该按钮时，一个新的 `Customer` 对象即添加到 <xref:System.Windows.Forms.BindingSource>。</span><span class="sxs-lookup"><span data-stu-id="b599a-111">When you click the button, a new `Customer` object is added to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="b599a-112">在实际情况中，可以通过调用 Web 服务或其他数据源来获取数据。</span><span class="sxs-lookup"><span data-stu-id="b599a-112">In a real-world scenario, the data might be obtained by a call to a Web service or other data source.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b599a-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="b599a-113">Compiling the Code</span></span>  
 <span data-ttu-id="b599a-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="b599a-114">This example requires:</span></span>  
  
- <span data-ttu-id="b599a-115">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="b599a-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b599a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b599a-116">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="b599a-117">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="b599a-117">BindingSource Component</span></span>](bindingsource-component.md)
