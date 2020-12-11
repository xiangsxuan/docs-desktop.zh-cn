---
title: 控件的属性
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: 3f9873ff032497a9cda6de199ed9db5ee9522d81
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970294"
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="a64de-102">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="a64de-102">Properties in Windows Forms Controls</span></span>

<span data-ttu-id="a64de-103">Windows 窗体控件从基类继承了许多属性 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="a64de-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a64de-104">其中包括、、、、、、、、、、、等属性 <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control.ForeColor%2A> <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.Bounds%2A> <xref:System.Windows.Forms.Control.ClientRectangle%2A> <xref:System.Windows.Forms.Control.DisplayRectangle%2A> <xref:System.Windows.Forms.Control.Enabled%2A> <xref:System.Windows.Forms.Control.Focused%2A> <xref:System.Windows.Forms.Control.Height%2A> <xref:System.Windows.Forms.Control.Width%2A> <xref:System.Windows.Forms.Control.Visible%2A> <xref:System.Windows.Forms.Control.AutoSize%2A> 。</span><span class="sxs-lookup"><span data-stu-id="a64de-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="a64de-105">有关继承的属性的详细信息，请参阅 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="a64de-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a64de-106">可以在控件中重写继承的属性和定义新属性。</span><span class="sxs-lookup"><span data-stu-id="a64de-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a64de-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="a64de-107">In This Section</span></span>  

 [<span data-ttu-id="a64de-108">定义属性</span><span class="sxs-lookup"><span data-stu-id="a64de-108">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="a64de-109">演示如何为自定义控件或组件实现属性，以及如何将该属性集成到设计环境中。</span><span class="sxs-lookup"><span data-stu-id="a64de-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="a64de-110">使用 ShouldSerialize 和 Reset 方法定义默认值</span><span class="sxs-lookup"><span data-stu-id="a64de-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="a64de-111">演示如何为自定义控件或组件定义默认属性值。</span><span class="sxs-lookup"><span data-stu-id="a64de-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="a64de-112">属性更改事件</span><span class="sxs-lookup"><span data-stu-id="a64de-112">Property-Changed Events</span></span>](property-changed-events.md)  
 <span data-ttu-id="a64de-113">介绍如何在属性值发生更改时启用属性更改通知。</span><span class="sxs-lookup"><span data-stu-id="a64de-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="a64de-114">如何：公开构成控件的属性</span><span class="sxs-lookup"><span data-stu-id="a64de-114">How to: Expose Properties of Constituent Controls</span></span>](how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="a64de-115">演示如何在自定义复合控件中公开构成控件的属性。</span><span class="sxs-lookup"><span data-stu-id="a64de-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="a64de-116">自定义控件中的方法实现</span><span class="sxs-lookup"><span data-stu-id="a64de-116">Method Implementation in Custom Controls</span></span>](method-implementation-in-custom-controls.md)  
 <span data-ttu-id="a64de-117">介绍如何在自定义控件和组件中实现方法。</span><span class="sxs-lookup"><span data-stu-id="a64de-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a64de-118">参考</span><span class="sxs-lookup"><span data-stu-id="a64de-118">Reference</span></span>  

 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="a64de-119">介绍用于实现复合控件的基类。</span><span class="sxs-lookup"><span data-stu-id="a64de-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="a64de-120">记录指定 <xref:System.ComponentModel.TypeConverter> 要用于自定义属性类型的的属性。</span><span class="sxs-lookup"><span data-stu-id="a64de-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="a64de-121">记录属性，该属性指定 <xref:System.Drawing.Design.UITypeEditor> 要用于自定义属性的。</span><span class="sxs-lookup"><span data-stu-id="a64de-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a64de-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="a64de-122">Related Sections</span></span>  

 [<span data-ttu-id="a64de-123">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="a64de-123">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="a64de-124">描述你可以应用到自定义控件和组件的属性或其他成员的特性。</span><span class="sxs-lookup"><span data-stu-id="a64de-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 <span data-ttu-id="a64de-125">[Design-Time Attributes for Components（组件的设计时属性）](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a64de-125">[Design-Time Attributes for Components](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="a64de-126">将列出的元数据特性应用到组件和控件，以便在设计时正确显示在可视化设计器中。</span><span class="sxs-lookup"><span data-stu-id="a64de-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="a64de-127">[扩展设计时支持](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a64de-127">[Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="a64de-128">描述如何实现提供设计时支持的类，例如编辑器和设计器。</span><span class="sxs-lookup"><span data-stu-id="a64de-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>
