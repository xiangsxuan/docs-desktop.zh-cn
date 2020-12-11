---
title: 如何：在托管 HTML 文档对象模型中更改元素的样式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
ms.openlocfilehash: 728bc77db959e25fe31d2ff37288b2359dca852e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971243"
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a><span data-ttu-id="a4911-102">如何：在托管 HTML 文档对象模型中更改元素的样式</span><span class="sxs-lookup"><span data-stu-id="a4911-102">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>

<span data-ttu-id="a4911-103">您可以使用 HTML 中的样式来控制文档及其元素的外观。</span><span class="sxs-lookup"><span data-stu-id="a4911-103">You can use styles in HTML to control the appearance of a document and its elements.</span></span> <span data-ttu-id="a4911-104"><xref:System.Windows.Forms.HtmlDocument> 和 <xref:System.Windows.Forms.HtmlElement> 支持 <xref:System.Windows.Forms.HtmlElement.Style%2A> 采用以下格式的样式字符串的属性：</span><span class="sxs-lookup"><span data-stu-id="a4911-104"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> support <xref:System.Windows.Forms.HtmlElement.Style%2A> properties that take style strings of the following format:</span></span>

`name1:value1;...;nameN:valueN;`

<span data-ttu-id="a4911-105">下面是一个 `DIV` 带有样式字符串的，它将字体设置为 Arial，并将所有文本设置为粗体：</span><span class="sxs-lookup"><span data-stu-id="a4911-105">Here is a `DIV` with a style string that sets the font to Arial and all text to bold:</span></span>

```html
<DIV style="font-face:arial;font-weight:bold;">
Hello, world!
</DIV>
```

<span data-ttu-id="a4911-106">使用属性操作样式的问题 <xref:System.Windows.Forms.HtmlElement.Style%2A> 在于，在字符串中添加和移除单个样式设置会很繁琐。</span><span class="sxs-lookup"><span data-stu-id="a4911-106">The problem with manipulating styles using the <xref:System.Windows.Forms.HtmlElement.Style%2A> property is that it can prove cumbersome to add to and remove individual style settings from the string.</span></span> <span data-ttu-id="a4911-107">例如，当用户将光标置于上时，它将成为一个复杂的过程，您可以使用斜体呈现以前的文本 `DIV` ，并在光标离开时去掉斜体 `DIV` 。</span><span class="sxs-lookup"><span data-stu-id="a4911-107">For example, it would become a complex procedure for you to render the previous text in italics whenever the user positions the cursor over the `DIV`, and take italics off when the cursor leaves the `DIV`.</span></span> <span data-ttu-id="a4911-108">如果需要以这种方式操作大量样式，则时间会成为一个问题。</span><span class="sxs-lookup"><span data-stu-id="a4911-108">Time would become an issue if you need to manipulate a large number of styles in this manner.</span></span>

<span data-ttu-id="a4911-109">以下过程包含可用于轻松操作 HTML 文档和元素上的样式的代码。</span><span class="sxs-lookup"><span data-stu-id="a4911-109">The following procedure contains code that you can use to easily manipulate styles on HTML documents and elements.</span></span> <span data-ttu-id="a4911-110">此过程要求你知道如何在 Windows 窗体中执行基本任务，例如创建一个新项目并向窗体添加一个控件。</span><span class="sxs-lookup"><span data-stu-id="a4911-110">The procedure requires that you know how to perform basic tasks in Windows Forms, such as creating a new project and adding a control to a form.</span></span>

### <a name="to-process-style-changes-in-a-windows-forms-application"></a><span data-ttu-id="a4911-111">处理 Windows 窗体应用程序中的样式更改</span><span class="sxs-lookup"><span data-stu-id="a4911-111">To process style changes in a Windows Forms application</span></span>

1. <span data-ttu-id="a4911-112">创建新的 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="a4911-112">Create a new Windows Forms project.</span></span>

2. <span data-ttu-id="a4911-113">在适用于你的编程语言的扩展中创建以结尾的新类文件。</span><span class="sxs-lookup"><span data-stu-id="a4911-113">Create a new class file ending in the extension appropriate for your programming language.</span></span>

3. <span data-ttu-id="a4911-114">将 `StyleGenerator` 本主题的 "示例" 部分中的类代码复制到类文件中，并保存代码。</span><span class="sxs-lookup"><span data-stu-id="a4911-114">Copy the `StyleGenerator` class code in the Example section of this topic into the class file, and save the code.</span></span>

4. <span data-ttu-id="a4911-115">将以下 HTML 保存到名为 Test.htm 的文件中。</span><span class="sxs-lookup"><span data-stu-id="a4911-115">Save the following HTML to a file named Test.htm.</span></span>

    ```html
    <HTML>
        <BODY>

            <DIV style="font-face:arial;font-weight:bold;">
                Hello, world!
            </DIV><P>

            <DIV>
                Hello again, world!
            </DIV><P>

        </BODY>
    </HTML>
    ```

5. <span data-ttu-id="a4911-116">将名为的 <xref:System.Windows.Forms.WebBrowser> 控件添加 `webBrowser1` 到项目的主窗体。</span><span class="sxs-lookup"><span data-stu-id="a4911-116">Add a <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1` to the main form of your project.</span></span>

6. <span data-ttu-id="a4911-117">将以下代码添加到项目的代码文件中。</span><span class="sxs-lookup"><span data-stu-id="a4911-117">Add the following code to your project's code file.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a4911-118">确保 `webBrowser1_DocumentCompleted` 事件处理程序已配置为事件的侦听器 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 。</span><span class="sxs-lookup"><span data-stu-id="a4911-118">Ensure that the `webBrowser1_DocumentCompleted` event handler is configured as a listener for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="a4911-119">在 Visual Studio 中，双击 <xref:System.Windows.Forms.WebBrowser> 控件; 在文本编辑器中，以编程方式配置侦听器。</span><span class="sxs-lookup"><span data-stu-id="a4911-119">In Visual Studio, double-click on the <xref:System.Windows.Forms.WebBrowser> control; in a text editor, configure the listener programmatically.</span></span>

     [!code-csharp[ManagedDOMStyles#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]

7. <span data-ttu-id="a4911-120">运行该项目。</span><span class="sxs-lookup"><span data-stu-id="a4911-120">Run the project.</span></span> <span data-ttu-id="a4911-121">在第一台计算机上运行光标 `DIV` ，观察代码的效果。</span><span class="sxs-lookup"><span data-stu-id="a4911-121">Run your cursor over the first `DIV` to observe the effects of the code.</span></span>

## <a name="example"></a><span data-ttu-id="a4911-122">示例</span><span class="sxs-lookup"><span data-stu-id="a4911-122">Example</span></span>

<span data-ttu-id="a4911-123">下面的代码示例演示类的完整代码，该代码 `StyleGenerator` 分析现有样式值，支持添加、更改和删除样式，并返回具有所请求更改的新样式值。</span><span class="sxs-lookup"><span data-stu-id="a4911-123">The following code example shows the full code for the `StyleGenerator` class, which parses an existing style value, supports adding, changing, and removing styles, and returns a new style value with the requested changes.</span></span>

[!code-csharp[ManagedDOMStyles#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
[!code-vb[ManagedDOMStyles#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]

## <a name="see-also"></a><span data-ttu-id="a4911-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4911-124">See also</span></span>

- <xref:System.Windows.Forms.HtmlElement>
