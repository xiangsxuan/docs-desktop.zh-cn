---
title: L2DBForm.xaml.cs 源代码
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 882699a76eab3c291cd92c298287bc5d28fb08e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972081"
---
# <a name="l2dbformxamlcs-source-code"></a><span data-ttu-id="53226-102">L2DBForm.xaml.cs 源代码</span><span class="sxs-lookup"><span data-stu-id="53226-102">L2DBForm.xaml.cs source code</span></span>

<span data-ttu-id="53226-103">此页包含文件 *L2DBForm.xaml.cs* 中 c # 源代码的内容和说明。</span><span class="sxs-lookup"><span data-stu-id="53226-103">This page contains the contents and description of the C# source code in the file *L2DBForm.xaml.cs*.</span></span> <span data-ttu-id="53226-104">本文件中包含的 L2XDBForm 分部类可分为三个逻辑区域：数据成员、`OnRemove` 和 `OnAddBook` 按钮单击事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="53226-104">The L2XDBForm partial class contained in this file can be divided into three logical sections: data members and the `OnRemove` and `OnAddBook` button click event handlers.</span></span>

## <a name="data-members"></a><span data-ttu-id="53226-105">数据成员</span><span class="sxs-lookup"><span data-stu-id="53226-105">Data members</span></span>

<span data-ttu-id="53226-106">使用两个私有数据成员将此类与 L2DBForm.xaml 中使用的窗口资源相关联。</span><span class="sxs-lookup"><span data-stu-id="53226-106">Two private data members are used to associate this class to the window resources used in *L2DBForm.xaml*.</span></span>

- <span data-ttu-id="53226-107">命名空间变量 `myBooks` 初始化为 `"http://www.mybooks.com"`。</span><span class="sxs-lookup"><span data-stu-id="53226-107">The namespace variable `myBooks` is initialized to `"http://www.mybooks.com"`.</span></span>

- <span data-ttu-id="53226-108">该成员 `bookList` 在构造函数中初始化为 *l2dbform.xaml* 中的 CDATA 字符串，该行如下所示：</span><span class="sxs-lookup"><span data-stu-id="53226-108">The member `bookList` is initialized in the constructor to the CDATA string in *L2DBForm.xaml* with the following line:</span></span>

    ```csharp
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
    ```

## <a name="onaddbook-event-handler"></a><span data-ttu-id="53226-109">OnAddBook 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="53226-109">OnAddBook event handler</span></span>

<span data-ttu-id="53226-110">此方法包含下面三个语句：</span><span class="sxs-lookup"><span data-stu-id="53226-110">This method contains the following three statements:</span></span>

- <span data-ttu-id="53226-111">第一个条件语句用于输入验证。</span><span class="sxs-lookup"><span data-stu-id="53226-111">The first conditional statement is used for input validation.</span></span>

- <span data-ttu-id="53226-112">第二个语句根据用户在“添加新书籍”用户界面 (UI) 区域中输入的字符串值新建 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="53226-112">The second statement creates a new <xref:System.Xml.Linq.XElement> from the string values the user entered in the **Add New Book** user interface (UI) section.</span></span>

- <span data-ttu-id="53226-113">最后一个语句将此新书籍元素添加到 *l2dbform.xaml* 中的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="53226-113">The last statement adds this new book element to the data provider in *L2DBForm.xaml*.</span></span> <span data-ttu-id="53226-114">因此，动态数据绑定将用此新项自动更新 UI；不需要用户提供额外的代码。</span><span class="sxs-lookup"><span data-stu-id="53226-114">Consequently, dynamic data binding will automatically update the UI with this new item; no extra user-supplied code is required.</span></span>

## <a name="onremove-event-handler"></a><span data-ttu-id="53226-115">OnRemove 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="53226-115">OnRemove event handler</span></span>

<span data-ttu-id="53226-116">由于两个原因，`OnRemove` 处理程序比 `OnAddBook` 处理程序更复杂。</span><span class="sxs-lookup"><span data-stu-id="53226-116">The `OnRemove` handler is more complicated than the `OnAddBook` handler for two reasons.</span></span> <span data-ttu-id="53226-117">首先，由于原始 XML 包含保留的空白，因此还必须与书籍条目一起移除匹配的换行符。</span><span class="sxs-lookup"><span data-stu-id="53226-117">First, because the raw XML contains preserved white space, matching newlines must also be removed with the book entry.</span></span> <span data-ttu-id="53226-118">其次，出于方便，对所选项进行的选择会重置为列表中以前的选择。</span><span class="sxs-lookup"><span data-stu-id="53226-118">Second, as a convenience, the selection, which was on the deleted item, is reset to the previous one in the list.</span></span>

