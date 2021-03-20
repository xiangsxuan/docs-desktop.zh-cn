---
title: 如何：在单击标题时对 GridView 列进行排序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], GridView
- controls [WPF], ListView
- ListView controls [WPF], sorting GridView columns
- GridView controls [WPF], ListView control
ms.assetid: 4865d720-d147-40ed-83a7-af7587f8aad8
ms.openlocfilehash: 0cea786afb6e99151b79f2c620919031d23ef0f0
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668131"
---
# <a name="how-to-sort-a-gridview-column-when-a-header-is-clicked"></a><span data-ttu-id="ba0b8-102">如何：在单击标题时对 GridView 列进行排序</span><span class="sxs-lookup"><span data-stu-id="ba0b8-102">How to: Sort a GridView Column When a Header Is Clicked</span></span>

<span data-ttu-id="ba0b8-103">此示例演示如何创建一个 <xref:System.Windows.Controls.ListView> 实现视图模式的控件 <xref:System.Windows.Controls.GridView> ，并在用户单击列标题时对数据内容进行排序。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-103">This example shows how to create a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView> view mode and sorts the data content when a user clicks a column header.</span></span>

## <a name="example"></a><span data-ttu-id="ba0b8-104">示例</span><span class="sxs-lookup"><span data-stu-id="ba0b8-104">Example</span></span>

<span data-ttu-id="ba0b8-105">下面的示例定义了 <xref:System.Windows.Controls.GridView> 包含三列的，这些列绑定到 <xref:System.DateTime.Year%2A> 结构的、 <xref:System.DateTime.Month%2A> 、和 <xref:System.DateTime.Day%2A> 属性 <xref:System.DateTime> 。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-105">The following example defines a <xref:System.Windows.Controls.GridView> with three columns that bind to the <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, and <xref:System.DateTime.Day%2A>, properties of the <xref:System.DateTime> structure.</span></span>

```xaml
<GridView>
  <GridViewColumn DisplayMemberBinding="{Binding Path=Year}"
                  Header="Year"
                  Width="100"/>
  <GridViewColumn DisplayMemberBinding="{Binding Path=Month}"
                  Header="Month"
                  Width="100"/>
  <GridViewColumn DisplayMemberBinding="{Binding Path=Day}"
                  Header="Day"
                  Width="100"/>
</GridView>
```

<span data-ttu-id="ba0b8-106">下面的示例显示了定义为 <xref:System.Collections.ArrayList> 对象的的数据项 <xref:System.DateTime> 。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-106">The following example shows the data items that are defined as an <xref:System.Collections.ArrayList> of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="ba0b8-107"><xref:System.Collections.ArrayList>定义为 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 控件的 <xref:System.Windows.Controls.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-107">The <xref:System.Collections.ArrayList> is defined as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> control.</span></span>

```xaml
<ListView.ItemsSource>
  <s:ArrayList>
    <p:DateTime>1993/1/1 12:22:02</p:DateTime>
    <p:DateTime>1993/1/2 13:2:01</p:DateTime>
    <p:DateTime>1997/1/3 2:1:6</p:DateTime>
    <p:DateTime>1997/1/4 13:6:55</p:DateTime>
    <p:DateTime>1999/2/1 12:22:02</p:DateTime>
    <p:DateTime>1998/2/2 13:2:01</p:DateTime>
    <p:DateTime>2000/2/3 2:1:6</p:DateTime>
    <p:DateTime>2002/2/4 13:6:55</p:DateTime>
    <p:DateTime>2001/3/1 12:22:02</p:DateTime>
    <p:DateTime>2006/3/2 13:2:01</p:DateTime>
    <p:DateTime>2004/3/3 2:1:6</p:DateTime>
    <p:DateTime>2004/3/4 13:6:55</p:DateTime>
  </s:ArrayList>
</ListView.ItemsSource>
```

<span data-ttu-id="ba0b8-108">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 标记中的 `s` 和 `p` 标识符引用在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页面元数据中定义的命名空间映射。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-108">The `s` and `p` identifiers in the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tags refer to namespace mappings that are defined in the metadata of the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="ba0b8-109">下面的示例显示了元数据定义。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-109">The following example shows the metadata definition.</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="ListViewSort.Window1"
    xmlns:s="clr-namespace:System.Collections;assembly=mscorlib"
    xmlns:p="clr-namespace:System;assembly=mscorlib">
```

<span data-ttu-id="ba0b8-110">若要根据列的内容对数据进行排序，此示例定义了一个事件处理程序，用于处理 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 按下列标题按钮时发生的事件。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-110">To sort the data according to the contents of a column, the example defines an event handler to handle the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event that occurs when you press the column header button.</span></span> <span data-ttu-id="ba0b8-111">下面的示例演示如何为控件指定事件处理程序 <xref:System.Windows.Controls.GridViewColumnHeader> 。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-111">The following example shows how to specify an event handler for the <xref:System.Windows.Controls.GridViewColumnHeader> control.</span></span>

```xaml
<ListView x:Name='lv' Height="150" HorizontalAlignment="Center"
  VerticalAlignment="Center"
  GridViewColumnHeader.Click="GridViewColumnHeaderClickedHandler"
 >
```

<span data-ttu-id="ba0b8-112">该示例定义了事件处理程序，以便每次按下列标题按钮时，排序方向会在升序和降序之间发生变化。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-112">The example defines the event handler so that the sort direction changes between ascending order and descending order each time you press the column header button.</span></span> <span data-ttu-id="ba0b8-113">下面的示例显示了事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-113">The following example shows the event handler.</span></span>

```csharp
public partial class Window1 : Window
{
    public Window1()
    {
        InitializeComponent();
    }

