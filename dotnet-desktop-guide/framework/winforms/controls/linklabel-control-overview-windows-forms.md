---
title: LinkLabel 控件概述
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 3e8607644c858ae804e384c974b5e81c1786c6a1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972625"
---
# <a name="linklabel-control-overview-windows-forms"></a><span data-ttu-id="0a3d4-102">LinkLabel 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="0a3d4-102">LinkLabel Control Overview (Windows Forms)</span></span>
<span data-ttu-id="0a3d4-103">Windows 窗体 <xref:System.Windows.Forms.LinkLabel> 控件允许您将 Web 样式链接添加到 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="0a3d4-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to add Web-style links to Windows Forms applications.</span></span> <span data-ttu-id="0a3d4-104">您可以使用控件来 <xref:System.Windows.Forms.LinkLabel> 实现可以使用控件的所有内容 <xref:System.Windows.Forms.Label> ; 还可以将部分文本设置为指向文件、文件夹或网页的链接。</span><span class="sxs-lookup"><span data-stu-id="0a3d4-104">You can use the <xref:System.Windows.Forms.LinkLabel> control for everything that you can use the <xref:System.Windows.Forms.Label> control for; you can also set part of the text as a link to a file, folder, or Web page.</span></span>  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a><span data-ttu-id="0a3d4-105">可以对 LinkLabel 控件执行的操作</span><span class="sxs-lookup"><span data-stu-id="0a3d4-105">What You Can Do with the LinkLabel Control</span></span>  
 <span data-ttu-id="0a3d4-106">除了控件的所有属性、方法和事件之外 <xref:System.Windows.Forms.Label> ， <xref:System.Windows.Forms.LinkLabel> 控件还具有超链接和链接颜色的属性。</span><span class="sxs-lookup"><span data-stu-id="0a3d4-106">In addition to all the properties, methods, and events of the <xref:System.Windows.Forms.Label> control, the <xref:System.Windows.Forms.LinkLabel> control has properties for hyperlinks and link colors.</span></span> <span data-ttu-id="0a3d4-107"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A>属性设置激活链接的文本区域。</span><span class="sxs-lookup"><span data-stu-id="0a3d4-107">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property sets the area of the text that activates the link.</span></span> <span data-ttu-id="0a3d4-108"><xref:System.Windows.Forms.LinkLabel.LinkColor%2A>、 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 和 <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> 属性设置链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="0a3d4-108">The <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> properties set the colors of the link.</span></span> <span data-ttu-id="0a3d4-109"><xref:System.Windows.Forms.LinkLabel.LinkClicked>事件确定在选择链接文本后将发生的情况。</span><span class="sxs-lookup"><span data-stu-id="0a3d4-109">The <xref:System.Windows.Forms.LinkLabel.LinkClicked> event determines what happens when the link text is selected.</span></span>  
  
 <span data-ttu-id="0a3d4-110">控件的最简单用法 <xref:System.Windows.Forms.LinkLabel> 是使用属性显示单个链接 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> ，但也可以使用属性显示多个超链接 <xref:System.Windows.Forms.LinkLabel.Links%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0a3d4-110">The simplest use of the <xref:System.Windows.Forms.LinkLabel> control is to display a single link using the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property, but you can also display multiple hyperlinks using the <xref:System.Windows.Forms.LinkLabel.Links%2A> property.</span></span> <span data-ttu-id="0a3d4-111"><xref:System.Windows.Forms.LinkLabel.Links%2A>属性使你能够访问链接的集合。</span><span class="sxs-lookup"><span data-stu-id="0a3d4-111">The <xref:System.Windows.Forms.LinkLabel.Links%2A> property enables you to access a collection of links.</span></span> <span data-ttu-id="0a3d4-112">您还可以在 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 每个对象的属性中指定数据 <xref:System.Windows.Forms.LinkLabel.Link> 。</span><span class="sxs-lookup"><span data-stu-id="0a3d4-112">You can also specify data in the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property of each individual <xref:System.Windows.Forms.LinkLabel.Link> object.</span></span> <span data-ttu-id="0a3d4-113">属性的值 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 可用于存储要显示的文件的位置或网站的地址。</span><span class="sxs-lookup"><span data-stu-id="0a3d4-113">The value of the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property can be used to store the location of a file to display or the address of a Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a3d4-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a3d4-114">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="0a3d4-115">Label 控件概述</span><span class="sxs-lookup"><span data-stu-id="0a3d4-115">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="0a3d4-116">如何：使用 Windows 窗体 LinkLabel 控件链接到对象或 Web 页面</span><span class="sxs-lookup"><span data-stu-id="0a3d4-116">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="0a3d4-117">如何：更改 Windows 窗体 LinkLabel 控件的外观</span><span class="sxs-lookup"><span data-stu-id="0a3d4-117">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
