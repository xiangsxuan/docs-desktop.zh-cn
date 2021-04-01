---
title: 如何：使用 ResourceDictionary 来管理可本地化的字符串资源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: 3e7a6813497a6a4a7251b49382ed32e4a7b521da
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971811"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>如何：使用 ResourceDictionary 来管理可本地化的字符串资源
此示例演示如何使用 <xref:System.Windows.ResourceDictionary> 来打包 (WPF) 应用程序 Windows Presentation Foundation 的可本地化字符串资源。  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>使用 ResourceDictionary 来管理可本地化的字符串资源  
  
1. 创建一个 <xref:System.Windows.ResourceDictionary> ，其中包含要本地化的字符串。 以下代码展示了一个示例。  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     此代码 `localizedMessage` <xref:System.String> 从 <xref:System> mscorlib.dll 中的命名空间定义类型为的字符串资源。  
  
2. <xref:System.Windows.ResourceDictionary>使用以下代码将添加到应用程序。  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. 使用类似于下面的标记的字符串资源 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. 通过如下所示的代码来使用代码隐藏文件中的字符串资源。  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. 对应用程序进行本地化。 有关详细信息，请参阅对 [应用程序进行本地化](how-to-localize-an-application.md)。