    GridViewColumnHeader _lastHeaderClicked = null;
    ListSortDirection _lastDirection = ListSortDirection.Ascending;

    void GridViewColumnHeaderClickedHandler(object sender,
                                            RoutedEventArgs e)
    {
        var headerClicked = e.OriginalSource as GridViewColumnHeader;
        ListSortDirection direction;

        if (headerClicked != null)
        {
            if (headerClicked.Role != GridViewColumnHeaderRole.Padding)
            {
                if (headerClicked != _lastHeaderClicked)
                {
                    direction = ListSortDirection.Ascending;
                }
                else
                {
                    if (_lastDirection == ListSortDirection.Ascending)
                    {
                        direction = ListSortDirection.Descending;
                    }
                    else
                    {
                        direction = ListSortDirection.Ascending;
                    }
                }

                var columnBinding = headerClicked.Column.DisplayMemberBinding as Binding;
                var sortBy = columnBinding?.Path.Path ?? headerClicked.Column.Header as string;

                Sort(sortBy, direction);

                if (direction == ListSortDirection.Ascending)
                {
                    headerClicked.Column.HeaderTemplate =
                      Resources["HeaderTemplateArrowUp"] as DataTemplate;
                }
                else
                {
                    headerClicked.Column.HeaderTemplate =
                      Resources["HeaderTemplateArrowDown"] as DataTemplate;
                }

                // Remove arrow from previously sorted header
                if (_lastHeaderClicked != null && _lastHeaderClicked != headerClicked)
                {
                    _lastHeaderClicked.Column.HeaderTemplate = null;
                }

                _lastHeaderClicked = headerClicked;
                _lastDirection = direction;
            }
        }
    }
}
```

```vb
Partial Public Class Window1
    Inherits Window
    Public Sub New()
        InitializeComponent()
    End Sub

    Private _lastHeaderClicked As GridViewColumnHeader = Nothing
    Private _lastDirection As ListSortDirection = ListSortDirection.Ascending

    Private Sub GridViewColumnHeaderClickedHandler(ByVal sender As Object, ByVal e As RoutedEventArgs)
        Dim headerClicked = TryCast(e.OriginalSource, GridViewColumnHeader)
        Dim direction As ListSortDirection

        If headerClicked IsNot Nothing Then
            If headerClicked.Role <> GridViewColumnHeaderRole.Padding Then
                If headerClicked IsNot _lastHeaderClicked Then
                    direction = ListSortDirection.Ascending
                Else
                    If _lastDirection = ListSortDirection.Ascending Then
                        direction = ListSortDirection.Descending
                    Else
                        direction = ListSortDirection.Ascending
                    End If
                End If

                Dim columnBinding = TryCast(headerClicked.Column.DisplayMemberBinding, Binding)
                Dim sortBy = If(columnBinding?.Path.Path, TryCast(headerClicked.Column.Header, String))

                Sort(sortBy, direction)

                If direction = ListSortDirection.Ascending Then
                    headerClicked.Column.HeaderTemplate = TryCast(Resources("HeaderTemplateArrowUp"), DataTemplate)
                Else
                    headerClicked.Column.HeaderTemplate = TryCast(Resources("HeaderTemplateArrowDown"), DataTemplate)
                End If

                ' Remove arrow from previously sorted header
                If _lastHeaderClicked IsNot Nothing AndAlso _lastHeaderClicked IsNot headerClicked Then
                    _lastHeaderClicked.Column.HeaderTemplate = Nothing
                End If

                _lastHeaderClicked = headerClicked
                _lastDirection = direction
            End If
        End If
    End Sub
End Class
```

<span data-ttu-id="ba0b8-114">下面的示例演示由事件处理程序调用以供对数据进行排序的排序算法。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-114">The following example shows the sorting algorithm that is called by the event handler to sort the data.</span></span> <span data-ttu-id="ba0b8-115">排序是通过创建新结构来执行的 <xref:System.ComponentModel.SortDescription> 。</span><span class="sxs-lookup"><span data-stu-id="ba0b8-115">The sort is performed by creating a new <xref:System.ComponentModel.SortDescription> structure.</span></span>

```csharp
private void Sort(string sortBy, ListSortDirection direction)
{
    ICollectionView dataView =
      CollectionViewSource.GetDefaultView(lv.ItemsSource);

    dataView.SortDescriptions.Clear();
    SortDescription sd = new SortDescription(sortBy, direction);
    dataView.SortDescriptions.Add(sd);
    dataView.Refresh();
}
```

```vb
Private Sub Sort(ByVal sortBy As String, ByVal direction As ListSortDirection)
    Dim dataView As ICollectionView = CollectionViewSource.GetDefaultView(lv.ItemsSource)

    dataView.SortDescriptions.Clear()
    Dim sd As New SortDescription(sortBy, direction)
    dataView.SortDescriptions.Add(sd)
    dataView.Refresh()
End Sub
```

## <a name="see-also"></a><span data-ttu-id="ba0b8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba0b8-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="ba0b8-117">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="ba0b8-117">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="ba0b8-118">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="ba0b8-118">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="ba0b8-119">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="ba0b8-119">How-to Topics</span></span>](listview-how-to-topics.md)
