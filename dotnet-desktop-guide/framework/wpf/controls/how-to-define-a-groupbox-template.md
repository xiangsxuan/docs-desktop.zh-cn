---
title: 如何：定义 GroupBox 模板
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: f04e4a7e3feb4bd7c5dac1b4127d48923fb7ea62
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973718"
---
# <a name="how-to-define-a-groupbox-template"></a>如何：定义 GroupBox 模板

此示例演示如何为控件创建模板 <xref:System.Windows.Controls.GroupBox> 。  
  
## <a name="example"></a>示例  

 下面的示例 <xref:System.Windows.Controls.GroupBox> 通过使用布局控件定义控件模板 <xref:System.Windows.Controls.Grid> 。 模板使用 <xref:System.Windows.Controls.BorderGapMaskConverter> 来定义的边框， <xref:System.Windows.Controls.GroupBox> 以使边框不会遮盖 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 内容。  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.GroupBox>
- [如何：创建分组框](/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))
