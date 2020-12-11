---
title: 为 Windows 窗体上的控件提供辅助功能信息
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 672104db94826cfbe113a7ae0ea29546b0c3b9da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970293"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="2ccbb-102">为 Windows 窗体上的控件提供辅助功能信息</span><span class="sxs-lookup"><span data-stu-id="2ccbb-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="2ccbb-103">辅助工具是专用的程序和设备，用于帮助残障人士更加有效地使用计算机。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="2ccbb-104">示例包括适用于盲人的屏幕阅读器，还有声音输入实用功能，方便人们发出声音命令，而不使用鼠标或键盘。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="2ccbb-105">这些辅助工具与由 Windows 窗体控件公开的辅助功能属性相交互。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="2ccbb-106">这些属性为：</span><span class="sxs-lookup"><span data-stu-id="2ccbb-106">These properties are:</span></span>  
  
- <span data-ttu-id="2ccbb-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="2ccbb-107">**AccessibilityObject**</span></span>  
  
- <span data-ttu-id="2ccbb-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="2ccbb-108">**AccessibleDefaultActionDescription**</span></span>  
  
- <span data-ttu-id="2ccbb-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="2ccbb-109">**AccessibleDescription**</span></span>  
  
- <span data-ttu-id="2ccbb-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="2ccbb-110">**AccessibleName**</span></span>  
  
- <span data-ttu-id="2ccbb-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="2ccbb-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="2ccbb-112">AccessibilityObject 属性</span><span class="sxs-lookup"><span data-stu-id="2ccbb-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="2ccbb-113">此只读属性包含 <xref:System.Windows.Forms.AccessibleObject> 实例。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="2ccbb-114">**AccessibleObject** 实现了 <xref:Accessibility.IAccessible> 接口，它提供了有关控件的说明、屏幕位置、导航功能和值的信息。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="2ccbb-115">在将控件添加到窗体时，设计器会设置此值。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="2ccbb-116">AccessibleDefaultActionDescription 属性</span><span class="sxs-lookup"><span data-stu-id="2ccbb-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="2ccbb-117">该字符串描述控件的操作。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-117">This string describes the action of the control.</span></span> <span data-ttu-id="2ccbb-118">它不显示在“属性”窗口中，可能只在代码中被设置。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="2ccbb-119">下面的示例为按钮控件设置此属性：</span><span class="sxs-lookup"><span data-stu-id="2ccbb-119">The following example sets this property for a button control:</span></span>  
  
```vb  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
```

```csharp  
Button1.AccessibleDefaultActionDescription =
   "Closes the application.";  
```

```cpp  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a><span data-ttu-id="2ccbb-120">AccessibleDescription 属性</span><span class="sxs-lookup"><span data-stu-id="2ccbb-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="2ccbb-121">该字符串描述控件。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-121">This string describes the control.</span></span> <span data-ttu-id="2ccbb-122">它可能在“属性”窗口或代码中被设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ccbb-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```vb  
Button1.AccessibleDescription = "A button with text 'Exit'."  
```

```csharp  
Button1.AccessibleDescription = "A button with text 'Exit'";  
```

```cpp  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="2ccbb-123">AccessibleName 属性</span><span class="sxs-lookup"><span data-stu-id="2ccbb-123">AccessibleName Property</span></span>  
 <span data-ttu-id="2ccbb-124">这是报告给辅助工具的控件名称。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="2ccbb-125">它可能在“属性”窗口或代码中被设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ccbb-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```vb  
Button1.AccessibleName = "Order"  
```

```csharp  
Button1.AccessibleName = "Order";  
```

```cpp  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="2ccbb-126">AccessibleRole 属性</span><span class="sxs-lookup"><span data-stu-id="2ccbb-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="2ccbb-127">此属性描述控件的用户接口角色，其中包含 <xref:System.Windows.Forms.AccessibleRole> 枚举。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="2ccbb-128">新控件的值设置为 `Default`。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="2ccbb-129">这就意味着默认情况下， **Button** 控件充当 **按钮**。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="2ccbb-130">如果控件具有另一个角色，你可能希望重置此属性。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="2ccbb-131">例如，你可能正将 **PictureBox** 控件用作“图表” ，并且可能希望辅助工具将角色报告为“图表” ，而非 **PictureBox**。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="2ccbb-132">你可能还希望为已开发的自定义控件指定此属性。</span><span class="sxs-lookup"><span data-stu-id="2ccbb-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="2ccbb-133">此属性可能在“属性”窗口或代码中被设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ccbb-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart  
```

```csharp  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
```

```cpp  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ccbb-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ccbb-134">See also</span></span>

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
