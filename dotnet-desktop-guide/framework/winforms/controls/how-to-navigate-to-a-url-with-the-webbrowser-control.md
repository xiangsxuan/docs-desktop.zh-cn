---
title: 如何：使用 WebBrowser 控件导航到 URL
description: 了解如何使用 Windows 窗体 WebBrowser. 导航控件导航到特定的 URL。 还了解如何确定何时加载新文档。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
ms.openlocfilehash: e6ad360cc73a84ca040869832bb59d354cb78bd5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972571"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="f8426-104">如何：使用 WebBrowser 控件导航到 URL</span><span class="sxs-lookup"><span data-stu-id="f8426-104">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="f8426-105">下面的代码示例演示如何将控件导航 <xref:System.Windows.Forms.WebBrowser> 到特定的 URL。</span><span class="sxs-lookup"><span data-stu-id="f8426-105">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="f8426-106">若要确定新文档完全加载的时间，请处理 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 事件。</span><span class="sxs-lookup"><span data-stu-id="f8426-106">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="f8426-107">有关此事件的演示，请参阅 [如何：使用 WebBrowser 控件进行打印](how-to-print-with-a-webbrowser-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f8426-107">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="f8426-108">示例</span><span class="sxs-lookup"><span data-stu-id="f8426-108">Example</span></span>

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="f8426-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="f8426-109">Compiling the Code</span></span>
 <span data-ttu-id="f8426-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f8426-110">This example requires:</span></span>

- <span data-ttu-id="f8426-111">名为 `webBrowser1` 的 <xref:System.Windows.Forms.WebBrowser> 控件。</span><span class="sxs-lookup"><span data-stu-id="f8426-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="f8426-112">对 `System` 和 `System.Windows.Forms` 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f8426-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8426-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8426-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="f8426-114">WebBrowser 控件</span><span class="sxs-lookup"><span data-stu-id="f8426-114">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="f8426-115">如何：使用 WebBrowser 控件打印</span><span class="sxs-lookup"><span data-stu-id="f8426-115">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
