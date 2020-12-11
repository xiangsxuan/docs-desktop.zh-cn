---
title: 如何：重写逻辑树
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973655"
---
# <a name="how-to-override-the-logical-tree"></a>如何：重写逻辑树
尽管在大多数情况下不必重写逻辑树，但资深的控件创作者可选择执行此操作。  
  
## <a name="example"></a>示例  
 此示例说明如何为 <xref:System.Windows.Controls.StackPanel> 重写逻辑树划分子类，这种情况下，可以强制执行面板仅呈现一个子元素的行为。 这不一定是实际需要的行为，但在这里进行演示是为了举例说明重写元素的正常逻辑树的情况。  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 有关逻辑树的详细信息，请参阅 [WPF 中的树](trees-in-wpf.md)。
