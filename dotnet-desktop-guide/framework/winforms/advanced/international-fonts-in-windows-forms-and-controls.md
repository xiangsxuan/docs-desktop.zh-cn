---
title: 窗体和控件中的国际字体
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 59dde6bb384d644321a8ff5674d735f8e6d36fd0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971382"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="5380f-102">Windows 窗体和控件中的国际字体</span><span class="sxs-lookup"><span data-stu-id="5380f-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="5380f-103">在国际应用程序中，建议尽可能使用字体回退来选择字体。</span><span class="sxs-lookup"><span data-stu-id="5380f-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="5380f-104">字体回退是指系统确定字符所属的脚本。</span><span class="sxs-lookup"><span data-stu-id="5380f-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="5380f-105">使用字体回退</span><span class="sxs-lookup"><span data-stu-id="5380f-105">Using font fallback</span></span>

<span data-ttu-id="5380f-106">若要利用此功能，请不要 <xref:System.Drawing.Font> 为窗体或任何其他元素设置属性。</span><span class="sxs-lookup"><span data-stu-id="5380f-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="5380f-107">应用程序将自动使用默认系统字体，该字体不同于操作系统的一种本地化语言。</span><span class="sxs-lookup"><span data-stu-id="5380f-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="5380f-108">当应用程序运行时，系统会自动为操作系统中选定的区域性提供正确的字体。</span><span class="sxs-lookup"><span data-stu-id="5380f-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="5380f-109">不设置字体的规则有一个例外，即更改字体样式。</span><span class="sxs-lookup"><span data-stu-id="5380f-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="5380f-110">这对于应用程序而言很重要，用户在该应用程序中单击按钮以使文本框中的文本以粗体显示。</span><span class="sxs-lookup"><span data-stu-id="5380f-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="5380f-111">为此，您可以编写一个函数，根据窗体的字体是，将文本框的字体样式更改为粗体。</span><span class="sxs-lookup"><span data-stu-id="5380f-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="5380f-112">在两个位置调用此函数很重要：在按钮的 <xref:System.Windows.Forms.Control.Click> 事件处理程序和 <xref:System.Windows.Forms.Control.FontChanged> 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="5380f-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="5380f-113">如果只在事件处理程序中调用函数， <xref:System.Windows.Forms.Control.Click> 而其他代码段更改整个窗体的字体系列，则文本框不会随窗体的其余部分而更改。</span><span class="sxs-lookup"><span data-stu-id="5380f-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

<span data-ttu-id="5380f-114">但是，在对应用程序进行本地化时，对于某些语言，粗体字显示的字体可能会很差。</span><span class="sxs-lookup"><span data-stu-id="5380f-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="5380f-115">如果需要考虑这一点，您希望本地化人员可以选择将字体从粗体切换为普通文本。</span><span class="sxs-lookup"><span data-stu-id="5380f-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="5380f-116">由于本地化人员通常不是开发人员，因此不能访问源代码，因此，只需在资源文件中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="5380f-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="5380f-117">为此，请将 <xref:System.Drawing.Font.Bold%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="5380f-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="5380f-118">这会导致将字体设置写出到资源文件，本地化人员可以在这些资源文件中对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="5380f-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="5380f-119">然后，在方法之后编写代码 `InitializeComponent` ，根据窗体的字体为，但使用资源文件中指定的字体样式来重置字体。</span><span class="sxs-lookup"><span data-stu-id="5380f-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="5380f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5380f-120">See also</span></span>

- [<span data-ttu-id="5380f-121">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="5380f-121">Using Fonts and Text</span></span>](using-fonts-and-text.md)
