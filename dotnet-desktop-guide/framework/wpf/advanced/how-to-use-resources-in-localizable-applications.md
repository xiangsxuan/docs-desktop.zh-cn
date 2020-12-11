---
title: 如何：使用可本地化的应用程序中的资源
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970963"
---
# <a name="how-to-use-resources-in-localizable-apps"></a>如何：在可本地化的应用中使用资源

本地化是指使用户界面适应不同的文化。 为此，必须翻译标题、标题和列表框项等文本。 为了更轻松地进行翻译，要翻译的项将收集到资源文件中。 有关如何创建用于本地化的资源文件的信息，请参阅 [本地化应用程序](how-to-localize-an-application.md) 。 若要使 WPF 应用程序可本地化，开发人员需要将所有可本地化的资源生成到一个资源程序集中。 资源程序集本地化为不同的语言，代码隐藏使用资源管理 API 进行加载。

## <a name="example"></a>示例

WPF 应用程序所需的文件之一是 ( proj) 的项目文件。 应用程序中使用的所有资源都应包括在项目文件中。 下面的 XAML 示例演示了这一点。

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

若要在应用程序中使用资源，请实例化 <xref:System.Resources.ResourceManager> 并加载要使用的资源。 下面的 c # 代码演示如何执行此操作。

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a>另请参阅

- [对应用进行本地化](how-to-localize-an-application.md)
