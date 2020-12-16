---
title: 设置控件显示的文本
description: 了解如何设置 Windows 窗体控件所显示的文本。 使用 Text 属性设置或返回文本，或使用 Font 属性更改字体。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.openlocfilehash: 2fd5a62310ae5e7d6e0528c7f12f37ed40f8a626
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941920"
---
# <a name="how-to-set-the-text-displayed-by-a-control-windows-forms-net"></a><span data-ttu-id="52d51-104">操作说明：设置控件显示的文本（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="52d51-104">How to: Set the text displayed by a control (Windows Forms .NET)</span></span>

<span data-ttu-id="52d51-105">Windows 窗体控件通常会显示一些与控件的主要功能相关的文本。</span><span class="sxs-lookup"><span data-stu-id="52d51-105">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="52d51-106">例如，<xref:System.Windows.Forms.Button> 控件通常会显示一个题注，用于指示单击按钮时将执行的操作。</span><span class="sxs-lookup"><span data-stu-id="52d51-106">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="52d51-107">对于所有控件而言，都可通过使用 <xref:System.Windows.Forms.Control.Text%2A> 属性来设置或返回文本。</span><span class="sxs-lookup"><span data-stu-id="52d51-107">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="52d51-108">可以使用 <xref:System.Windows.Forms.Control.Font%2A> 属性更改字体。</span><span class="sxs-lookup"><span data-stu-id="52d51-108">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="52d51-109">还可使用[设计器](#designer)来设置文本。</span><span class="sxs-lookup"><span data-stu-id="52d51-109">You can also set the text by using the [designer](#designer).</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a><span data-ttu-id="52d51-110">Designer</span><span class="sxs-lookup"><span data-stu-id="52d51-110">Designer</span></span>

01. <span data-ttu-id="52d51-111">在 Visual Studio 中的“属性”窗口中，将控件的 Text 属性设置为相应的字符串 。</span><span class="sxs-lookup"><span data-stu-id="52d51-111">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

    <span data-ttu-id="52d51-112">若要创建一个带下划线的快捷键，请在将作为快捷键的字母前添加一个 & 符号。</span><span class="sxs-lookup"><span data-stu-id="52d51-112">To create an underlined shortcut key, include an ampersand (&) before the letter that will be the shortcut key.</span></span>

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-text.png" alt-text="显示了 Text 属性的 .NET Windows 窗体的 Visual Studio“属性”窗格。":::

01. <span data-ttu-id="52d51-114">在“属性”窗口中，选择 Font 属性旁边的省略号按钮（![Visual Studio 的“属性”窗口中的省略号按钮 (...)](../media/visual-studio-ellipsis-button.png)） 。</span><span class="sxs-lookup"><span data-stu-id="52d51-114">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](../media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-font.png" alt-text="显示了 Font 属性的 .NET Windows 窗体的 Visual Studio“属性”窗格。":::

    <span data-ttu-id="52d51-116">在标准字体对话框中，用类型、大小和样式等设置调整字体。</span><span class="sxs-lookup"><span data-stu-id="52d51-116">In the standard font dialog box, adjust the font with settings such as type, size, and style.</span></span>

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/font-window.png" alt-text="显示了 Font 设置窗口的 .NET Windows 窗体的 Visual Studio“属性”窗格。":::

## <a name="programmatic"></a><span data-ttu-id="52d51-118">编程</span><span class="sxs-lookup"><span data-stu-id="52d51-118">Programmatic</span></span>

01. <span data-ttu-id="52d51-119">将 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为字符串。</span><span class="sxs-lookup"><span data-stu-id="52d51-119">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

    <span data-ttu-id="52d51-120">若要创建一个带下划线的访问键，请在将作为访问键的字母前添加一个 & 符号。</span><span class="sxs-lookup"><span data-stu-id="52d51-120">To create an underlined access key, include an ampersand (&) before the letter that will be the access key.</span></span>

01. <span data-ttu-id="52d51-121">将 <xref:System.Windows.Forms.Control.Font%2A> 属性设置为类型 <xref:System.Drawing.Font> 的对象。</span><span class="sxs-lookup"><span data-stu-id="52d51-121">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    > [!NOTE]
    > <span data-ttu-id="52d51-122">可使用转义符来显示用户界面元素中的特殊字符，通常对这些元素（如菜单项）有着不同的解释。</span><span class="sxs-lookup"><span data-stu-id="52d51-122">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="52d51-123">例如，下面的代码行将菜单项的文本设置为“& 现读取完全不同的内容”：</span><span class="sxs-lookup"><span data-stu-id="52d51-123">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

## <a name="see-also"></a><span data-ttu-id="52d51-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52d51-124">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="52d51-125">如何：创建 Windows 窗体控件的访问键</span><span class="sxs-lookup"><span data-stu-id="52d51-125">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys.md)
