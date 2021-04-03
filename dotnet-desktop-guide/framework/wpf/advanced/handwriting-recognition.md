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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970701"
---
# <a name="handwriting-recognition"></a><span data-ttu-id="109f0-102">手写识别</span><span class="sxs-lookup"><span data-stu-id="109f0-102">Handwriting Recognition</span></span>

<span data-ttu-id="109f0-103">本节介绍了识别基础知识，因为这与 WPF 平台中数字墨迹有关。</span><span class="sxs-lookup"><span data-stu-id="109f0-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="109f0-104">识别解决方案</span><span class="sxs-lookup"><span data-stu-id="109f0-104">Recognition Solutions</span></span>  

 <span data-ttu-id="109f0-105">以下示例演示如何使用 [Microsoft.Ink.InkCollector](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) 类识别墨迹。</span><span class="sxs-lookup"><span data-stu-id="109f0-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="109f0-106">此示例要求在系统上安装手写识别器。</span><span class="sxs-lookup"><span data-stu-id="109f0-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="109f0-107">在 Visual Studio 中创建一个名为 **InkRecognition** 的新 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="109f0-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="109f0-108">用下列 XAML 代码替换 Window1.xaml 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="109f0-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="109f0-109">此代码呈现应用程序的用户界面。</span><span class="sxs-lookup"><span data-stu-id="109f0-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="109f0-110">添加对 Microsoft 墨迹程序集和 Microsoft.Ink.dll 的引用，可在 \Program Files\Common Files\Microsoft Shared\Ink 中找到这些内容。</span><span class="sxs-lookup"><span data-stu-id="109f0-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="109f0-111">用下列代码替换代码隐藏文件的内容。</span><span class="sxs-lookup"><span data-stu-id="109f0-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="109f0-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="109f0-112">See also</span></span>

- <span data-ttu-id="109f0-113">[Microsoft.Ink.InkCollector](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="109f0-113">[Microsoft.Ink.InkCollector](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))</span></span>
