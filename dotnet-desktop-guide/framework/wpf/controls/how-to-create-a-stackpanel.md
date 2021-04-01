---
title: 如何：创建 StackPanel
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973562"
---
# <a name="how-to-create-a-stackpanel"></a>如何：创建 StackPanel
此示例演示如何创建 <xref:System.Windows.Controls.StackPanel> 。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.StackPanel>允许你按指定方向堆叠元素。 通过使用在上定义的属性 <xref:System.Windows.Controls.StackPanel> ，内容可以垂直流动（这是默认设置），也可以水平流动。  
  
 下面的示例通过使用，垂直堆栈五个 <xref:System.Windows.Controls.TextBlock> 控件，每个控件都不同于 <xref:System.Windows.Controls.Border> 和 <xref:System.Windows.Controls.Border.Background%2A> <xref:System.Windows.Controls.StackPanel> 。 没有指定 <xref:System.Windows.FrameworkElement.Width%2A> stretch 来填充父窗口的子元素; 但是，具有指定的子元素在 <xref:System.Windows.FrameworkElement.Width%2A> 窗口中居中。  
  
 中的默认堆栈方向 <xref:System.Windows.Controls.StackPanel> 是垂直的。 若要控制中的内容流 <xref:System.Windows.Controls.StackPanel> ，请使用 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 属性。 您可以使用属性控制水平对齐方式 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 。  
  
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
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.StackPanel>
- [面板概述](panels-overview.md)
- [操作指南主题](stackpanel-how-to-topics.md)
