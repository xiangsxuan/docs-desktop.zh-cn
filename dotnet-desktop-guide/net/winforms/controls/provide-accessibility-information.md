---
title: 为 Windows 窗体上的控件提供辅助功能信息
description: 了解如何向控件添加辅助功能信息。 通过 Windows 窗体，可以向控件添加辅助功能设置，为残疾人士提供帮助。
ms.date: 10/26/2020
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
ms.openlocfilehash: 27c06a7d01cb98ecb2f7216c09dc292d2fe68a6f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941990"
---
# <a name="providing-accessibility-information-for-controls-windows-forms-net"></a><span data-ttu-id="84cf5-104">为控件提供辅助功能信息（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="84cf5-104">Providing Accessibility Information for Controls (Windows Forms .NET)</span></span>

<span data-ttu-id="84cf5-105">辅助工具是专用的程序和设备，用于帮助残障人士更加有效地使用计算机。</span><span class="sxs-lookup"><span data-stu-id="84cf5-105">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="84cf5-106">示例包括适用于盲人的屏幕阅读器，还有声音输入实用功能，方便人们发出声音命令，而不使用鼠标或键盘。</span><span class="sxs-lookup"><span data-stu-id="84cf5-106">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="84cf5-107">这些辅助工具与由 Windows 窗体控件公开的辅助功能属性相交互。</span><span class="sxs-lookup"><span data-stu-id="84cf5-107">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="84cf5-108">这些属性为：</span><span class="sxs-lookup"><span data-stu-id="84cf5-108">These properties are:</span></span>

- <xref:System.Windows.Forms.AccessibleObject?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=fullName>
- <xref:System.Windows.Forms.AccessibleRole?displayProperty=fullName>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessibilityobject-property"></a><span data-ttu-id="84cf5-109">AccessibilityObject 属性</span><span class="sxs-lookup"><span data-stu-id="84cf5-109">AccessibilityObject Property</span></span>

<span data-ttu-id="84cf5-110">此只读属性包含 <xref:System.Windows.Forms.AccessibleObject> 实例。</span><span class="sxs-lookup"><span data-stu-id="84cf5-110">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="84cf5-111">`AccessibleObject` 实现了 <xref:Accessibility.IAccessible> 接口，它提供了有关控件的说明、屏幕位置、导航功能和值的信息。</span><span class="sxs-lookup"><span data-stu-id="84cf5-111">The `AccessibleObject` implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="84cf5-112">在将控件添加到窗体时，设计器会设置此值。</span><span class="sxs-lookup"><span data-stu-id="84cf5-112">The designer sets this value when the control is added to the form.</span></span>

## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="84cf5-113">AccessibleDefaultActionDescription 属性</span><span class="sxs-lookup"><span data-stu-id="84cf5-113">AccessibleDefaultActionDescription Property</span></span>

<span data-ttu-id="84cf5-114">该字符串描述控件的操作。</span><span class="sxs-lookup"><span data-stu-id="84cf5-114">This string describes the action of the control.</span></span> <span data-ttu-id="84cf5-115">它不显示在“属性”窗口中，可能只在代码中被设置。</span><span class="sxs-lookup"><span data-stu-id="84cf5-115">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="84cf5-116">下面的示例为按钮控件设置 <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription> 属性：</span><span class="sxs-lookup"><span data-stu-id="84cf5-116">The following example sets the <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription> property for a button control:</span></span>

```vb
Button1.AccessibleDefaultActionDescription = "Closes the application."
```

```csharp
button1.AccessibleDefaultActionDescription = "Closes the application.";
```

## <a name="accessibledescription-property"></a><span data-ttu-id="84cf5-117">AccessibleDescription 属性</span><span class="sxs-lookup"><span data-stu-id="84cf5-117">AccessibleDescription Property</span></span>

<span data-ttu-id="84cf5-118">该字符串描述控件。</span><span class="sxs-lookup"><span data-stu-id="84cf5-118">This string describes the control.</span></span> <span data-ttu-id="84cf5-119"><xref:System.Windows.Forms.Control.AccessibleDescription> 属性可能在“属性”窗口或代码中被设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="84cf5-119">The <xref:System.Windows.Forms.Control.AccessibleDescription> property may be set in the Properties window, or in code as follows:</span></span>

```vb
Button1.AccessibleDescription = "A button with text 'Exit'."
```

```csharp
button1.AccessibleDescription = "A button with text 'Exit'";
```

## <a name="accessiblename-property"></a><span data-ttu-id="84cf5-120">AccessibleName 属性</span><span class="sxs-lookup"><span data-stu-id="84cf5-120">AccessibleName Property</span></span>

<span data-ttu-id="84cf5-121">这是报告给辅助工具的控件名称。</span><span class="sxs-lookup"><span data-stu-id="84cf5-121">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="84cf5-122"><xref:System.Windows.Forms.Control.AccessibleName> 属性可能在“属性”窗口或代码中被设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="84cf5-122">The <xref:System.Windows.Forms.Control.AccessibleName> property may be set in the Properties window, or in code as follows:</span></span>

```vb
Button1.AccessibleName = "Order"
```

```csharp
button1.AccessibleName = "Order";
```

## <a name="accessiblerole-property"></a><span data-ttu-id="84cf5-123">AccessibleRole 属性</span><span class="sxs-lookup"><span data-stu-id="84cf5-123">AccessibleRole Property</span></span>

<span data-ttu-id="84cf5-124">此属性描述控件的用户接口角色，其中包含 <xref:System.Windows.Forms.AccessibleRole> 枚举。</span><span class="sxs-lookup"><span data-stu-id="84cf5-124">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="84cf5-125">新控件的值设置为 `Default`。</span><span class="sxs-lookup"><span data-stu-id="84cf5-125">A new control has the value set to `Default`.</span></span> <span data-ttu-id="84cf5-126">这意味着默认情况下，`Button` 控件充当 `Button`。</span><span class="sxs-lookup"><span data-stu-id="84cf5-126">This would mean that by default, a `Button` control acts as a `Button`.</span></span> <span data-ttu-id="84cf5-127">如果控件具有另一个角色，你可能希望重置此属性。</span><span class="sxs-lookup"><span data-stu-id="84cf5-127">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="84cf5-128">例如，你可能正将 `PictureBox` 控件用作 `Chart`，并且可能希望辅助工具将角色报告为 `Chart`，而非 `PictureBox`。</span><span class="sxs-lookup"><span data-stu-id="84cf5-128">For example, you may be using a `PictureBox` control as a `Chart`, and you may want accessibility aids to report the role as a `Chart`, not as a `PictureBox`.</span></span> <span data-ttu-id="84cf5-129">你可能还希望为已开发的自定义控件指定此属性。</span><span class="sxs-lookup"><span data-stu-id="84cf5-129">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="84cf5-130">此属性可能在“属性”窗口或代码中被设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="84cf5-130">This property may be set in the Properties window, or in code as follows:</span></span>

```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart
```

```csharp
pictureBox1.AccessibleRole = AccessibleRole.Chart;
```

## <a name="see-also"></a><span data-ttu-id="84cf5-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84cf5-131">See also</span></span>

- [<span data-ttu-id="84cf5-132">Label 控件概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="84cf5-132">Label control overview (Windows Forms .NET)</span></span>](labels.md)
- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
