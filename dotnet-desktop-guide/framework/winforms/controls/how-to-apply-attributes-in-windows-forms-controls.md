---
title: 在控件中应用特性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: f12b430d787b4b974e12902b2c17d3a35a09e468
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971262"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="d1fa4-102">如何：应用 Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="d1fa4-102">How to: Apply Attributes in Windows Forms Controls</span></span>

<span data-ttu-id="d1fa4-103">若要开发正确与设计环境进行交互并在运行时正确执行的组件和控件，需要正确地将特性应用于类和成员。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1fa4-104">示例</span><span class="sxs-lookup"><span data-stu-id="d1fa4-104">Example</span></span>  

 <span data-ttu-id="d1fa4-105">下面的代码示例演示如何在自定义控件上使用多个特性。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="d1fa4-106">控件说明了简单的日志记录功能。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="d1fa4-107">当控件绑定到数据源时，它将在控件中显示数据源发送的值 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d1fa4-108">如果某个值超出了由属性指定的值 `Threshold` ， `ThresholdExceeded` 则会引发事件。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="d1fa4-109">`AttributesDemoControl`使用类记录值 `LogEntry` 。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="d1fa4-110">`LogEntry`类是一个模板类，这意味着它将在它所记录的类型中进行参数化。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="d1fa4-111">例如，如果 `AttributesDemoControl` 是日志记录值类型 `float` ， `LogEntry` 则按如下方式声明并使用每个实例。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="d1fa4-112">由于 `LogEntry` 是由任意类型参数化的，因此它必须使用反射来对参数类型进行操作。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="d1fa4-113">要使阈值功能正常工作，参数类型 `T` 必须实现 <xref:System.IComparable> 接口。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="d1fa4-114">托管查询性能计数器的窗体会 `AttributesDemoControl` 定期执行。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="d1fa4-115">每个值都打包为 `LogEntry` 适当类型的，并添加到窗体的中 <xref:System.Windows.Forms.BindingSource> 。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="d1fa4-116">`AttributesDemoControl`通过数据绑定接收值并在控件中显示值 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="d1fa4-117">第一个代码示例是 `AttributesDemoControl` 实现。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="d1fa4-118">第二个代码示例演示使用的窗体 `AttributesDemoControl` 。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="d1fa4-119">类级属性</span><span class="sxs-lookup"><span data-stu-id="d1fa4-119">Class-level Attributes</span></span>  

 <span data-ttu-id="d1fa4-120">某些属性应用于类级别。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="d1fa4-121">下面的代码示例演示通常应用于 Windows 窗体控件的特性。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="d1fa4-122">TypeConverter 特性</span><span class="sxs-lookup"><span data-stu-id="d1fa4-122">TypeConverter Attribute</span></span>  

 <span data-ttu-id="d1fa4-123"><xref:System.ComponentModel.TypeConverterAttribute> 是另一种常用的类级属性。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="d1fa4-124">下面的代码示例演示如何使用 `LogEntry` 类。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="d1fa4-125">此示例还演示类型的的实现 <xref:System.ComponentModel.TypeConverter> ，该 `LogEntry` 类型名为 `LogEntryTypeConverter` 。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="d1fa4-126">成员级特性</span><span class="sxs-lookup"><span data-stu-id="d1fa4-126">Member-level Attributes</span></span>  

 <span data-ttu-id="d1fa4-127">某些属性应用于成员级别。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="d1fa4-128">下面的代码示例演示一些通常应用于 Windows 窗体控件的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="d1fa4-129">AmbientValue 特性</span><span class="sxs-lookup"><span data-stu-id="d1fa4-129">AmbientValue Attribute</span></span>  

 <span data-ttu-id="d1fa4-130">下面的示例演示 <xref:System.ComponentModel.AmbientValueAttribute> 并显示支持与设计环境交互的代码。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="d1fa4-131">这种交互称为 " *环境*"。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="d1fa4-132">数据绑定属性</span><span class="sxs-lookup"><span data-stu-id="d1fa4-132">Databinding Attributes</span></span>  

 <span data-ttu-id="d1fa4-133">下面的示例演示如何实现复杂数据绑定。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="d1fa4-134"><xref:System.ComponentModel.ComplexBindingPropertiesAttribute>前面所示的类级别指定了用于 `DataSource` 数据绑定的和 `DataMember` 属性。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="d1fa4-135"><xref:System.ComponentModel.AttributeProviderAttribute>指定属性将绑定到的类型 `DataSource` 。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d1fa4-136">编译代码</span><span class="sxs-lookup"><span data-stu-id="d1fa4-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="d1fa4-137">承载的窗体 `AttributesDemoControl` 需要引用 `AttributesDemoControl` 程序集才能生成。</span><span class="sxs-lookup"><span data-stu-id="d1fa4-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1fa4-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1fa4-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="d1fa4-139">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d1fa4-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="d1fa4-140">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="d1fa4-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="d1fa4-141">[如何：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d1fa4-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
