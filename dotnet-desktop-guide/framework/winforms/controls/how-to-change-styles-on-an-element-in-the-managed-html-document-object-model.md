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
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a>如何：在托管 HTML 文档对象模型中更改元素的样式

您可以使用 HTML 中的样式来控制文档及其元素的外观。 <xref:System.Windows.Forms.HtmlDocument> 和 <xref:System.Windows.Forms.HtmlElement> 支持 <xref:System.Windows.Forms.HtmlElement.Style%2A> 采用以下格式的样式字符串的属性：

`name1:value1;...;nameN:valueN;`

下面是一个 `DIV` 带有样式字符串的，它将字体设置为 Arial，并将所有文本设置为粗体：

```html
<DIV style="font-face:arial;font-weight:bold;">
Hello, world!
</DIV>
```

使用属性操作样式的问题 <xref:System.Windows.Forms.HtmlElement.Style%2A> 在于，在字符串中添加和移除单个样式设置会很繁琐。 例如，当用户将光标置于上时，它将成为一个复杂的过程，您可以使用斜体呈现以前的文本 `DIV` ，并在光标离开时去掉斜体 `DIV` 。 如果需要以这种方式操作大量样式，则时间会成为一个问题。

以下过程包含可用于轻松操作 HTML 文档和元素上的样式的代码。 此过程要求你知道如何在 Windows 窗体中执行基本任务，例如创建一个新项目并向窗体添加一个控件。

### <a name="to-process-style-changes-in-a-windows-forms-application"></a>处理 Windows 窗体应用程序中的样式更改

1. 创建新的 Windows 窗体项目。

2. 在适用于你的编程语言的扩展中创建以结尾的新类文件。

3. 将 `StyleGenerator` 本主题的 "示例" 部分中的类代码复制到类文件中，并保存代码。

4. 将以下 HTML 保存到名为 Test.htm 的文件中。

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

5. 将名为的 <xref:System.Windows.Forms.WebBrowser> 控件添加 `webBrowser1` 到项目的主窗体。

6. 将以下代码添加到项目的代码文件中。

    > [!IMPORTANT]
    > 确保 `webBrowser1_DocumentCompleted` 事件处理程序已配置为事件的侦听器 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 。 在 Visual Studio 中，双击 <xref:System.Windows.Forms.WebBrowser> 控件; 在文本编辑器中，以编程方式配置侦听器。

     [!code-csharp[ManagedDOMStyles#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]

7. 运行该项目。 在第一台计算机上运行光标 `DIV` ，观察代码的效果。

## <a name="example"></a>示例

下面的代码示例演示类的完整代码，该代码 `StyleGenerator` 分析现有样式值，支持添加、更改和删除样式，并返回具有所请求更改的新样式值。

[!code-csharp[ManagedDOMStyles#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
[!code-vb[ManagedDOMStyles#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.HtmlElement>
