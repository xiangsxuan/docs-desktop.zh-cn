---
title: 如何：使用应用程序资源
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: 09a30f90e0884022bb6247229caf4ca2f753d714
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665830"
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="7b1db-102">如何：使用应用程序资源</span><span class="sxs-lookup"><span data-stu-id="7b1db-102">How to: Use Application Resources</span></span>
<span data-ttu-id="7b1db-103">本示例演示如何使用应用程序资源。</span><span class="sxs-lookup"><span data-stu-id="7b1db-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b1db-104">示例</span><span class="sxs-lookup"><span data-stu-id="7b1db-104">Example</span></span>  
 <span data-ttu-id="7b1db-105">以下示例演示应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="7b1db-105">The following example shows an application definition file.</span></span> <span data-ttu-id="7b1db-106">应用程序定义文件为属性)  (值定义资源部分 <xref:System.Windows.Application.Resources%2A> 。</span><span class="sxs-lookup"><span data-stu-id="7b1db-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="7b1db-107">构成应用程序的所有其他页均可访问在应用程序级别定义的资源。</span><span class="sxs-lookup"><span data-stu-id="7b1db-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="7b1db-108">这种情况下，资源是声明样式。</span><span class="sxs-lookup"><span data-stu-id="7b1db-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="7b1db-109">由于包含控件模板的完整样式可能会很长，因此此示例将省略在样式的属性 setter 中定义的控件模板 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 。</span><span class="sxs-lookup"><span data-stu-id="7b1db-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="7b1db-110">下面的示例演示一个 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页面，该页面引用上一个示例定义的应用程序级资源。</span><span class="sxs-lookup"><span data-stu-id="7b1db-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="7b1db-111">使用指定所请求资源的唯一资源键的     [StaticResource 标记扩展](staticresource-markup-extension.md) 来引用资源。</span><span class="sxs-lookup"><span data-stu-id="7b1db-111">The resource is referenced by using a     [StaticResource Markup Extension](staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="7b1db-112">在当前页中没有找到具有“GelButton”键的资源，所以请求资源的资源查找范围超出当前页，进入已定义的应用程序级资源。</span><span class="sxs-lookup"><span data-stu-id="7b1db-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="7b1db-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b1db-113">See also</span></span>

- [<span data-ttu-id="7b1db-114">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="7b1db-114">XAML Resources</span></span>](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [<span data-ttu-id="7b1db-115">应用程序管理概述</span><span class="sxs-lookup"><span data-stu-id="7b1db-115">Application Management Overview</span></span>](../app-development/application-management-overview.md)
- [<span data-ttu-id="7b1db-116">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="7b1db-116">How-to Topics</span></span>](resources-how-to-topics.md)
