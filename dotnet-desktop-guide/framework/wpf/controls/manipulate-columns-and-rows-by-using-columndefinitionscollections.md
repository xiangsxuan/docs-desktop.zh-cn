---
title: 如何：使用 ColumnDefinitionsCollection 和 RowDefinitionsCollection 来操作列和行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: 2f6d174fd54dca3744e5967f198c645e01a94fe5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973195"
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a><span data-ttu-id="1cff0-102">如何：使用 ColumnDefinitionsCollection 和 RowDefinitionsCollection 来操作列和行</span><span class="sxs-lookup"><span data-stu-id="1cff0-102">How to: Manipulate Columns and Rows by Using ColumnDefinitionsCollections and RowDefinitionsCollections</span></span>
<span data-ttu-id="1cff0-103">此示例演示如何使用和类中的方法 <xref:System.Windows.Controls.ColumnDefinitionCollection> <xref:System.Windows.Controls.RowDefinitionCollection> 来执行诸如添加、清除或计算行或列内容的操作。</span><span class="sxs-lookup"><span data-stu-id="1cff0-103">This example shows how to use the methods in the <xref:System.Windows.Controls.ColumnDefinitionCollection> and <xref:System.Windows.Controls.RowDefinitionCollection> classes to perform actions like adding, clearing, or counting the contents of rows or columns.</span></span> <span data-ttu-id="1cff0-104">例如，您可以 <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A> 、 <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A> ，也可以 <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> 是或中包含的项 <xref:System.Windows.Controls.ColumnDefinition> <xref:System.Windows.Controls.RowDefinition> 。</span><span class="sxs-lookup"><span data-stu-id="1cff0-104">For example, you can <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, or <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> the items that are included in a <xref:System.Windows.Controls.ColumnDefinition> or <xref:System.Windows.Controls.RowDefinition>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cff0-105">示例</span><span class="sxs-lookup"><span data-stu-id="1cff0-105">Example</span></span>  
 <span data-ttu-id="1cff0-106">下面的示例创建一个 <xref:System.Windows.Controls.Grid> 元素，该元素 <xref:System.Windows.FrameworkElement.Name%2A> 的为 `grid1` 。</span><span class="sxs-lookup"><span data-stu-id="1cff0-106">The following example creates a <xref:System.Windows.Controls.Grid> element with a <xref:System.Windows.FrameworkElement.Name%2A> of `grid1`.</span></span> <span data-ttu-id="1cff0-107"><xref:System.Windows.Controls.Grid>包含一个 <xref:System.Windows.Controls.StackPanel> ，它保存 <xref:System.Windows.Controls.Button> 元素，每个元素由不同的集合方法控制。</span><span class="sxs-lookup"><span data-stu-id="1cff0-107">The <xref:System.Windows.Controls.Grid> contains a <xref:System.Windows.Controls.StackPanel> that holds <xref:System.Windows.Controls.Button> elements, each controlled by a different collection method.</span></span> <span data-ttu-id="1cff0-108">单击时 <xref:System.Windows.Controls.Button> ，它会激活代码隐藏文件中的方法调用。</span><span class="sxs-lookup"><span data-stu-id="1cff0-108">When you click a <xref:System.Windows.Controls.Button>, it activates a method call in the code-behind file.</span></span>  
  
 [!code-xaml[ColumnDefinitionsGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="1cff0-109">此示例定义了一系列自定义方法，每个方法都对应于 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 文件中的一个事件 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="1cff0-109">This example defines a series of custom methods, each corresponding to a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="1cff0-110">您可以通过多种方式更改中的列和行的数目 <xref:System.Windows.Controls.Grid> ，包括添加或删除行和列，以及计算总行数和列数。</span><span class="sxs-lookup"><span data-stu-id="1cff0-110">You can change the number of columns and rows in the <xref:System.Windows.Controls.Grid> in several ways, which includes adding or removing rows and columns; and counting the total number of rows and columns.</span></span> <span data-ttu-id="1cff0-111">若要防止 <xref:System.ArgumentOutOfRangeException> 和 <xref:System.ArgumentException> 异常，可以使用方法提供的错误检查功能 <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> 。</span><span class="sxs-lookup"><span data-stu-id="1cff0-111">To prevent <xref:System.ArgumentOutOfRangeException> and <xref:System.ArgumentException> exceptions, you can use the error-checking functionality that the <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> method provides.</span></span>  
  
 [!code-csharp[ColumnDefinitionsGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1cff0-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cff0-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.ColumnDefinitionCollection>
- <xref:System.Windows.Controls.RowDefinitionCollection>
