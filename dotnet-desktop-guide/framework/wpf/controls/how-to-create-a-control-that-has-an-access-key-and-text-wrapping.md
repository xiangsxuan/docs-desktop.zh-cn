---
title: 如何：创建具有访问键和文本换行的控件
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 86239374ca9cb3bd3d71415496e32d4a27fbae5a
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973980"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="2e23d-102">如何：创建具有访问键和文本换行的控件</span><span class="sxs-lookup"><span data-stu-id="2e23d-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>

<span data-ttu-id="2e23d-103">此示例演示如何创建具有访问键且支持文本换行的控件。</span><span class="sxs-lookup"><span data-stu-id="2e23d-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="2e23d-104">该示例使用 <xref:System.Windows.Controls.Label> 控件来说明这些概念。</span><span class="sxs-lookup"><span data-stu-id="2e23d-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e23d-105">示例</span><span class="sxs-lookup"><span data-stu-id="2e23d-105">Example</span></span>  

 <span data-ttu-id="2e23d-106">**将文本换行添加到标签**</span><span class="sxs-lookup"><span data-stu-id="2e23d-106">**Add Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="2e23d-107"><xref:System.Windows.Controls.Label>控件不支持文本换行。</span><span class="sxs-lookup"><span data-stu-id="2e23d-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="2e23d-108">如果需要一个多次换行的标签，可以嵌套其他支持文本换行的元素，并将该元素放在标签内。</span><span class="sxs-lookup"><span data-stu-id="2e23d-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="2e23d-109">下面的示例演示如何使用 <xref:System.Windows.Controls.TextBlock> 来创建一个环绕多行文本的标签。</span><span class="sxs-lookup"><span data-stu-id="2e23d-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 <span data-ttu-id="2e23d-110">**将访问键和文本换行添加到标签**</span><span class="sxs-lookup"><span data-stu-id="2e23d-110">**Add an Access Key and Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="2e23d-111">如果需要 <xref:System.Windows.Controls.Label> 具有访问密钥)  (助记键的，请使用中的 <xref:System.Windows.Controls.AccessText> 元素 <xref:System.Windows.Controls.Label> 。</span><span class="sxs-lookup"><span data-stu-id="2e23d-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="2e23d-112">控件（如、、、、、、 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Button> 和） <xref:System.Windows.Controls.RadioButton> <xref:System.Windows.Controls.CheckBox> <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.TabItem> <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.GroupBox> 具有默认控件模板。</span><span class="sxs-lookup"><span data-stu-id="2e23d-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="2e23d-113">这些模板包含一个 <xref:System.Windows.Controls.ContentPresenter> 。</span><span class="sxs-lookup"><span data-stu-id="2e23d-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="2e23d-114">可对其设置的属性之一 <xref:System.Windows.Controls.ContentPresenter> 是 <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A> = "true"，可用于指定控件的访问键。</span><span class="sxs-lookup"><span data-stu-id="2e23d-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="2e23d-115">下面的示例演示如何创建一个 <xref:System.Windows.Controls.Label> 具有访问键且支持文本换行的。</span><span class="sxs-lookup"><span data-stu-id="2e23d-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="2e23d-116">若要启用文本换行，示例设置了 <xref:System.Windows.Controls.AccessText.TextWrapping%2A> 属性，并使用下划线字符来指定访问密钥。</span><span class="sxs-lookup"><span data-stu-id="2e23d-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="2e23d-117">（紧跟下划线字符后面的字符就是访问键。）</span><span class="sxs-lookup"><span data-stu-id="2e23d-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="2e23d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e23d-118">See also</span></span>

- <span data-ttu-id="2e23d-119">[如何：设置 Label 的目标属性](/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2e23d-119">[How to: Set the Target Property of a Label](/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))</span></span>
