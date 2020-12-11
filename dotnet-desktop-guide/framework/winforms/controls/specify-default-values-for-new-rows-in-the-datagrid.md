---
title: 指定 DataGridView 控件中新行的默认值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: 364f922aefc10e57f2ed7f3a0c2a5b25c922d87a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971998"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="abfe9-102">如何：为 Windows 窗体 DataGridView 控件中的新行指定默认值</span><span class="sxs-lookup"><span data-stu-id="abfe9-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="abfe9-103">当应用程序在新添加的行中填充默认值时，可以更方便地输入数据。</span><span class="sxs-lookup"><span data-stu-id="abfe9-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="abfe9-104">利用 <xref:System.Windows.Forms.DataGridView> 类，您可以用事件填充默认值 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 。</span><span class="sxs-lookup"><span data-stu-id="abfe9-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="abfe9-105">当用户输入新记录的行时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="abfe9-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="abfe9-106">当代码处理此事件时，可以用所选的值填充所需的单元格。</span><span class="sxs-lookup"><span data-stu-id="abfe9-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="abfe9-107">下面的代码示例演示如何使用事件指定新行的默认值 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 。</span><span class="sxs-lookup"><span data-stu-id="abfe9-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abfe9-108">示例</span><span class="sxs-lookup"><span data-stu-id="abfe9-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="abfe9-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="abfe9-109">Compiling the Code</span></span>  
 <span data-ttu-id="abfe9-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="abfe9-110">This example requires:</span></span>  
  
- <span data-ttu-id="abfe9-111">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="abfe9-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="abfe9-112">`NewCustomerId`用于生成唯一值的函数 `CustomerID` 。</span><span class="sxs-lookup"><span data-stu-id="abfe9-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
- <span data-ttu-id="abfe9-113">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="abfe9-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abfe9-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abfe9-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="abfe9-115">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="abfe9-115">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="abfe9-116">在 Windows 窗体 DataGridView 控件中使用新记录行</span><span class="sxs-lookup"><span data-stu-id="abfe9-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
