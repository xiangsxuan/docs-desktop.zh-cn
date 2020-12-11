---
title: 设置 DataGridView 控件的大小调整模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], setting sizing modes
- DataGridView control [Windows Forms], sizing modes
ms.assetid: e9ad15e6-b4bb-44aa-a767-3738e9db1651
ms.openlocfilehash: 15b084afa4149ac43d40aeae7f35f0eaff5ac0e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972665"
---
# <a name="how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="60ab1-102">如何：设置 Windows 窗体 DataGridView 控件的大小调整模式</span><span class="sxs-lookup"><span data-stu-id="60ab1-102">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="60ab1-103">以下步骤演示了自定义或组合用于 <xref:System.Windows.Forms.DataGridView> 控件和控件中特定列的调整大小选项的一些常见方案。</span><span class="sxs-lookup"><span data-stu-id="60ab1-103">The following procedures demonstrate some common scenarios that customize or combine the sizing options available for the <xref:System.Windows.Forms.DataGridView> control and for specific columns in a control.</span></span>  
  
### <a name="to-create-a-fixed-width-column"></a><span data-ttu-id="60ab1-104">若要创建固定宽度的列</span><span class="sxs-lookup"><span data-stu-id="60ab1-104">To create a fixed-width column</span></span>  
  
- <span data-ttu-id="60ab1-105">将 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>，<xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> 属性设置为 <xref:System.Windows.Forms.DataGridViewTriState.False>，<xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 属性设置为 `true`，并将 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> 属性设置为适当值。</span><span class="sxs-lookup"><span data-stu-id="60ab1-105">Set the <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> property to <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, the <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> property to <xref:System.Windows.Forms.DataGridViewTriState.False>, the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`, and the <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> property to an appropriate value.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### <a name="to-create-a-column-that-adjusts-its-size-to-fit-its-content"></a><span data-ttu-id="60ab1-106">若要创建可调整自身大小以完整显示内容的列</span><span class="sxs-lookup"><span data-stu-id="60ab1-106">To create a column that adjusts its size to fit its content</span></span>  
  
- <span data-ttu-id="60ab1-107">将 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 属性设置为基于内容调整大小的模式。</span><span class="sxs-lookup"><span data-stu-id="60ab1-107">Set the <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> property to a content-based sizing mode.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### <a name="to-create-fill-mode-columns-for-values-of-varying-size-and-importance"></a><span data-ttu-id="60ab1-108">若要为其大小和重要性不同的值创建填充模式列</span><span class="sxs-lookup"><span data-stu-id="60ab1-108">To create fill-mode columns for values of varying size and importance</span></span>  
  
- <span data-ttu-id="60ab1-109">将 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> 属性设置为 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>，从而为不会重写此值的所有列设置调整大小模式。</span><span class="sxs-lookup"><span data-stu-id="60ab1-109">Set the <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> to set the sizing mode for all columns that do not override this value.</span></span> <span data-ttu-id="60ab1-110">将列的 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 属性设置为与其平均内容宽度成正比的值。</span><span class="sxs-lookup"><span data-stu-id="60ab1-110">Set the <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> properties of the columns to values that are proportional to their average content widths.</span></span> <span data-ttu-id="60ab1-111">设置重要列的 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> 属性以确保显示部分内容。</span><span class="sxs-lookup"><span data-stu-id="60ab1-111">Set the <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> properties of important columns to ensure partial content display.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="60ab1-112">示例</span><span class="sxs-lookup"><span data-stu-id="60ab1-112">Example</span></span>  
 <span data-ttu-id="60ab1-113">以下完整的代码示例演示了应用程序，可帮助你了解本主题所描述的调整大小选项。</span><span class="sxs-lookup"><span data-stu-id="60ab1-113">The following complete code example provides a demonstration application that can help you understand the sizing options described in this topic.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 <span data-ttu-id="60ab1-114">使用此演示应用程序：</span><span class="sxs-lookup"><span data-stu-id="60ab1-114">To use this demonstration application:</span></span>  
  
- <span data-ttu-id="60ab1-115">更改窗体大小。</span><span class="sxs-lookup"><span data-stu-id="60ab1-115">Change the size of the form.</span></span> <span data-ttu-id="60ab1-116">观察填充模式列如何更改宽度并同时保留 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 属性值指示的比例。</span><span class="sxs-lookup"><span data-stu-id="60ab1-116">Observe how the fill-mode columns change their widths while retaining the proportions indicated by the <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> property values.</span></span> <span data-ttu-id="60ab1-117">观察窗体过小时列的 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> 如何防止其进行更改。</span><span class="sxs-lookup"><span data-stu-id="60ab1-117">Observe how a column's <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> prevents it from changing when the form is too small.</span></span>  
  
- <span data-ttu-id="60ab1-118">通过使用鼠标拖动列分隔线，更改列的大小。</span><span class="sxs-lookup"><span data-stu-id="60ab1-118">Change the column sizes by dragging the column dividers with the mouse.</span></span> <span data-ttu-id="60ab1-119">观察某些列如何无法调整大小，以及可调整大小的列如何无法比自身最小宽度更窄。</span><span class="sxs-lookup"><span data-stu-id="60ab1-119">Observe how some columns cannot be resized, and how resizable columns cannot be made narrower than their minimum widths.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="60ab1-120">编译代码</span><span class="sxs-lookup"><span data-stu-id="60ab1-120">Compiling the Code</span></span>  
 <span data-ttu-id="60ab1-121">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="60ab1-121">This example requires:</span></span>  
  
- <span data-ttu-id="60ab1-122">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="60ab1-122">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ab1-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60ab1-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
