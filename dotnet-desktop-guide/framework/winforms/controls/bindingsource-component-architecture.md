---
title: BindingSource 组件体系结构
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: 54a23ba899ceb05701fe3580aefbb723c6b3f0fd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970718"
---
# <a name="bindingsource-component-architecture"></a>BindingSource 组件体系结构
通过 <xref:System.Windows.Forms.BindingSource> 组件，可以将所有 Windows 窗体控件全局绑定到数据源。  
  
 该 <xref:System.Windows.Forms.BindingSource> 组件简化了将控件绑定到数据源的过程，并且比传统的数据绑定具有以下优势：  
  
- 启用到业务对象的设计时绑定。  
  
- 封装 <xref:System.Windows.Forms.CurrencyManager> 功能，并 <xref:System.Windows.Forms.CurrencyManager> 在设计时公开事件。  
  
- <xref:System.ComponentModel.IBindingList>通过提供对不以本机方式支持列表更改通知的数据源的列表更改通知，简化了创建支持该接口的列表的操作。  
  
- 为方法提供一个扩展点 <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> 。  
  
- 提供数据源和控件之间的间接级别。 当数据源在运行时可能更改时，此间接寻址非常重要。  
  
- 与其他与数据相关的 Windows 窗体控件（特别是 <xref:System.Windows.Forms.BindingNavigator> 和控件）互操作 <xref:System.Windows.Forms.DataGridView> 。  
  
 由于这些原因， <xref:System.Windows.Forms.BindingSource> 组件是将 Windows 窗体控件绑定到数据源的首选方法。  
  
## <a name="bindingsource-features"></a>BindingSource 功能  
 <xref:System.Windows.Forms.BindingSource>组件提供多种功能用于将控件绑定到数据。 利用这些功能，你可以实现大多数数据绑定方案，几乎不会对你的部分进行编码。  
  
 <xref:System.Windows.Forms.BindingSource>组件通过提供用于访问多种不同类型的数据源的一致界面来实现这一点。 这意味着，可以使用相同的过程来绑定到任何类型。 例如，可以将 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 属性附加到 <xref:System.Data.DataSet> 或业务对象，在这两种情况下，可以使用相同的一组属性、方法和事件来操作数据源。  
  
 组件提供的一致接口 <xref:System.Windows.Forms.BindingSource> 极大地简化了将数据绑定到控件的过程。 对于提供更改通知的数据源类型，该 <xref:System.Windows.Forms.BindingSource> 组件会自动传达控件和数据源之间的更改。 对于不提供更改通知的数据源类型，将提供事件，使你能够引发更改通知。 以下列表显示了该组件支持的功能 <xref:System.Windows.Forms.BindingSource> ：  
  
- 二级.  
  
- 货币管理。  
  
- 作为列表的数据源。  
  
- <xref:System.Windows.Forms.BindingSource> 用作 <xref:System.ComponentModel.IBindingList> 。  
  
- 自定义项创建。  
  
- 事务性项创建。  
  
- <xref:System.Collections.IEnumerable> 支持.  
  
- 设计时支持。  
  
- 静态 <xref:System.Windows.Forms.ListBindingHelper> 方法。  
  
- 用接口进行排序和筛选 <xref:System.ComponentModel.IBindingListView> 。  
  
- 与集成 <xref:System.Windows.Forms.BindingNavigator> 。  
  
### <a name="indirection"></a>间接寻址  
 <xref:System.Windows.Forms.BindingSource>组件提供控件和数据源之间的间接级别。 将控件绑定到数据源，而不是直接将控件绑定到数据源， <xref:System.Windows.Forms.BindingSource> 并将数据源附加到 <xref:System.Windows.Forms.BindingSource> 组件的 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 属性。  
  
 通过此级别的间接寻址，你可以更改数据源，而无需重置控件绑定。 这为你提供了以下功能：  
  
- 您可以附加 <xref:System.Windows.Forms.BindingSource> 到不同的数据源，同时保留当前控件绑定。  
  
- 您可以更改数据源中的项和通知绑定控件。 有关详细信息，请参阅 [如何：使用 BindingSource 在 Windows 窗体控件中反映数据源更新](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)。  
  
- 可以 <xref:System.Type> 在内存中绑定到而不是对象。 有关详细信息，请参阅 [如何：将 Windows 窗体控件绑定到类型](how-to-bind-a-windows-forms-control-to-a-type.md)。 然后，你可以在运行时绑定到对象。  
  
