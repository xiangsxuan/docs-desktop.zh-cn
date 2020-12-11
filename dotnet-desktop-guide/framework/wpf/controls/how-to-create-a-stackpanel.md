---
title: 如何：创建 StackPanel
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973562"
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="aacbe-102">如何：创建 StackPanel</span><span class="sxs-lookup"><span data-stu-id="aacbe-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="aacbe-103">此示例演示如何创建 <xref:System.Windows.Controls.StackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="aacbe-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aacbe-104">示例</span><span class="sxs-lookup"><span data-stu-id="aacbe-104">Example</span></span>  
 <span data-ttu-id="aacbe-105"><xref:System.Windows.Controls.StackPanel>允许你按指定方向堆叠元素。</span><span class="sxs-lookup"><span data-stu-id="aacbe-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="aacbe-106">通过使用在上定义的属性 <xref:System.Windows.Controls.StackPanel> ，内容可以垂直流动（这是默认设置），也可以水平流动。</span><span class="sxs-lookup"><span data-stu-id="aacbe-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="aacbe-107">下面的示例通过使用，垂直堆栈五个 <xref:System.Windows.Controls.TextBlock> 控件，每个控件都不同于 <xref:System.Windows.Controls.Border> 和 <xref:System.Windows.Controls.Border.Background%2A> <xref:System.Windows.Controls.StackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="aacbe-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="aacbe-108">没有指定 <xref:System.Windows.FrameworkElement.Width%2A> stretch 来填充父窗口的子元素; 但是，具有指定的子元素在 <xref:System.Windows.FrameworkElement.Width%2A> 窗口中居中。</span><span class="sxs-lookup"><span data-stu-id="aacbe-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="aacbe-109">中的默认堆栈方向 <xref:System.Windows.Controls.StackPanel> 是垂直的。</span><span class="sxs-lookup"><span data-stu-id="aacbe-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="aacbe-110">若要控制中的内容流 <xref:System.Windows.Controls.StackPanel> ，请使用 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="aacbe-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="aacbe-111">您可以使用属性控制水平对齐方式 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 。</span><span class="sxs-lookup"><span data-stu-id="aacbe-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aacbe-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aacbe-112">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="aacbe-113">面板概述</span><span class="sxs-lookup"><span data-stu-id="aacbe-113">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="aacbe-114">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="aacbe-114">How-to Topics</span></span>](stackpanel-how-to-topics.md)
