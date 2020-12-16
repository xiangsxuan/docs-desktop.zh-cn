---
title: 创建控件访问键
description: 了解如何在适用于 .NET 的 Windows 窗体中对控件或标签设置访问键快捷方式。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.openlocfilehash: 4d746082ffbaa749b882dcb1a769b5f9541c6fe8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941996"
---
# <a name="add-an-access-key-shortcut-to-a-control-windows-forms-net"></a><span data-ttu-id="230ea-103">向控件添加访问键快捷方式（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="230ea-103">Add an access key shortcut to a control (Windows Forms .NET)</span></span>

<span data-ttu-id="230ea-104">访问键是菜单、菜单项或控件（如按钮）标签的文本中带下划线的字符。</span><span class="sxs-lookup"><span data-stu-id="230ea-104">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="230ea-105">使用访问键，用户可通过同时按 <kbd>Alt</kbd> 键和预定义的访问键来“单击”按钮。</span><span class="sxs-lookup"><span data-stu-id="230ea-105">With an access key, the user can "click" a button by pressing the <kbd>Alt</kbd> key in combination with the predefined access key.</span></span> <span data-ttu-id="230ea-106">例如，如果某个按钮运行打印窗体的过程，因此其 `Text` 属性设置为“Print”，则在字母“P”之前添加 & 号将导致在运行时为按钮文本中的字母“P”添加下划线。</span><span class="sxs-lookup"><span data-stu-id="230ea-106">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="230ea-107">用户可通过按 <kbd>Alt</kbd> 来运行与该按钮关联的命令。</span><span class="sxs-lookup"><span data-stu-id="230ea-107">The user can run the command associated with the button by pressing <kbd>Alt</kbd>.</span></span>

<span data-ttu-id="230ea-108">不能接收焦点的控件不能有访问键，但标签控件除外。</span><span class="sxs-lookup"><span data-stu-id="230ea-108">Controls that cannot receive focus can't have access keys, except label controls.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a><span data-ttu-id="230ea-109">Designer</span><span class="sxs-lookup"><span data-stu-id="230ea-109">Designer</span></span>

<span data-ttu-id="230ea-110">在 Visual Studio 的“属性”窗口中，将 Text 属性设置为一个字符串，该字符串在将作为访问键的字母之前包含一个 & 符号 。</span><span class="sxs-lookup"><span data-stu-id="230ea-110">In the **Properties** window of Visual Studio, set the **Text** property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="230ea-111">例如，若要将字母“P”设置为访问键，请输入 &Print。</span><span class="sxs-lookup"><span data-stu-id="230ea-111">For example, to set the letter "P" as the access key, enter **&Print**.</span></span>

:::image type="content" source="media/how-to-create-access-keys/properties-text.png" alt-text="包含已选择的 Text 属性和访问键的属性对话框":::

## <a name="programmatic"></a><span data-ttu-id="230ea-113">编程</span><span class="sxs-lookup"><span data-stu-id="230ea-113">Programmatic</span></span>

<span data-ttu-id="230ea-114">将 `Text` 属性设置为一个字符串，该字符串在将作为快捷方式的字母之前包含一个 & 符号。</span><span class="sxs-lookup"><span data-stu-id="230ea-114">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

## <a name="use-a-label-to-focus-a-control"></a><span data-ttu-id="230ea-115">使用标签聚焦控件</span><span class="sxs-lookup"><span data-stu-id="230ea-115">Use a label to focus a control</span></span>

<span data-ttu-id="230ea-116">尽管标签无法被聚焦，它也能够按窗体的 Tab 键顺序来聚焦下一个控件。</span><span class="sxs-lookup"><span data-stu-id="230ea-116">Even though a label cannot be focused, it has the ability to focus the next control in the tab order of the form.</span></span> <span data-ttu-id="230ea-117">每个控件都分配有一个 <xref:System.Windows.Forms.Control.TabIndex> 属性的值，通常以升序顺序排列。</span><span class="sxs-lookup"><span data-stu-id="230ea-117">Each control is assigned a value to the <xref:System.Windows.Forms.Control.TabIndex> property, generally in ascending sequential order.</span></span> <span data-ttu-id="230ea-118">为 [Label.Text](xref:System.Windows.Forms.Label.Text) 属性分配访问键时，将聚焦于按 Tab 键顺序排列的下一个控件。</span><span class="sxs-lookup"><span data-stu-id="230ea-118">When the access key is assigned to the [Label.Text](xref:System.Windows.Forms.Label.Text) property, the next control in the sequential tab order is focused.</span></span>

<span data-ttu-id="230ea-119">使用[计划](#programmatic)部分中的示例，如果该按钮未设置任何文本，而是显示打印机的图像，则可使用标签来聚焦该按钮。</span><span class="sxs-lookup"><span data-stu-id="230ea-119">Using the example from the [Programmatic](#programmatic) section, if the button didn't have any text set, but instead presented an image of a printer, you could use a label to focus the button.</span></span>

```vb
' Set the letter "P" as an access key.
Label1.Text = "&Print"
Label1.TabIndex = 9
Button1.TabIndex = 10
```

```csharp
// Set the letter "P" as an access key.
label1.Text = "&Print";
label1.TabIndex = 9
button1.TabIndex = 10
```

## <a name="display-an-ampersand"></a><span data-ttu-id="230ea-120">显示 & 符号</span><span class="sxs-lookup"><span data-stu-id="230ea-120">Display an ampersand</span></span>

<span data-ttu-id="230ea-121">设置将 & 符号解释为访问键的控件的文本或描述文字时，请使用两个连续的 & 符号 (&&) 来显示单个 & 符号。</span><span class="sxs-lookup"><span data-stu-id="230ea-121">When setting the text or caption of a control that interprets an ampersand (&) as an access key, use two consecutive ampersands (&&) to display a single ampersand.</span></span> <span data-ttu-id="230ea-122">例如，设置为 `"Print && Close"` 的按钮的文本显示在 `Print & Close` 的描述文字中：</span><span class="sxs-lookup"><span data-stu-id="230ea-122">For example, the text of a button set to `"Print && Close"` displays in the caption of `Print & Close`:</span></span>

```vb
' Set the letter "P" as an access key.
Button1.Text = "Print && Close"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "Print && Close";
```

:::image type="content" source="media/how-to-create-access-keys/double-ampersand.png" alt-text="在按钮中显示 & 符号":::

## <a name="see-also"></a><span data-ttu-id="230ea-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="230ea-124">See also</span></span>

- [<span data-ttu-id="230ea-125">如何：设置 Windows 窗体控件显示的文本</span><span class="sxs-lookup"><span data-stu-id="230ea-125">How to: Set the text displayed by a Windows Forms control</span></span>](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.Label>
