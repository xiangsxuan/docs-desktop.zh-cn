---
title: 如何：使用可本地化的应用程序中的资源
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970963"
---
# <a name="how-to-use-resources-in-localizable-apps"></a><span data-ttu-id="0269b-102">如何：在可本地化的应用中使用资源</span><span class="sxs-lookup"><span data-stu-id="0269b-102">How to: Use resources in localizable apps</span></span>

<span data-ttu-id="0269b-103">本地化是指使用户界面适应不同的文化。</span><span class="sxs-lookup"><span data-stu-id="0269b-103">Localization means to adapt a user interface to different cultures.</span></span> <span data-ttu-id="0269b-104">为此，必须翻译标题、标题和列表框项等文本。</span><span class="sxs-lookup"><span data-stu-id="0269b-104">To do this, text such as titles, captions, and list box items must be translated.</span></span> <span data-ttu-id="0269b-105">为了更轻松地进行翻译，要翻译的项将收集到资源文件中。</span><span class="sxs-lookup"><span data-stu-id="0269b-105">To make translation easier, the items to be translated are collected into resource files.</span></span> <span data-ttu-id="0269b-106">有关如何创建用于本地化的资源文件的信息，请参阅 [本地化应用程序](how-to-localize-an-application.md) 。</span><span class="sxs-lookup"><span data-stu-id="0269b-106">See [Localize an app](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="0269b-107">若要使 WPF 应用程序可本地化，开发人员需要将所有可本地化的资源生成到一个资源程序集中。</span><span class="sxs-lookup"><span data-stu-id="0269b-107">To make a WPF application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="0269b-108">资源程序集本地化为不同的语言，代码隐藏使用资源管理 API 进行加载。</span><span class="sxs-lookup"><span data-stu-id="0269b-108">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span>

## <a name="example"></a><span data-ttu-id="0269b-109">示例</span><span class="sxs-lookup"><span data-stu-id="0269b-109">Example</span></span>

<span data-ttu-id="0269b-110">WPF 应用程序所需的文件之一是 ( proj) 的项目文件。</span><span class="sxs-lookup"><span data-stu-id="0269b-110">One of the files required for a WPF application is a project file (.proj).</span></span> <span data-ttu-id="0269b-111">应用程序中使用的所有资源都应包括在项目文件中。</span><span class="sxs-lookup"><span data-stu-id="0269b-111">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="0269b-112">下面的 XAML 示例演示了这一点。</span><span class="sxs-lookup"><span data-stu-id="0269b-112">The following XAML example shows this.</span></span>

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

<span data-ttu-id="0269b-113">若要在应用程序中使用资源，请实例化 <xref:System.Resources.ResourceManager> 并加载要使用的资源。</span><span class="sxs-lookup"><span data-stu-id="0269b-113">To use a resource in your application, instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="0269b-114">下面的 c # 代码演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0269b-114">The following C# code demonstrates how to do this.</span></span>

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a><span data-ttu-id="0269b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0269b-115">See also</span></span>

- [<span data-ttu-id="0269b-116">对应用进行本地化</span><span class="sxs-lookup"><span data-stu-id="0269b-116">Localize an app</span></span>](how-to-localize-an-application.md)
