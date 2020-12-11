---
title: TableLayoutPanel 控件的最佳做法
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: e46d0fe6913bec61bd56199b7cb56a9b24d15bd0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971323"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="d8118-102">TableLayoutPanel 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="d8118-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="d8118-103"><xref:System.Windows.Forms.TableLayoutPanel>控件提供了强大的布局功能，您应该在 Windows 窗体上使用之前仔细考虑。</span><span class="sxs-lookup"><span data-stu-id="d8118-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>

## <a name="recommendations"></a><span data-ttu-id="d8118-104">建议</span><span class="sxs-lookup"><span data-stu-id="d8118-104">Recommendations</span></span>
 <span data-ttu-id="d8118-105">以下建议将帮助你将控件用于 <xref:System.Windows.Forms.TableLayoutPanel> 其最佳优势。</span><span class="sxs-lookup"><span data-stu-id="d8118-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>

### <a name="targeted-use"></a><span data-ttu-id="d8118-106">目标使用</span><span class="sxs-lookup"><span data-stu-id="d8118-106">Targeted Use</span></span>
 <span data-ttu-id="d8118-107">谨慎使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="d8118-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="d8118-108">在需要可调整大小的布局的所有情况下，不应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="d8118-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="d8118-109">下面的列表介绍了使用控件的最大优势 <xref:System.Windows.Forms.TableLayoutPanel> ：</span><span class="sxs-lookup"><span data-stu-id="d8118-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>

- <span data-ttu-id="d8118-110">布局，其中，窗体的多个部分都按比例调整大小。</span><span class="sxs-lookup"><span data-stu-id="d8118-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>

- <span data-ttu-id="d8118-111">将在运行时动态修改或生成的布局，例如基于首选项添加或缩减用户可自定义字段的数据输入窗体。</span><span class="sxs-lookup"><span data-stu-id="d8118-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>

- <span data-ttu-id="d8118-112">应保持整体固定大小的布局。</span><span class="sxs-lookup"><span data-stu-id="d8118-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="d8118-113">例如，你可能会有一个对话框，该对话框应保持小于 800 x 600，但你需要支持本地化的字符串。</span><span class="sxs-lookup"><span data-stu-id="d8118-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>

 <span data-ttu-id="d8118-114">下面的列表介绍了使用控件无法显著提高的布局 <xref:System.Windows.Forms.TableLayoutPanel> ：</span><span class="sxs-lookup"><span data-stu-id="d8118-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>

- <span data-ttu-id="d8118-115">简单的数据输入窗体，其中包含一列标签和单列文本输入区域。</span><span class="sxs-lookup"><span data-stu-id="d8118-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>

- <span data-ttu-id="d8118-116">具有单个大型显示区域的窗体，当发生调整大小时，应填充所有可用空间。</span><span class="sxs-lookup"><span data-stu-id="d8118-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="d8118-117">这种情况的一个示例是显示单个控件的窗体 <xref:System.Windows.Forms.PropertyGrid> 。</span><span class="sxs-lookup"><span data-stu-id="d8118-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="d8118-118">在这种情况下，请使用锚定，因为在调整窗体大小时，其他任何内容都不应扩展。</span><span class="sxs-lookup"><span data-stu-id="d8118-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>

 <span data-ttu-id="d8118-119">仔细选择哪些控件需要在 <xref:System.Windows.Forms.TableLayoutPanel> 控件中。</span><span class="sxs-lookup"><span data-stu-id="d8118-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="d8118-120">如果你有足够的空间使文本使用锚定增长30%，请考虑 <xref:System.Windows.Forms.Control.Anchor%2A> 只使用属性。</span><span class="sxs-lookup"><span data-stu-id="d8118-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="d8118-121">如果可以估计布局所需的空间，则和的使用 <xref:System.Windows.Forms.Control.Dock%2A> <xref:System.Windows.Forms.Control.Anchor%2A> 比估计剩余空间和行为的详细信息更容易 <xref:System.Windows.Forms.Control.AutoSize%2A> 。</span><span class="sxs-lookup"><span data-stu-id="d8118-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>

 <span data-ttu-id="d8118-122">通常，在通过控件设计布局时 <xref:System.Windows.Forms.TableLayoutPanel> ，请尽可能简化设计。</span><span class="sxs-lookup"><span data-stu-id="d8118-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>

### <a name="use-the-document-outline-window"></a><span data-ttu-id="d8118-123">使用 "文档大纲" 窗口</span><span class="sxs-lookup"><span data-stu-id="d8118-123">Use the Document Outline Window</span></span>
 <span data-ttu-id="d8118-124">"文档大纲" 窗口提供布局的树状视图，您可以使用这些视图来操作控件的 z 顺序和父子关系。</span><span class="sxs-lookup"><span data-stu-id="d8118-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="d8118-125">从 " **视图" 菜单** 中选择 " **其他窗口**"，然后选择 " **文档大纲**"。</span><span class="sxs-lookup"><span data-stu-id="d8118-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>

### <a name="avoid-nesting"></a><span data-ttu-id="d8118-126">避免嵌套</span><span class="sxs-lookup"><span data-stu-id="d8118-126">Avoid Nesting</span></span>
 <span data-ttu-id="d8118-127">避免 <xref:System.Windows.Forms.TableLayoutPanel> 在控件内嵌套其他控件 <xref:System.Windows.Forms.TableLayoutPanel> 。</span><span class="sxs-lookup"><span data-stu-id="d8118-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="d8118-128">调试嵌套布局可能比较困难。</span><span class="sxs-lookup"><span data-stu-id="d8118-128">Debugging nested layouts can be difficult.</span></span>

### <a name="avoid-visual-inheritance"></a><span data-ttu-id="d8118-129">避免视觉对象继承</span><span class="sxs-lookup"><span data-stu-id="d8118-129">Avoid Visual Inheritance</span></span>
 <span data-ttu-id="d8118-130"><xref:System.Windows.Forms.TableLayoutPanel>控件不支持 Visual Studio 的 Windows 窗体设计器中的可视化继承。</span><span class="sxs-lookup"><span data-stu-id="d8118-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="d8118-131"><xref:System.Windows.Forms.TableLayoutPanel>派生类中的控件在设计时显示为 "已锁定"。</span><span class="sxs-lookup"><span data-stu-id="d8118-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8118-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8118-132">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
