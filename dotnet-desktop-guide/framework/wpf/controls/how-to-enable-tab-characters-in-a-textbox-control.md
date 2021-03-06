---
title: 如何：在 TextBox 控件中启用制表符
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], enabling tab characters
- tab characters [WPF], enabling
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
ms.openlocfilehash: 9a01ae93d1b75c604fbe4f15f720e0a84086bd1a
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973318"
---
# <a name="how-to-enable-tab-characters-in-a-textbox-control"></a>如何：在 TextBox 控件中启用制表符
此示例演示如何在控件中启用制表符作为一般输入接受 <xref:System.Windows.Controls.TextBox> 。  
  
## <a name="example"></a>示例  
 若要在控件中启用制表符作为输入 <xref:System.Windows.Controls.TextBox> ，请将 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> 属性设置为 **true**。  
  
 [!code-xaml[TextBox_EnablingTab#_AcceptsTab](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## <a name="see-also"></a>另请参阅

- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
