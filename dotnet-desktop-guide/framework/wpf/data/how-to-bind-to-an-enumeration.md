---
title: 如何：绑定到枚举
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: c92f1f00aa3feb37b70aa9a3647265236a1625b2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970392"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="cda80-102">如何：绑定到枚举</span><span class="sxs-lookup"><span data-stu-id="cda80-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="cda80-103">此示例演示如何通过绑定到枚举的 GetValues 方法绑定到枚举。</span><span class="sxs-lookup"><span data-stu-id="cda80-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cda80-104">示例</span><span class="sxs-lookup"><span data-stu-id="cda80-104">Example</span></span>  
 <span data-ttu-id="cda80-105">在下面的示例中， <xref:System.Windows.Controls.ListBox> <xref:System.Windows.HorizontalAlignment> 通过数据绑定显示枚举值的列表。</span><span class="sxs-lookup"><span data-stu-id="cda80-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="cda80-106"><xref:System.Windows.Controls.ListBox>和将 <xref:System.Windows.Controls.Button> 绑定，以便您可以 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.Controls.Button> 通过在中选择一个值来更改的属性值 <xref:System.Windows.Controls.ListBox> 。</span><span class="sxs-lookup"><span data-stu-id="cda80-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="cda80-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cda80-107">See also</span></span>

- [<span data-ttu-id="cda80-108">绑定到方法</span><span class="sxs-lookup"><span data-stu-id="cda80-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="cda80-109">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="cda80-109">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="cda80-110">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="cda80-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