<span data-ttu-id="53226-119">但是，移除所选书籍项的核心工作仅通过两个语句完成：</span><span class="sxs-lookup"><span data-stu-id="53226-119">However, the core work of removing the selected book item is accomplished by only two statements:</span></span>

- <span data-ttu-id="53226-120">首先，检索与列表框中当前所选项相关联的书籍元素：</span><span class="sxs-lookup"><span data-stu-id="53226-120">First, the book element associated with the currently selected item in the list box is retrieved:</span></span>

    ```csharp
    XElement selBook = (XElement)lbBooks.SelectedItem;
    ```

- <span data-ttu-id="53226-121">然后，从数据提供程序中删除此元素：</span><span class="sxs-lookup"><span data-stu-id="53226-121">Then, this element is deleted from the data provider:</span></span>

    ```csharp
    selBook.Remove();
    ```

<span data-ttu-id="53226-122">此外，动态数据绑定将确保自动更新程序的 UI。</span><span class="sxs-lookup"><span data-stu-id="53226-122">Again, dynamic data binding assures that the program's UI is automatically updated.</span></span>

## <a name="example"></a><span data-ttu-id="53226-123">示例</span><span class="sxs-lookup"><span data-stu-id="53226-123">Example</span></span>

### <a name="code"></a><span data-ttu-id="53226-124">代码</span><span class="sxs-lookup"><span data-stu-id="53226-124">Code</span></span>

```csharp
using System;
using System.Linq;
using System.Collections;
using System.Collections.Generic;
using System.Diagnostics;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Input;
using System.Xml;
using System.Xml.Linq;

namespace LinqToXmlDataBinding {
    /// <summary>
    /// Interaction logic for L2XDBForm.xaml
    /// </summary>

    public partial class L2XDBForm : System.Windows.Window
    {
        XNamespace mybooks = "http://www.mybooks.com";
        XElement bookList;

        public L2XDBForm()
        {
            InitializeComponent();
            bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
        }

        void OnRemoveBook(object sender, EventArgs e)
        {
            int index = lbBooks.SelectedIndex;
            if (index < 0) return;

            XElement selBook = (XElement)lbBooks.SelectedItem;
            //Get next node before removing element.
            XNode nextNode = selBook.NextNode;
            selBook.Remove();

            //Remove any matching newline node.
            if (nextNode != null && nextNode.ToString().Trim().Equals(""))
            { nextNode.Remove(); }

            //Set selected item.
            if (lbBooks.Items.Count > 0)
            {  lbBooks.SelectedItem = lbBooks.Items[index > 0 ? index - 1 : 0]; }
        }

        void OnAddBook(object sender, EventArgs e)
        {
            if (String.IsNullOrEmpty(tbAddID.Text) ||
                String.IsNullOrEmpty(tbAddValue.Text))
            {
                MessageBox.Show("Please supply both a Book ID and a Value!", "Entry Error!");
                return;
            }
            XElement newBook = new XElement(
                                mybooks + "book",
                                new XAttribute("id", tbAddID.Text),
                                tbAddValue.Text);
            bookList.Add("  ", newBook, "\r\n");
        }
    }
}
```

### <a name="comments"></a><span data-ttu-id="53226-125">注释</span><span class="sxs-lookup"><span data-stu-id="53226-125">Comments</span></span>

<span data-ttu-id="53226-126">有关这些处理程序的关联 XAML 源，请参阅 [l2dbform.xaml 源代码](l2dbform-xaml-source-code.md)。</span><span class="sxs-lookup"><span data-stu-id="53226-126">For the associated XAML source for these handlers, see [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="53226-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53226-127">See also</span></span>

- [<span data-ttu-id="53226-128">演练：LinqToXmlDataBinding 示例</span><span class="sxs-lookup"><span data-stu-id="53226-128">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="53226-129">L2DBForm.xaml 源代码</span><span class="sxs-lookup"><span data-stu-id="53226-129">L2DBForm.xaml source code</span></span>](l2dbform-xaml-source-code.md)
