---
title: 如何：实现 IListSource 接口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], implementing
- IListSource interface
ms.assetid: 63ce27aa-2e23-4fbd-8228-0c1726f6c421
ms.openlocfilehash: 718514c843bbfc0fcc56e89ca0b60bd3ec65b3cf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970520"
---
# <a name="how-to-implement-the-ilistsource-interface"></a><span data-ttu-id="5a61a-102">如何：实现 IListSource 接口</span><span class="sxs-lookup"><span data-stu-id="5a61a-102">How to: Implement the IListSource Interface</span></span>
<span data-ttu-id="5a61a-103">实现 <xref:System.ComponentModel.IListSource> 接口可创建不实现的可绑定类， <xref:System.Collections.IList> 而是从另一个位置提供列表。</span><span class="sxs-lookup"><span data-stu-id="5a61a-103">Implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class that does not implement <xref:System.Collections.IList> but instead provides a list from another location.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a61a-104">示例</span><span class="sxs-lookup"><span data-stu-id="5a61a-104">Example</span></span>  
 <span data-ttu-id="5a61a-105">下面的代码示例演示如何实现 <xref:System.ComponentModel.IListSource> 接口。</span><span class="sxs-lookup"><span data-stu-id="5a61a-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.IListSource> interface.</span></span> <span data-ttu-id="5a61a-106">名为的组件 `EmployeeListSource` <xref:System.Collections.IList> 通过实现方法公开数据绑定的 <xref:System.ComponentModel.IListSource.GetList%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5a61a-106">A component named `EmployeeListSource` exposes an <xref:System.Collections.IList> for data binding by implementing the <xref:System.ComponentModel.IListSource.GetList%2A> method.</span></span>  
  
 [!code-csharp[System.ComponentModel.IListSource#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/EmployeeListSource.cs#1)]
 [!code-vb[System.ComponentModel.IListSource#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/EmployeeListSource.vb#1)]  
  
 [!code-csharp[System.ComponentModel.IListSource#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/Employee.cs#10)]
 [!code-vb[System.ComponentModel.IListSource#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/Employee.vb#10)]  
  
 [!code-csharp[System.ComponentModel.IListSource#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/BusinessObjectBase.cs#100)]
 [!code-vb[System.ComponentModel.IListSource#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/BusinessObjectBase.vb#100)]  
  
 [!code-csharp[System.ComponentModel.IListSource#1000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/Form1.cs#1000)]
 [!code-vb[System.ComponentModel.IListSource#1000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/Form1.vb#1000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5a61a-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="5a61a-107">Compiling the Code</span></span>  
 <span data-ttu-id="5a61a-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="5a61a-108">This example requires:</span></span>  
  
- <span data-ttu-id="5a61a-109">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="5a61a-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a61a-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a61a-110">See also</span></span>

- <xref:System.ComponentModel.IListSource>
- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [<span data-ttu-id="5a61a-111">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="5a61a-111">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
