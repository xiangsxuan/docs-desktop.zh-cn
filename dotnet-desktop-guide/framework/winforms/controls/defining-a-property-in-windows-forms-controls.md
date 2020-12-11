---
title: 定义控件属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
ms.openlocfilehash: ef81818123e78c50ade9f700a3acdbea1c5551b4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970106"
---
# <a name="defining-a-property-in-windows-forms-controls"></a><span data-ttu-id="3c938-102">在 Windows 窗体控件中定义属性</span><span class="sxs-lookup"><span data-stu-id="3c938-102">Defining a Property in Windows Forms Controls</span></span>

<span data-ttu-id="3c938-103">有关属性的概述，请参阅[属性概述](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="3c938-103">For an overview of properties, see [Properties Overview](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span></span> <span data-ttu-id="3c938-104">定义属性时需考虑以下重要注意事项：</span><span class="sxs-lookup"><span data-stu-id="3c938-104">There are a few important considerations when defining a property:</span></span>  
  
- <span data-ttu-id="3c938-105">必须将特性应用于定义的属性。</span><span class="sxs-lookup"><span data-stu-id="3c938-105">You must apply attributes to the properties you define.</span></span> <span data-ttu-id="3c938-106">特性指定设计器应如何显示属性。</span><span class="sxs-lookup"><span data-stu-id="3c938-106">Attributes specify how the designer should display a property.</span></span> <span data-ttu-id="3c938-107">有关详细信息，请参阅[组件的设计时特性](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="3c938-107">For details, see [Design-Time Attributes for Components](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>  
  
- <span data-ttu-id="3c938-108">如果更改属性会影响控件的可视显示，请调用方法， <xref:System.Windows.Forms.Control.Invalidate%2A> (控件继承自 <xref:System.Windows.Forms.Control> 访问器) 的方法 `set` 。</span><span class="sxs-lookup"><span data-stu-id="3c938-108">If changing the property affects the visual display of the control, call the <xref:System.Windows.Forms.Control.Invalidate%2A> method (that your control inherits from <xref:System.Windows.Forms.Control>) from the `set` accessor.</span></span> <span data-ttu-id="3c938-109"><xref:System.Windows.Forms.Control.Invalidate%2A> 进而调用 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，这会重绘控件。</span><span class="sxs-lookup"><span data-stu-id="3c938-109"><xref:System.Windows.Forms.Control.Invalidate%2A> in turn calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which redraws the control.</span></span> <span data-ttu-id="3c938-110">多次调用将 <xref:System.Windows.Forms.Control.Invalidate%2A> 导致一次调用以 <xref:System.Windows.Forms.Control.OnPaint%2A> 提高效率。</span><span class="sxs-lookup"><span data-stu-id="3c938-110">Multiple calls to <xref:System.Windows.Forms.Control.Invalidate%2A> result in a single call to <xref:System.Windows.Forms.Control.OnPaint%2A> for efficiency.</span></span>  
  
- <span data-ttu-id="3c938-111">.NET Framework 类库为常见数据类型（如整数、小数、布尔值和其他数据类型）提供了类型转换器。</span><span class="sxs-lookup"><span data-stu-id="3c938-111">The .NET Framework class library provides type converters for common data types such as integers, decimal numbers, Boolean values, and others.</span></span> <span data-ttu-id="3c938-112">类型转换器的用途通常是提供字符串到数值的转换（从字符串数据转换为其他数据类型）。</span><span class="sxs-lookup"><span data-stu-id="3c938-112">The purpose of a type converter is generally to provide string-to-value conversion (from string data to other data types).</span></span> <span data-ttu-id="3c938-113">常见数据类型与默认类型转换器相关联，默认类型转换器可将数值转换为字符串，并将字符串转换为相应数据类型。</span><span class="sxs-lookup"><span data-stu-id="3c938-113">Common data types are associated with default type converters that convert values into strings and strings into the appropriate data types.</span></span> <span data-ttu-id="3c938-114">如果定义了自定义（即非标准）数据类型的属性，则应用的特性必须将类型转换器指定为与该属性相关联。</span><span class="sxs-lookup"><span data-stu-id="3c938-114">If you define a property that is a custom (that is, nonstandard) data type, you will have to apply an attribute that specifies the type converter to associate with that property.</span></span> <span data-ttu-id="3c938-115">还可使用特性将自定义 UI 类型编辑器与某个属性相关联。</span><span class="sxs-lookup"><span data-stu-id="3c938-115">You can also use an attribute to associate a custom UI type editor with a property.</span></span> <span data-ttu-id="3c938-116">UI 类型编辑器提供一个用于编辑属性或数据类型的用户界面。</span><span class="sxs-lookup"><span data-stu-id="3c938-116">A UI type editor provides a user interface for editing a property or data type.</span></span> <span data-ttu-id="3c938-117">UI 类型编辑器的一个例子是颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="3c938-117">A color picker is an example of a UI type editor.</span></span> <span data-ttu-id="3c938-118">本主题末尾给出了特性的示例。</span><span class="sxs-lookup"><span data-stu-id="3c938-118">Examples of attributes are given at the end of this topic.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3c938-119">如果没有类型转换器或 UI 类型编辑器可供自定义属性使用，则可根据[扩展设计时支持](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))中所述来实现一个。</span><span class="sxs-lookup"><span data-stu-id="3c938-119">If a type converter or a UI type editor is not available for your custom property, you can implement one as described in [Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span></span>  
  
 <span data-ttu-id="3c938-120">以下代码片段为自定义控件 `FlashTrackBar` 定义了一个名为 `EndColor` 的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="3c938-120">The following code fragment defines a custom property named `EndColor` for the custom control `FlashTrackBar`.</span></span>  
  
```vb  
Public Class FlashTrackBar  
   Inherits Control  
   ...  
   ' Private data member that backs the EndColor property.  
   Private _endColor As Color = Color.LimeGreen  
  
   ' The Category attribute tells the designer to display  
   ' it in the Flash grouping.
   ' The Description attribute provides a description of  
   ' the property.
   <Category("Flash"), _  
   Description("The ending color of the bar.")>  _  
   Public Property EndColor() As Color  
      ' The public property EndColor accesses _endColor.  
      Get  
         Return _endColor  
      End Get  
      Set  
         _endColor = value  
         If Not (baseBackground Is Nothing) And showGradient Then  
            baseBackground.Dispose()  
            baseBackground = Nothing  
         End If  
         ' The Invalidate method calls the OnPaint method, which redraws
         ' the control.  
         Invalidate()  
      End Set  
   End Property  
   ...  
End Class  
```  
  
```csharp  
public class FlashTrackBar : Control {  
   ...  
   // Private data member that backs the EndColor property.  
   private Color endColor = Color.LimeGreen;  
   // The Category attribute tells the designer to display  
   // it in the Flash grouping.
   // The Description attribute provides a description of  
   // the property.
   [  
   Category("Flash"),  
   Description("The ending color of the bar.")  
   ]  
   // The public property EndColor accesses endColor.  
   public Color EndColor {  
      get {  
         return endColor;  
      }  
      set {  
         endColor = value;  
         if (baseBackground != null && showGradient) {  
            baseBackground.Dispose();  
            baseBackground = null;  
         }  
         // The Invalidate method calls the OnPaint method, which redraws
         // the control.  
         Invalidate();  
      }  
   }  
   ...  
}  
```  
  
 <span data-ttu-id="3c938-121">以下代码片段将类型转换器和 UI 类型编辑器与属性 `Value` 相关联。</span><span class="sxs-lookup"><span data-stu-id="3c938-121">The following code fragment associates a type converter and a UI type editor with the property `Value`.</span></span> <span data-ttu-id="3c938-122">在这种情况下，它 `Value` 是一个整数并且具有默认的类型转换器，但该 <xref:System.ComponentModel.TypeConverterAttribute> 属性将应用自定义类型转换器 (`FlashTrackBarValueConverter`) 使设计器能够将其显示为百分比。</span><span class="sxs-lookup"><span data-stu-id="3c938-122">In this case `Value` is an integer and has a default type converter, but the <xref:System.ComponentModel.TypeConverterAttribute> attribute applies a custom type converter (`FlashTrackBarValueConverter`) that enables the designer to display it as a percentage.</span></span> <span data-ttu-id="3c938-123">UI 类型编辑器 `FlashTrackBarValueEditor` 允许以可视化方式显示百分比。</span><span class="sxs-lookup"><span data-stu-id="3c938-123">The UI type editor, `FlashTrackBarValueEditor`, allows the percentage to be displayed visually.</span></span> <span data-ttu-id="3c938-124">此示例还显示了或特性指定的类型转换器或编辑器 <xref:System.ComponentModel.TypeConverterAttribute> 将 <xref:System.ComponentModel.EditorAttribute> 重写默认转换器。</span><span class="sxs-lookup"><span data-stu-id="3c938-124">This example also shows that the type converter or editor specified by the <xref:System.ComponentModel.TypeConverterAttribute> or <xref:System.ComponentModel.EditorAttribute> attribute overrides the default converter.</span></span>  
  
```vb  
<Category("Flash"), _  
TypeConverter(GetType(FlashTrackBarValueConverter)), _  
Editor(GetType(FlashTrackBarValueEditor), _  
GetType(UITypeEditor)), _  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")>  _  
Public ReadOnly Property Value() As Integer  
...  
End Property  
```  
  
```csharp  
[  
Category("Flash"),
TypeConverter(typeof(FlashTrackBarValueConverter)),  
Editor(typeof(FlashTrackBarValueEditor), typeof(UITypeEditor)),  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")  
]  
public int Value {  
...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c938-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c938-125">See also</span></span>

- [<span data-ttu-id="3c938-126">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="3c938-126">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="3c938-127">使用 ShouldSerialize 和 Reset 方法定义默认值</span><span class="sxs-lookup"><span data-stu-id="3c938-127">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)
- [<span data-ttu-id="3c938-128">属性更改事件</span><span class="sxs-lookup"><span data-stu-id="3c938-128">Property-Changed Events</span></span>](property-changed-events.md)
- [<span data-ttu-id="3c938-129">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="3c938-129">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