### <a name="currency-management"></a>货币管理  
 <xref:System.Windows.Forms.BindingSource>组件实现 <xref:System.Windows.Forms.ICurrencyManagerProvider> 接口以处理货币管理。 使用 <xref:System.Windows.Forms.ICurrencyManagerProvider> 接口，还可以访问的的 " <xref:System.Windows.Forms.BindingSource> 除" 之外的其他绑定到 "其他" 的 "货币经理" <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.DataMember%2A> 。  
  
 <xref:System.Windows.Forms.BindingSource>组件封装 <xref:System.Windows.Forms.CurrencyManager> 功能并公开最常见的 <xref:System.Windows.Forms.CurrencyManager> 属性和事件。 下表描述了与货币管理相关的一些成员。  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> 属性  
 获取与关联的货币管理器 <xref:System.Windows.Forms.BindingSource> 。  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A> 方法  
 如果有另一个 <xref:System.Windows.Forms.BindingSource> 绑定到指定的数据成员，则获取其 "货币经理"。  
  
 <xref:System.Windows.Forms.BindingSource.Current%2A> 属性  
 获取数据源的当前项。  
  
 <xref:System.Windows.Forms.BindingSource.Position%2A> 属性  
 获取或设置基础列表中的当前位置。  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 方法  
 将挂起的更改应用于基础数据源。  
  
 <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> 方法  
 取消当前的编辑操作。  
  
### <a name="data-source-as-a-list"></a>作为列表的数据源  
 <xref:System.Windows.Forms.BindingSource>组件实现 <xref:System.ComponentModel.IBindingListView> 和 <xref:System.ComponentModel.ITypedList> 接口。 使用此实现，你可以使用 <xref:System.Windows.Forms.BindingSource> 组件本身作为数据源，而无需任何外部存储。  
  
 当 <xref:System.Windows.Forms.BindingSource> 组件附加到数据源时，它会将数据源作为列表公开。  
  
 <xref:System.Windows.Forms.BindingSource.DataSource%2A>属性可设置为多个数据源。 其中包括类型、对象和类型列表。 生成的数据源将作为列表公开。 下表显示了一些常用数据源和生成的列表计算。  
  
