---
title: 手写识别
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
ms.openlocfilehash: 4c0a5a50695ee3742f0524142e49aa32f70e166d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970701"
---
# <a name="handwriting-recognition"></a>手写识别

本节介绍了识别基础知识，因为这与 WPF 平台中数字墨迹有关。  
  
## <a name="recognition-solutions"></a>识别解决方案  

 以下示例演示如何使用 [Microsoft.Ink.InkCollector](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) 类识别墨迹。  
  
> [!NOTE]
> 此示例要求在系统上安装手写识别器。  
  
 在 Visual Studio 中创建一个名为 **InkRecognition** 的新 WPF 应用程序项目。 用下列 XAML 代码替换 Window1.xaml 文件的内容。 此代码呈现应用程序的用户界面。  
  
 [!code-xaml[InkRecognition#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 添加对 Microsoft 墨迹程序集和 Microsoft.Ink.dll 的引用，可在 \Program Files\Common Files\Microsoft Shared\Ink 中找到这些内容。 用下列代码替换代码隐藏文件的内容。  
  
 [!code-csharp[InkRecognition#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>另请参阅

- [Microsoft.Ink.InkCollector](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))
