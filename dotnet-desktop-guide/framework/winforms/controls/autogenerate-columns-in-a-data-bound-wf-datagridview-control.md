---
title: 自动生成 Data-Bound DataGridView 控件中的列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: 860e640e095537358d2f8778c810aa577e9d7ff0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971325"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="f52aa-102">如何：在已绑定数据的 Windows 窗体 DataGridView 控件中自动生成列</span><span class="sxs-lookup"><span data-stu-id="f52aa-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f52aa-103">下面的代码示例演示如何在控件中显示绑定数据源中的列 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="f52aa-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f52aa-104">当 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 属性值 `true` (默认值) 时，将为 <xref:System.Windows.Forms.DataGridViewColumn> 数据源表中的每个列创建一个。</span><span class="sxs-lookup"><span data-stu-id="f52aa-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="f52aa-105">如果在 <xref:System.Windows.Forms.DataGridView> 设置属性时该控件已经包含列 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> ，则将现有绑定列与数据源中的列进行比较，并在有匹配项时保留。</span><span class="sxs-lookup"><span data-stu-id="f52aa-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="f52aa-106">未绑定的列始终保留。</span><span class="sxs-lookup"><span data-stu-id="f52aa-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="f52aa-107">删除了数据源中没有匹配项的绑定列。</span><span class="sxs-lookup"><span data-stu-id="f52aa-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="f52aa-108">在控件中没有匹配项的数据源中的列将生成新 <xref:System.Windows.Forms.DataGridViewColumn> 的对象，这些对象将添加到集合的末尾 <xref:System.Windows.Forms.DataGridView.Columns%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f52aa-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f52aa-109">示例</span><span class="sxs-lookup"><span data-stu-id="f52aa-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f52aa-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="f52aa-110">Compiling the Code</span></span>  
 <span data-ttu-id="f52aa-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f52aa-111">This example requires:</span></span>  
  
- <span data-ttu-id="f52aa-112">名为 `customersDataGridView` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="f52aa-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
- <span data-ttu-id="f52aa-113">一个 <xref:System.Data.DataSet> 名为 `customersDataSet` 的对象，它具有名为的表 `Customers` 。</span><span class="sxs-lookup"><span data-stu-id="f52aa-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
- <span data-ttu-id="f52aa-114">对 <xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、<xref:System.Data?displayProperty=nameWithType> 和 <xref:System.Xml?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f52aa-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f52aa-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f52aa-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f52aa-116">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="f52aa-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f52aa-117">如何：从 Windows 窗体 DataGridView 控件中移除自动生成的列</span><span class="sxs-lookup"><span data-stu-id="f52aa-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
