---
title: 为控件创建访问键
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972055"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="a63c7-102">如何：为 Windows 窗体控件创建访问键</span><span class="sxs-lookup"><span data-stu-id="a63c7-102">How to: Create access keys for Windows Forms controls</span></span>

<span data-ttu-id="a63c7-103">*访问键* 是菜单、菜单项或控件（如按钮）的标签文本中带下划线的字符。</span><span class="sxs-lookup"><span data-stu-id="a63c7-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="a63c7-104">使用访问键，用户可以通过将 Alt 键与预定义访问键结合使用来 "单击" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a63c7-104">With an access key, the user can "click" a button by pressing the Alt key in combination with the predefined access key.</span></span> <span data-ttu-id="a63c7-105">例如，如果按钮运行过程来打印窗体，因此其 `Text` 属性设置为 "打印"，则在字母 "p" 之前添加 "&" 符会导致在运行时将字母 "p" 添加到按钮文本中的下划线。</span><span class="sxs-lookup"><span data-stu-id="a63c7-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="a63c7-106">用户可以通过按 Alt + P 运行与该按钮关联的命令。</span><span class="sxs-lookup"><span data-stu-id="a63c7-106">The user can run the command associated with the button by pressing Alt+P.</span></span>

<span data-ttu-id="a63c7-107">无法接收焦点的控件不能有访问密钥。</span><span class="sxs-lookup"><span data-stu-id="a63c7-107">Controls that cannot receive focus can't have access keys.</span></span>

## <a name="programmatic"></a><span data-ttu-id="a63c7-108">编程</span><span class="sxs-lookup"><span data-stu-id="a63c7-108">Programmatic</span></span>

<span data-ttu-id="a63c7-109">将 `Text` 属性设置为一个字符串，该字符串包含与将作为快捷方式的字母 ( # A0) 的符号。</span><span class="sxs-lookup"><span data-stu-id="a63c7-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

```cpp
// Set the letter "P" as an access key.
button1->Text = "&Print";
```

> [!NOTE]
> <span data-ttu-id="a63c7-110">若要在标题中使用 "and" 符而不创建访问键，请包含两个与 ( # A2) 。</span><span class="sxs-lookup"><span data-stu-id="a63c7-110">To use an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="a63c7-111">标题中将显示单个号，并且不会有任何字符带有下划线。</span><span class="sxs-lookup"><span data-stu-id="a63c7-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>

## <a name="designer"></a><span data-ttu-id="a63c7-112">Designer</span><span class="sxs-lookup"><span data-stu-id="a63c7-112">Designer</span></span>

<span data-ttu-id="a63c7-113">在 Visual Studio 的 " **属性** " 窗口中，将 " **Text** " 属性设置为一个字符串，该字符串包含与将为访问键的字母 ( "&" ) 。</span><span class="sxs-lookup"><span data-stu-id="a63c7-113">In the **Properties** window of Visual Studio, set the **Text** property to a string that includes an ampersand ('&') before the letter that will be the access key.</span></span> <span data-ttu-id="a63c7-114">例如，若要将字母 "P" 设置为访问键，请输入 **&Print**。</span><span class="sxs-lookup"><span data-stu-id="a63c7-114">For example, to set the letter "P" as the access key, enter **&Print**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a63c7-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a63c7-115">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="a63c7-116">如何：响应 Windows 窗体按钮的单击</span><span class="sxs-lookup"><span data-stu-id="a63c7-116">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="a63c7-117">如何：设置 Windows 窗体控件所显示的文本</span><span class="sxs-lookup"><span data-stu-id="a63c7-117">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="a63c7-118">标记单个 Windows 窗体控件并提供它们的快捷方式</span><span class="sxs-lookup"><span data-stu-id="a63c7-118">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
