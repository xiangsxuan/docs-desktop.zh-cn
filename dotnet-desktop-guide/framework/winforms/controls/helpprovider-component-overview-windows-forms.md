---
title: HelpProvider 组件概述
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 74d35dfa39a605cb1e1e85cc3aeda834e1c60669
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971519"
---
# <a name="helpprovider-component-overview-windows-forms"></a><span data-ttu-id="7b58f-102">HelpProvider 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="7b58f-102">HelpProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="7b58f-103">Windows 窗体 [HelpProvider](helpprovider-component-windows-forms.md) 组件用于将 html Help 1.x 帮助文件 (与 Html 帮助讨论会一起生成的 .chm 文件或与您的 Windows 应用程序) 的 .htm 文件相关联。</span><span class="sxs-lookup"><span data-stu-id="7b58f-103">The Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows application.</span></span> <span data-ttu-id="7b58f-104">可以通过多种方式提供帮助：</span><span class="sxs-lookup"><span data-stu-id="7b58f-104">You can provide help in a variety of ways:</span></span>  
  
- <span data-ttu-id="7b58f-105">为 Windows 窗体上的控件提供上下文相关帮助。</span><span class="sxs-lookup"><span data-stu-id="7b58f-105">Provide context-sensitive Help for controls on Windows Forms.</span></span>  
  
- <span data-ttu-id="7b58f-106">在特定对话框或对话框中的特定控件上提供区分上下文的帮助。</span><span class="sxs-lookup"><span data-stu-id="7b58f-106">Provide context-sensitive Help on a particular dialog box or specific controls on a dialog box.</span></span>  
  
- <span data-ttu-id="7b58f-107">在特定区域中打开帮助文件，例如目录表、索引或搜索函数的主页。</span><span class="sxs-lookup"><span data-stu-id="7b58f-107">Open a Help file to specific areas, such as the main page of a Table of Contents, the Index, or a search function.</span></span>  
  
## <a name="using-the-help-provider"></a><span data-ttu-id="7b58f-108">使用帮助提供程序</span><span class="sxs-lookup"><span data-stu-id="7b58f-108">Using the Help Provider</span></span>  
 <span data-ttu-id="7b58f-109">将 <xref:System.Windows.Forms.HelpProvider> 组件添加到 Windows 窗体后，窗体上的其他控件就可以公开组件的 "帮助" 属性 <xref:System.Windows.Forms.HelpProvider> 。</span><span class="sxs-lookup"><span data-stu-id="7b58f-109">Adding a <xref:System.Windows.Forms.HelpProvider> component to your Windows Form allows the other controls on the form to expose the Help properties of the <xref:System.Windows.Forms.HelpProvider> component.</span></span> <span data-ttu-id="7b58f-110">这使您能够为 Windows 窗体上的控件提供帮助。</span><span class="sxs-lookup"><span data-stu-id="7b58f-110">This enables you to provide help for the controls on your Windows Form.</span></span> <span data-ttu-id="7b58f-111">您可以使用属性将帮助文件与 <xref:System.Windows.Forms.HelpProvider> 组件相关联 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 。</span><span class="sxs-lookup"><span data-stu-id="7b58f-111">You can associate a Help file with the <xref:System.Windows.Forms.HelpProvider> component using the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property.</span></span> <span data-ttu-id="7b58f-112">您可以通过调用 <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> 并提供指定控件的枚举中的值来指定提供的帮助的类型 <xref:System.Windows.Forms.HelpNavigator> 。</span><span class="sxs-lookup"><span data-stu-id="7b58f-112">You specify the type of Help provided by calling <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> and providing a value from the <xref:System.Windows.Forms.HelpNavigator> enumeration for the specified control.</span></span> <span data-ttu-id="7b58f-113">可以通过调用方法为帮助提供关键字或主题 <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> 。</span><span class="sxs-lookup"><span data-stu-id="7b58f-113">You provide the keyword or topic for Help by calling the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> method.</span></span>  
  
 <span data-ttu-id="7b58f-114">（可选）若要将特定帮助字符串与另一个控件关联，请使用 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="7b58f-114">Optionally, to associate a specific Help string with another control, use the <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> method.</span></span> <span data-ttu-id="7b58f-115">当控件具有焦点时，如果用户按 F1 键，则使用此方法与控件相关联的字符串将显示在弹出窗口中。</span><span class="sxs-lookup"><span data-stu-id="7b58f-115">The string that you associate with a control using this method is displayed in a pop-up window when the user presses the F1 key while the control has focus.</span></span>  
  
 <span data-ttu-id="7b58f-116">如果尚未 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 设置，则必须使用 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 提供帮助文本。</span><span class="sxs-lookup"><span data-stu-id="7b58f-116">If <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> has not been set, you must use <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> to provide the Help text.</span></span> <span data-ttu-id="7b58f-117">如果同时设置了 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 和帮助字符串，则基于的帮助 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 将优先。</span><span class="sxs-lookup"><span data-stu-id="7b58f-117">If you have set both <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> and the Help string, Help based on <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> will take precedence.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b58f-118">在 <xref:System.Windows.Forms.Help.ShowHelp%2A> 控件的方法或属性中指定帮助文件的路径时，使用相对路径可能会遇到问题 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> <xref:System.Windows.Forms.HelpProvider> 。</span><span class="sxs-lookup"><span data-stu-id="7b58f-118">You may encounter problems using the relative path when specifying the path to the Help file in the <xref:System.Windows.Forms.Help.ShowHelp%2A> method or <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property of the <xref:System.Windows.Forms.HelpProvider> control.</span></span> <span data-ttu-id="7b58f-119">因此，请务必使用绝对文件路径来指定帮助文件。</span><span class="sxs-lookup"><span data-stu-id="7b58f-119">As such, be sure to use the absolute file path to specify the Help file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b58f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b58f-120">See also</span></span>

- [<span data-ttu-id="7b58f-121">Windows 窗体应用程序中的帮助系统</span><span class="sxs-lookup"><span data-stu-id="7b58f-121">Help Systems in Windows Forms Applications</span></span>](../advanced/help-systems-in-windows-forms-applications.md)
