---
title: 控件中的特性
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
ms.openlocfilehash: 8f60b30021e6418f2ebf53965b62043e46e202b4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970734"
---
# <a name="attributes-in-windows-forms-controls"></a><span data-ttu-id="4f5a7-102">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="4f5a7-102">Attributes in Windows Forms Controls</span></span>

<span data-ttu-id="4f5a7-103">.NET Framework 提供了多种可应用于自定义控件和组件的成员的特性。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-103">The .NET Framework provides a variety of attributes you can apply to the members of your custom controls and components.</span></span> <span data-ttu-id="4f5a7-104">其中的一些特性会影响类的运行时行为，另一些会影响设计时行为。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-104">Some of these attributes affect the run-time behavior of a class, and others affect the design-time behavior.</span></span>  
  
## <a name="attributes-for-control-and-component-properties"></a><span data-ttu-id="4f5a7-105">控件和组件属性的特性</span><span class="sxs-lookup"><span data-stu-id="4f5a7-105">Attributes for Control and Component Properties</span></span>  

 <span data-ttu-id="4f5a7-106">下表显示了可应用于自定义控件和组件的属性或其他成员的特性。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-106">The following table shows the attributes you can apply to properties or other members of your custom controls and components.</span></span> <span data-ttu-id="4f5a7-107">请参阅[如何：在 Windows 窗体控件中应用特性](how-to-apply-attributes-in-windows-forms-controls.md)，获取一个使用了其中许多特性的示例。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-107">For an example that uses many of these attributes, see [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
|<span data-ttu-id="4f5a7-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="4f5a7-108">Attribute</span></span>|<span data-ttu-id="4f5a7-109">描述</span><span class="sxs-lookup"><span data-stu-id="4f5a7-109">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|<span data-ttu-id="4f5a7-110">指定要传递给属性的值，以使该属性从另一个源中获取其值。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-110">Specifies the value to pass to a property to cause the property to get its value from another source.</span></span> <span data-ttu-id="4f5a7-111">这称为“环境”。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-111">This is known as *ambience*.</span></span>|  
|<xref:System.ComponentModel.BrowsableAttribute>|<span data-ttu-id="4f5a7-112">指定是否应在 " **属性** " 窗口中显示属性或事件。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-112">Specifies whether a property or event should be displayed in a **Properties** window.</span></span>|  
|<xref:System.ComponentModel.CategoryAttribute>|<span data-ttu-id="4f5a7-113">指定类别的名称，在此类别中，将在设置为 mode 的控件中显示属性或事件 <xref:System.Windows.Forms.PropertyGrid> <xref:System.Windows.Forms.PropertySort.Categorized> 。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-113">Specifies the name of the category in which to group the property or event when displayed in a <xref:System.Windows.Forms.PropertyGrid> control set to <xref:System.Windows.Forms.PropertySort.Categorized> mode.</span></span>|  
|<xref:System.ComponentModel.DefaultValueAttribute>|<span data-ttu-id="4f5a7-114">指定属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-114">Specifies the default value for a property.</span></span>|  
|<xref:System.ComponentModel.DescriptionAttribute>|<span data-ttu-id="4f5a7-115">指定属性或事件的说明。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-115">Specifies a description for a property or event.</span></span>|  
|<xref:System.ComponentModel.DisplayNameAttribute>|<span data-ttu-id="4f5a7-116">为属性、事件或不采用参数的 `public void` 方法指定显示名称。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-116">Specifies the display name for a property, event, or `public void` method that takes no arguments.</span></span>|  
|<xref:System.ComponentModel.EditorAttribute>|<span data-ttu-id="4f5a7-117">指定用于更改属性的编辑器。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-117">Specifies the editor to use to change a property.</span></span>|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|<span data-ttu-id="4f5a7-118">指定可在编辑器中查看的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-118">Specifies that a property or method is viewable in an editor.</span></span>|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|<span data-ttu-id="4f5a7-119">为类或成员指定上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-119">Specifies the context keyword for a class or member.</span></span>|  
|<xref:System.ComponentModel.LocalizableAttribute>|<span data-ttu-id="4f5a7-120">指定是否应本地化某一属性。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-120">Specifies whether a property should be localized.</span></span>|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|<span data-ttu-id="4f5a7-121">指示对象的文本表示形式被星号等字符隐匿。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-121">Indicates that an object's text representation is obscured by characters such as asterisks.</span></span>|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|<span data-ttu-id="4f5a7-122">指定此特性绑定到的属性在设计时是只读还是可读/写。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-122">Specifies whether the property this attribute is bound to is read-only or read/write at design time.</span></span>|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|<span data-ttu-id="4f5a7-123">指示关联的属性值更改时应刷新属性网格。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-123">Indicates that the property grid should refresh when the associated property value changes.</span></span>|  
|<xref:System.ComponentModel.TypeConverterAttribute>|<span data-ttu-id="4f5a7-124">指定对于此属性绑定到的对象要使用哪种类型作为转换器。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-124">Specifies what type to use as a converter for the object this attribute is bound to.</span></span>|  
  
## <a name="attributes-for-data-binding-properties"></a><span data-ttu-id="4f5a7-125">数据绑定属性的特性</span><span class="sxs-lookup"><span data-stu-id="4f5a7-125">Attributes for Data Binding Properties</span></span>  

 <span data-ttu-id="4f5a7-126">下表显示了可用于指定自定义控件和组件如何与数据绑定之间进行交互的特性。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-126">The following table shows the attributes you can apply to specify how your custom controls and components interact with data binding.</span></span>  
  
|<span data-ttu-id="4f5a7-127">Attribute</span><span class="sxs-lookup"><span data-stu-id="4f5a7-127">Attribute</span></span>|<span data-ttu-id="4f5a7-128">描述</span><span class="sxs-lookup"><span data-stu-id="4f5a7-128">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|<span data-ttu-id="4f5a7-129">指定属性是否通常用于绑定。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-129">Specifies whether a property is typically used for binding.</span></span>|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|<span data-ttu-id="4f5a7-130">指定组件的数据源和数据成员属性。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-130">Specifies the data source and data member properties for a component.</span></span>|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|<span data-ttu-id="4f5a7-131">指定组件的默认绑定属性。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-131">Specifies the default binding property for a component.</span></span>|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|<span data-ttu-id="4f5a7-132">指定组件的数据源和数据成员属性。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-132">Specifies the data source and data member properties for a component.</span></span>|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|<span data-ttu-id="4f5a7-133">启用特性重定向。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-133">Enables attribute redirection.</span></span>|  
  
## <a name="attributes-for-classes"></a><span data-ttu-id="4f5a7-134">类的特性</span><span class="sxs-lookup"><span data-stu-id="4f5a7-134">Attributes for Classes</span></span>  

 <span data-ttu-id="4f5a7-135">下表显示了可用于在设计时指定自定义控件和组件的行为的特性。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-135">The following table shows the attributes you can apply to specify the behavior of your custom controls and components at design time.</span></span>  
  
|<span data-ttu-id="4f5a7-136">Attribute</span><span class="sxs-lookup"><span data-stu-id="4f5a7-136">Attribute</span></span>|<span data-ttu-id="4f5a7-137">描述</span><span class="sxs-lookup"><span data-stu-id="4f5a7-137">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|<span data-ttu-id="4f5a7-138">指定组件的默认事件。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-138">Specifies the default event for a component.</span></span>|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|<span data-ttu-id="4f5a7-139">指定组件的默认属性。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-139">Specifies the default property for a component.</span></span>|  
|<xref:System.ComponentModel.DesignerAttribute>|<span data-ttu-id="4f5a7-140">指定用于为组件实现设计时服务的类。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-140">Specifies the class used to implement design-time services for a component.</span></span>|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|<span data-ttu-id="4f5a7-141">指定类设计器属于某一类别。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-141">Specifies that the designer for a class belongs to a certain category.</span></span>|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|<span data-ttu-id="4f5a7-142">表示工具箱项的特性。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-142">Represents an attribute of a toolbox item.</span></span>|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|<span data-ttu-id="4f5a7-143">指定要用于工具箱项的筛选器字符串和筛选器类型。</span><span class="sxs-lookup"><span data-stu-id="4f5a7-143">Specifies the filter string and filter type to use for a Toolbox item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f5a7-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f5a7-144">See also</span></span>

- <xref:System.Attribute>
- [<span data-ttu-id="4f5a7-145">如何：应用 Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="4f5a7-145">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- <span data-ttu-id="4f5a7-146">[扩展设计时支持](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="4f5a7-146">[Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- [<span data-ttu-id="4f5a7-147">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="4f5a7-147">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
