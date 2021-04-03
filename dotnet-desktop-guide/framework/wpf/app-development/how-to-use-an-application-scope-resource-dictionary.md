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
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="5dbed-103">如何：使用应用程序范围的资源字典</span><span class="sxs-lookup"><span data-stu-id="5dbed-103">How to: Use an Application-Scope Resource Dictionary</span></span>

<span data-ttu-id="5dbed-104">本示例显示如何定义和使用应用程序范围的自定义资源字典。</span><span class="sxs-lookup"><span data-stu-id="5dbed-104">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dbed-105">示例</span><span class="sxs-lookup"><span data-stu-id="5dbed-105">Example</span></span>  

 <span data-ttu-id="5dbed-106"><xref:System.Windows.Application> 公开共享资源的应用程序范围存储区： <xref:System.Windows.Application.Resources%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbed-106"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="5dbed-107">默认情况下， <xref:System.Windows.Application.Resources%2A> 使用类型的实例来初始化属性 <xref:System.Windows.ResourceDictionary> 。</span><span class="sxs-lookup"><span data-stu-id="5dbed-107">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="5dbed-108">使用获取和设置应用程序范围的属性时，可以使用此实例 <xref:System.Windows.Application.Resources%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbed-108">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="5dbed-109">有关详细信息，请参阅 [如何：获取和设置 Application-Scope 资源](/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="5dbed-109">For more information, see [How to: Get and Set an Application-Scope Resource](/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="5dbed-110">如果你有使用设置的多个资源 <xref:System.Windows.Application.Resources%2A> ，则可以改为使用自定义资源字典来存储这些资源并使用它进行设置 <xref:System.Windows.Application.Resources%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbed-110">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="5dbed-111">下面演示了如何使用 XAML 声明自定义资源字典。</span><span class="sxs-lookup"><span data-stu-id="5dbed-111">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="5dbed-112">使用交换整个资源字典 <xref:System.Windows.Application.Resources%2A> 允许您支持应用程序范围的主题，其中每个主题都由单个资源字典封装。</span><span class="sxs-lookup"><span data-stu-id="5dbed-112">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="5dbed-113">下面的示例演示如何设置 <xref:System.Windows.ResourceDictionary>。</span><span class="sxs-lookup"><span data-stu-id="5dbed-113">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="5dbed-114">下面演示了如何通过 XAML 中公开的资源字典获取应用程序范围的资源 <xref:System.Windows.Application.Resources%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbed-114">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="5dbed-115">以下内容显示如何也能获取代码中的资源。</span><span class="sxs-lookup"><span data-stu-id="5dbed-115">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="5dbed-116">使用时有两个注意事项 <xref:System.Windows.Application.Resources%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbed-116">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="5dbed-117">首先，字典 *键* 是一个对象，因此在设置和获取属性值时，必须使用完全相同的对象实例。</span><span class="sxs-lookup"><span data-stu-id="5dbed-117">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="5dbed-118"> (请注意，使用字符串时，该键区分大小写。 ) 秒，字典 *值* 是一个对象，因此在获取属性值时，必须将该值转换为所需的类型。</span><span class="sxs-lookup"><span data-stu-id="5dbed-118">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  

<span data-ttu-id="5dbed-119">某些资源类型可能会自动使用类型定义的属性作为显式键，如 <xref:System.Windows.Style> 和 <xref:System.Windows.DataTemplate> 类型。</span><span class="sxs-lookup"><span data-stu-id="5dbed-119">Some resource types may automatically use a property defined by the type as an explicit key, such as the <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> types.</span></span> <span data-ttu-id="5dbed-120">这可能会覆盖你的 `x:Key` 值。</span><span class="sxs-lookup"><span data-stu-id="5dbed-120">This may override your `x:Key` value.</span></span> <span data-ttu-id="5dbed-121">若要确保遵循你的 `x:Key` 密钥，请在显式键属性之前声明。</span><span class="sxs-lookup"><span data-stu-id="5dbed-121">To guarantee that your `x:Key` key is respected, declare it before the explicit key property.</span></span> <span data-ttu-id="5dbed-122">有关详细信息，请参阅 [样式、DataTemplates 和隐式键](../advanced/xaml-resources-define.md#styles-datatemplates-and-implicit-keys)。</span><span class="sxs-lookup"><span data-stu-id="5dbed-122">For more information, see [Styles, DataTemplates, and implicit keys](../advanced/xaml-resources-define.md#styles-datatemplates-and-implicit-keys).</span></span>

## <a name="see-also"></a><span data-ttu-id="5dbed-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5dbed-123">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="5dbed-124">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="5dbed-124">XAML Resources</span></span>](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [<span data-ttu-id="5dbed-125">合并资源字典</span><span class="sxs-lookup"><span data-stu-id="5dbed-125">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