|DataSource 属性|列出结果|  
|-------------------------|------------------|  
|空引用（在 Visual Basic 中为 `Nothing`）|对象的空 <xref:System.ComponentModel.IBindingList> 。 添加项会将列表设置为所添加项的类型。|  
|`Nothing`具有 set 的 Visual Basic) 中 (空 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 引用|不受支持;引发 <xref:System.ArgumentException> 。|  
|"T" 类型的非列表类型或对象|类型为 <xref:System.ComponentModel.IBindingList> "T" 的空。|  
|数组实例|一个 <xref:System.ComponentModel.IBindingList> 包含数组元素的。|  
|<xref:System.Collections.IEnumerable> 实例|一个 <xref:System.ComponentModel.IBindingList> 包含 <xref:System.Collections.IEnumerable> 项的|  
|包含类型 "T" 的列表实例|一个 <xref:System.ComponentModel.IBindingList> 包含类型 "T" 的实例。|  
  
 此外，还 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 可以设置为其他列表类型（例如 <xref:System.ComponentModel.IListSource> 和）， <xref:System.ComponentModel.ITypedList> 并且 <xref:System.Windows.Forms.BindingSource> 会相应地处理它们。 在这种情况下，列表中包含的类型应具有一个无参数的构造函数。  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource 作为 IBindingList  
 <xref:System.Windows.Forms.BindingSource>组件提供用于访问基础数据并将其操作为的成员 <xref:System.ComponentModel.IBindingList> 。 下表对其中一些成员进行了说明。  
  
|成员|描述|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.List%2A> 属性|获取或属性的计算结果的列表 <xref:System.Windows.Forms.BindingSource.DataSource%2A> <xref:System.Windows.Forms.BindingSource.DataMember%2A> 。|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A> 方法|在基础列表中添加一个新项。 适用于实现 <xref:System.ComponentModel.IBindingList> 接口并允许添加项的数据源 (即， <xref:System.Windows.Forms.BindingSource.AllowNew%2A> 属性设置为 `true`) 。|  
  
### <a name="custom-item-creation"></a>自定义项创建  
 您可以处理 <xref:System.Windows.Forms.BindingSource.AddingNew> 事件以提供您自己的项创建逻辑。 <xref:System.Windows.Forms.BindingSource.AddingNew>事件发生在将新对象添加到之前 <xref:System.Windows.Forms.BindingSource> 。 <xref:System.Windows.Forms.BindingSource.AddNew%2A>调用方法后，但在将新项添加到基础列表之前，将引发此事件。 通过处理此事件，你可以提供自定义项创建行为，而无需从 <xref:System.Windows.Forms.BindingSource> 类派生。 有关详细信息，请参阅 [如何：自定义带有 Windows 窗体 BindingSource 的项添加操作](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)。  
  
### <a name="transactional-item-creation"></a>事务项创建  
 <xref:System.Windows.Forms.BindingSource>组件实现了 <xref:System.ComponentModel.ICancelAddNew> 接口，该接口启用事务项创建。 使用调用暂时创建新项后 <xref:System.Windows.Forms.BindingSource.AddNew%2A> ，可以通过以下方式提交或回滚添加操作：  
  
- <xref:System.ComponentModel.ICancelAddNew.EndNew%2A>方法将显式提交挂起的添加。  
  
- 执行其他集合操作（如插入、删除或移动）将隐式提交挂起的添加操作。  
  
- <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>如果尚未提交方法，则方法将回滚挂起的添加。  
  
### <a name="ienumerable-support"></a>IEnumerable 支持  
 <xref:System.Windows.Forms.BindingSource>组件启用将控件绑定到 <xref:System.Collections.IEnumerable> 数据源。 使用此组件，可以绑定到数据源，例如 <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType> 。  
  
 将 <xref:System.Collections.IEnumerable> 数据源分配给 <xref:System.Windows.Forms.BindingSource> 组件时，会 <xref:System.Windows.Forms.BindingSource> 创建一个 <xref:System.ComponentModel.IBindingList> ，并将数据源的内容添加 <xref:System.Collections.IEnumerable> 到列表。  
  
### <a name="design-time-support"></a>Design-Time 支持  
 某些对象类型无法在设计时创建，例如从工厂类创建的对象，或 Web 服务返回的对象。 有时，你可能需要在设计时将控件绑定到这些类型，即使控件可以绑定到的内存中没有对象。 例如，你可能需要 <xref:System.Windows.Forms.DataGridView> 使用自定义类型的公共属性的名称来标记控件的列标题。  
  
 若要支持此方案， <xref:System.Windows.Forms.BindingSource> 组件支持绑定到 <xref:System.Type> 。 将分配 <xref:System.Type> 到 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 属性时， <xref:System.Windows.Forms.BindingSource> 组件会创建一个空 <xref:System.ComponentModel.BindingList%601> 的 <xref:System.Type> 项。 以后绑定到组件的任何控件 <xref:System.Windows.Forms.BindingSource> 将在设计时或运行时向你发出类型属性或架构的警报。 有关详细信息，请参阅 [如何：将 Windows 窗体控件绑定到类型](how-to-bind-a-windows-forms-control-to-a-type.md)。  
  
### <a name="static-listbindinghelper-methods"></a>静态 ListBindingHelper 方法  
 <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>、 <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.BindingSource> 类型都共享公共逻辑，以便从对中生成列表 `DataSource` / `DataMember` 。 此外，在以下方法中，将公开此公共逻辑以供控件作者和其他第三方使用 `static` ：  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>通过 IBindingListView 接口进行排序和筛选  
 <xref:System.Windows.Forms.BindingSource>组件实现 <xref:System.ComponentModel.IBindingListView> 接口，该接口用于扩展 <xref:System.ComponentModel.IBindingList> 接口。 <xref:System.ComponentModel.IBindingList>提供单个列排序，并 <xref:System.ComponentModel.IBindingListView> 提供高级排序和筛选功能。 对于 <xref:System.ComponentModel.IBindingListView> ，如果数据源还实现其中一个接口，则可以对数据源中的项进行排序和筛选。 该 <xref:System.Windows.Forms.BindingSource> 组件不提供这些成员的引用实现。 而是将调用转发到基础列表。  
  
 下表描述了用于排序和筛选的属性。  
  
|成员|描述|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A> 属性|如果数据源是 <xref:System.ComponentModel.IBindingListView>，则获取或设置用于筛选已查看的行的表达式。|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A> 属性|如果数据源是 <xref:System.ComponentModel.IBindingList>，则获取或设置用于排序的列名称并对顺序信息进行排序。<br /><br /> -或-<br /><br /> 如果数据源是 <xref:System.ComponentModel.IBindingListView> 并支持高级排序，则获取用于排序和排序顺序的多个列名|  
  
### <a name="integration-with-bindingnavigator"></a>与 BindingNavigator 集成  
 您可以使用该 <xref:System.Windows.Forms.BindingSource> 组件将任何 Windows 窗体控件绑定到数据源，但该 <xref:System.Windows.Forms.BindingNavigator> 控件专门设计用于处理该 <xref:System.Windows.Forms.BindingSource> 组件。 <xref:System.Windows.Forms.BindingNavigator>控件提供用于控制 <xref:System.Windows.Forms.BindingSource> 组件当前项的用户界面。 默认情况下， <xref:System.Windows.Forms.BindingNavigator> 控件提供与组件上的导航方法相对应的按钮 <xref:System.Windows.Forms.BindingSource> 。 有关详细信息，请参阅 [如何：用 Windows 窗体 BindingNavigator 控件浏览数据](how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [BindingSource 组件概述](bindingsource-component-overview.md)
- [BindingNavigator 控件](bindingnavigator-control-windows-forms.md)
- [Windows 窗体数据绑定](../windows-forms-data-binding.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
- [如何：将 Windows 窗体控件绑定到类型](how-to-bind-a-windows-forms-control-to-a-type.md)
- [如何：使用 BindingSource 在 Windows 窗体控件中反映数据源更新](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
