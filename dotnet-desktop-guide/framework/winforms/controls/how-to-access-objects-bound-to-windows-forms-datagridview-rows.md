---
title: 访问绑定到 DataGridView 行的对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
ms.openlocfilehash: 0b9a4becb78ae817141728467c1e9ea5b693476d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971294"
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a><span data-ttu-id="f9798-102">如何：访问绑定到 Windows 窗体 DataGridView 行的对象</span><span class="sxs-lookup"><span data-stu-id="f9798-102">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>
<span data-ttu-id="f9798-103">有时，显示业务对象集合中存储的信息表很有用。</span><span class="sxs-lookup"><span data-stu-id="f9798-103">Sometimes it is useful to display a table of information stored in a collection of business objects.</span></span> <span data-ttu-id="f9798-104">将 <xref:System.Windows.Forms.DataGridView> 控件绑定到此类集合时，每个公共属性都将在它自己的列中显示，除非该属性已用 <xref:System.ComponentModel.BrowsableAttribute> 标记为不可浏览。</span><span class="sxs-lookup"><span data-stu-id="f9798-104">When you bind a <xref:System.Windows.Forms.DataGridView> control to such a collection, each public property is displayed in its own column unless the property has been marked non-browsable with a <xref:System.ComponentModel.BrowsableAttribute>.</span></span> <span data-ttu-id="f9798-105">例如，`Customer` 对象的集合包含“姓名”和“地址”等列。</span><span class="sxs-lookup"><span data-stu-id="f9798-105">For example, a collection of `Customer` objects would have columns such as **Name** and **Address**.</span></span>  
  
 <span data-ttu-id="f9798-106">如果这些对象包含你希望访问的附加信息和代码，则可以通过行对象来进行访问。</span><span class="sxs-lookup"><span data-stu-id="f9798-106">If these objects contain additional information and code that you want to access, you can reach it through row objects.</span></span> <span data-ttu-id="f9798-107">在下面的代码示例中，用户可以选择多行并单击一个按钮将发票发送给每个对应客户。</span><span class="sxs-lookup"><span data-stu-id="f9798-107">In the following code example, users can select multiple rows and click a button to send an invoice to each of the corresponding customers.</span></span>  
  
### <a name="to-access-row-bound-objects"></a><span data-ttu-id="f9798-108">访问行绑定对象</span><span class="sxs-lookup"><span data-stu-id="f9798-108">To access row-bound objects</span></span>  
  
- <span data-ttu-id="f9798-109">使用 <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="f9798-109">Use the <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="f9798-110">示例</span><span class="sxs-lookup"><span data-stu-id="f9798-110">Example</span></span>  
 <span data-ttu-id="f9798-111">完整的代码示例包括一个简单的 `Customer` 实现，并将 <xref:System.Windows.Forms.DataGridView> 绑定到一个包含几个 `Customer` 对象的 <xref:System.Collections.ArrayList>。</span><span class="sxs-lookup"><span data-stu-id="f9798-111">The complete code example includes a simple `Customer` implementation and binds the <xref:System.Windows.Forms.DataGridView> to an <xref:System.Collections.ArrayList> containing a few `Customer` objects.</span></span> <span data-ttu-id="f9798-112">因为在 <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> 事件处理程序之外无法访问客户集合，所以 <xref:System.Windows.Forms.Button?displayProperty=nameWithType> 的 <xref:System.Windows.Forms.Control.Click> 事件处理程序必须通过行访问 `Customer` 对象。</span><span class="sxs-lookup"><span data-stu-id="f9798-112">The <xref:System.Windows.Forms.Control.Click> event handler of the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> must access the `Customer` objects through the rows, because the customer collection is not accessible outside the <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> event handler.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f9798-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="f9798-113">Compiling the Code</span></span>  
 <span data-ttu-id="f9798-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f9798-114">This example requires:</span></span>  
  
- <span data-ttu-id="f9798-115">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f9798-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9798-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9798-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f9798-117">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="f9798-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f9798-118">如何：将对象绑定到 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="f9798-118">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)
