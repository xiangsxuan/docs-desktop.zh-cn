---
title: 如何：使用应用程序范围的资源字典
description: 了解如何在 Windows Presentation Foundation (WPF) 中定义和使用应用程序范围的自定义资源字典。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 0d9c4f851c5ee03bf60dbdadc31d9fc4c6536746
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "98535983"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>如何：使用应用程序范围的资源字典

本示例显示如何定义和使用应用程序范围的自定义资源字典。  
  
## <a name="example"></a>示例  

 <xref:System.Windows.Application> 公开共享资源的应用程序范围存储区： <xref:System.Windows.Application.Resources%2A> 。 默认情况下， <xref:System.Windows.Application.Resources%2A> 使用类型的实例来初始化属性 <xref:System.Windows.ResourceDictionary> 。 使用获取和设置应用程序范围的属性时，可以使用此实例 <xref:System.Windows.Application.Resources%2A> 。 有关详细信息，请参阅 [如何：获取和设置 Application-Scope 资源](/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))。
  
 如果你有使用设置的多个资源 <xref:System.Windows.Application.Resources%2A> ，则可以改为使用自定义资源字典来存储这些资源并使用它进行设置 <xref:System.Windows.Application.Resources%2A> 。 下面演示了如何使用 XAML 声明自定义资源字典。
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 使用交换整个资源字典 <xref:System.Windows.Application.Resources%2A> 允许您支持应用程序范围的主题，其中每个主题都由单个资源字典封装。 下面的示例演示如何设置 <xref:System.Windows.ResourceDictionary>。  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 下面演示了如何通过 XAML 中公开的资源字典获取应用程序范围的资源 <xref:System.Windows.Application.Resources%2A> 。  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 以下内容显示如何也能获取代码中的资源。  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 使用时有两个注意事项 <xref:System.Windows.Application.Resources%2A> 。 首先，字典 *键* 是一个对象，因此在设置和获取属性值时，必须使用完全相同的对象实例。  (请注意，使用字符串时，该键区分大小写。 ) 秒，字典 *值* 是一个对象，因此在获取属性值时，必须将该值转换为所需的类型。  

某些资源类型可能会自动使用类型定义的属性作为显式键，如 <xref:System.Windows.Style> 和 <xref:System.Windows.DataTemplate> 类型。 这可能会覆盖你的 `x:Key` 值。 若要确保遵循你的 `x:Key` 密钥，请在显式键属性之前声明。 有关详细信息，请参阅 [样式、DataTemplates 和隐式键](../advanced/xaml-resources-define.md#styles-datatemplates-and-implicit-keys)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [合并资源字典](../advanced/merged-resource-dictionaries.md)
