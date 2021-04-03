---
title: 如何：绑定两个控件的属性
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 28b5f65a57fc210f3d405020daa0d75c28b934c8
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970402"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="e2330-102">如何：绑定两个控件的属性</span><span class="sxs-lookup"><span data-stu-id="e2330-102">How to: Bind the Properties of Two Controls</span></span>

<span data-ttu-id="e2330-103">此示例演示如何使用属性将一个实例化控件的属性绑定到另一个实例化控件的属性 <xref:System.Windows.Data.Binding.ElementName%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e2330-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="e2330-104">示例</span><span class="sxs-lookup"><span data-stu-id="e2330-104">Example</span></span>

<span data-ttu-id="e2330-105">下面的示例演示如何将的 <xref:System.Windows.Controls.Panel.Background%2A> 属性绑定到的 <xref:System.Windows.Controls.Canvas> [SelectedItem](xref:System.Windows.Controls.ContentControl.Content%2A) 属性 <xref:System.Windows.Controls.ComboBox> ：</span><span class="sxs-lookup"><span data-stu-id="e2330-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the [SelectedItem.Content](xref:System.Windows.Controls.ContentControl.Content%2A) property of a <xref:System.Windows.Controls.ComboBox>:</span></span>

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

<span data-ttu-id="e2330-106">当此示例呈现时，应如下所示：</span><span class="sxs-lookup"><span data-stu-id="e2330-106">When this example is rendered it looks like the following:</span></span>

![屏幕截图，其中显示了值为绿色的组合框和绿色正方形。](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="e2330-108">在此示例中 (绑定目标属性， <xref:System.Windows.Controls.Panel.Background%2A> 属性) 必须是依赖属性。</span><span class="sxs-lookup"><span data-stu-id="e2330-108">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="e2330-109">有关详细信息，请参阅 [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。</span><span class="sxs-lookup"><span data-stu-id="e2330-109">For more information, see [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2330-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2330-110">See also</span></span>

- [<span data-ttu-id="e2330-111">指定绑定源</span><span class="sxs-lookup"><span data-stu-id="e2330-111">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="e2330-112">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="e2330-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
