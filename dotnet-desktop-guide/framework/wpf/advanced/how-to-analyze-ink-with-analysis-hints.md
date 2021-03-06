---
title: 如何：通过分析提示来分析墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
ms.openlocfilehash: 5e94628d357a2ca75ad1b6fb7e464a3355f1fd5f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971928"
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a>如何：通过分析提示来分析墨迹

[AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90))为它所附加到的[InkAnalyzer](/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90))提供了一种提示（& a）。  该提示适用于[AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90))的[ContextNode% 2a](/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90))属性所指定的区域，并向 Ink 分析器提供额外的上下文，以提高识别准确率的准确性。 当分析从提示区域内获取的墨迹时， [InkAnalyzer](/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) 将应用此上下文信息。  
  
## <a name="example"></a>示例  

 下面的示例是一个应用程序，它在接受墨迹输入的窗体上使用了多个 [AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) 对象。 应用程序使用 [AnalysisHintNode% 2a](/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) 属性为窗体上的每个条目提供上下文信息。  在用户停止添加墨迹后，应用程序使用后台分析来分析墨迹并清除所有墨迹的形式。  
  
 [!code-xaml[HowToAnalyzeInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
