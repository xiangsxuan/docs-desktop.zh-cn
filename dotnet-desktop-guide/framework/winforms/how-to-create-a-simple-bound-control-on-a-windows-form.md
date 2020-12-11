---
title: 如何：在 Windows 窗体上创建简单绑定控件
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: bb7554831ab3698333850b71c42a5343ceb7d682
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970264"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="3a03e-102">如何：在 Windows 窗体上创建简单绑定控件</span><span class="sxs-lookup"><span data-stu-id="3a03e-102">How to: Create a simple-bound control on a Windows Form</span></span>

<span data-ttu-id="3a03e-103">使用 *简单绑定*，可以在控件中显示单个数据元素，例如数据集表中的列值。</span><span class="sxs-lookup"><span data-stu-id="3a03e-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="3a03e-104">可以简单地将控件的任何属性绑定到数据值。</span><span class="sxs-lookup"><span data-stu-id="3a03e-104">You can simple-bind any property of a control to a data value.</span></span>

## <a name="to-simple-bind-a-control"></a><span data-ttu-id="3a03e-105">简单-绑定控件</span><span class="sxs-lookup"><span data-stu-id="3a03e-105">To simple-bind a control</span></span>

1. <span data-ttu-id="3a03e-106">连接到数据源。</span><span class="sxs-lookup"><span data-stu-id="3a03e-106">Connect to a data source.</span></span> <span data-ttu-id="3a03e-107">有关详细信息，请参阅 [连接到数据源](/dotnet/framework/data/adonet/connecting-to-a-data-source)。</span><span class="sxs-lookup"><span data-stu-id="3a03e-107">For more information, see [Connecting to a Data Source](/dotnet/framework/data/adonet/connecting-to-a-data-source).</span></span>

2. <span data-ttu-id="3a03e-108">在 Visual Studio 中，选择窗体上的控件并显示 " **属性** " 窗口。</span><span class="sxs-lookup"><span data-stu-id="3a03e-108">In Visual Studio, select the control on the form and display the **Properties** window.</span></span>

3. <span data-ttu-id="3a03e-109">展开 " **(databinding)** " 属性。</span><span class="sxs-lookup"><span data-stu-id="3a03e-109">Expand the **(DataBindings)** property.</span></span>

     <span data-ttu-id="3a03e-110">最常绑定的属性将显示在 **(databinding)** 属性下。</span><span class="sxs-lookup"><span data-stu-id="3a03e-110">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="3a03e-111">例如，在大多数控件中， **Text** 属性是最常绑定的。</span><span class="sxs-lookup"><span data-stu-id="3a03e-111">For example, in most controls, the **Text** property is most frequently bound.</span></span>

4. <span data-ttu-id="3a03e-112">如果要绑定的属性不是某个常用的绑定属性，请单击 **省略号** 按钮 (![ Visual Studio 属性窗口中的省略号按钮 ( ... ) 。 ](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) 在 " **(高级)** " 框中显示 " **格式设置和高级绑定** " 对话框，其中包含该控件的属性的完整列表。</span><span class="sxs-lookup"><span data-stu-id="3a03e-112">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>

5. <span data-ttu-id="3a03e-113">选择要绑定的属性，然后单击 " **绑定**" 下的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="3a03e-113">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>

     <span data-ttu-id="3a03e-114">此时将显示可用数据源的列表。</span><span class="sxs-lookup"><span data-stu-id="3a03e-114">A list of available data sources is displayed.</span></span>

6. <span data-ttu-id="3a03e-115">展开要绑定到的数据源，直到找到所需的单个数据元素。</span><span class="sxs-lookup"><span data-stu-id="3a03e-115">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="3a03e-116">例如，如果你正在绑定到数据集表中的列值，请展开该数据集的名称，然后展开表名以显示列名。</span><span class="sxs-lookup"><span data-stu-id="3a03e-116">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

7. <span data-ttu-id="3a03e-117">单击要绑定到的元素的名称。</span><span class="sxs-lookup"><span data-stu-id="3a03e-117">Click the name of an element to bind to.</span></span>

8. <span data-ttu-id="3a03e-118">如果使用的是 " **格式设置和高级绑定** " 对话框，请单击 **"确定"** 以返回到 " **属性** " 窗口。</span><span class="sxs-lookup"><span data-stu-id="3a03e-118">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>

9. <span data-ttu-id="3a03e-119">如果要绑定控件的其他属性，请重复步骤3到步骤7。</span><span class="sxs-lookup"><span data-stu-id="3a03e-119">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a03e-120">由于简单绑定控件只显示单个数据元素，因此在 Windows 窗体中包含具有简单绑定控件的导航逻辑非常典型。</span><span class="sxs-lookup"><span data-stu-id="3a03e-120">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a03e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a03e-121">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="3a03e-122">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="3a03e-122">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="3a03e-123">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="3a03e-123">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
