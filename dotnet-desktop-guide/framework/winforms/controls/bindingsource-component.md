---
title: BindingSource 组件
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970716"
---
# <a name="bindingsource-component"></a><span data-ttu-id="1c1e1-102">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="1c1e1-102">BindingSource Component</span></span>
<span data-ttu-id="1c1e1-103">封装数据源以绑定到控件。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="1c1e1-104"><xref:System.Windows.Forms.BindingSource> 组件有两个用途。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="1c1e1-105">首先，将一个窗体的控件绑定到数据时，该组件会提供一个间接层。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="1c1e1-106">这是通过将 <xref:System.Windows.Forms.BindingSource> 组件与你的数据源绑定，然后将窗体上的控件绑定到 <xref:System.Windows.Forms.BindingSource> 组件完成的。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="1c1e1-107">与数据的所有进一步交互（包括导航、排序、筛选和更新）都是通过调用 <xref:System.Windows.Forms.BindingSource> 组件来完成的。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="1c1e1-108">第二，<xref:System.Windows.Forms.BindingSource> 组件可以充当强类型的数据源。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="1c1e1-109">通过使用 <xref:System.Windows.Forms.BindingSource.Add%2A> 方法向 <xref:System.Windows.Forms.BindingSource> 组件添加一个类型来创建该类型的列表。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c1e1-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="1c1e1-110">In This Section</span></span>  
 [<span data-ttu-id="1c1e1-111">BindingSource 组件概述</span><span class="sxs-lookup"><span data-stu-id="1c1e1-111">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)  
 <span data-ttu-id="1c1e1-112">介绍 <xref:System.Windows.Forms.BindingSource> 组件的一般概念，这些概念使你能将数据源绑定到控件。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="1c1e1-113">如何：将 Windows 窗体控件绑定到 DBNull 数据库值</span><span class="sxs-lookup"><span data-stu-id="1c1e1-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="1c1e1-114">演示如何使用 <xref:System.Windows.Forms.BindingSource> 组件处理数据源的 <xref:System.DBNull>值。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="1c1e1-115">如何：使用 Windows 窗体 BindingSource 组件对 ADO.NET 数据进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="1c1e1-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="1c1e1-116">演示如何使用 <xref:System.Windows.Forms.BindingSource> 组件将排序和筛选应用到显示的数据上。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="1c1e1-117">如何：使用 Windows 窗体 BindingSource 绑定到 Web 服务</span><span class="sxs-lookup"><span data-stu-id="1c1e1-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="1c1e1-118">演示如何使用 <xref:System.Windows.Forms.BindingSource> 组件绑定到 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="1c1e1-119">如何：处理因数据绑定而发生的错误和异常</span><span class="sxs-lookup"><span data-stu-id="1c1e1-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="1c1e1-120">演示如何使用 <xref:System.Windows.Forms.BindingSource> 组件妥善处理数据在绑定操作中发生的错误。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="1c1e1-121">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="1c1e1-121">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="1c1e1-122">演示如何使用 <xref:System.Windows.Forms.BindingSource> 组件绑定到一种类型。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="1c1e1-123">如何：将 Windows 窗体控件绑定到 Factory 对象</span><span class="sxs-lookup"><span data-stu-id="1c1e1-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="1c1e1-124">演示如何使用 <xref:System.Windows.Forms.BindingSource> 组件绑定到 Factory 对象或方法。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="1c1e1-125">如何：使用 Windows 窗体 BindingSource 自定义项添加</span><span class="sxs-lookup"><span data-stu-id="1c1e1-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="1c1e1-126">演示如何使用 <xref:System.Windows.Forms.BindingSource> 组件创建新项并将它们添加到数据源。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="1c1e1-127">如何：使用 BindingSource ResetItem 方法引发更改通知</span><span class="sxs-lookup"><span data-stu-id="1c1e1-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="1c1e1-128">演示如何使用 <xref:System.Windows.Forms.BindingSource> 组件引发对不支持更改通知的数据源的更改通知事件。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="1c1e1-129">如何：使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知</span><span class="sxs-lookup"><span data-stu-id="1c1e1-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="1c1e1-130">演示如何将继承自 <xref:System.ComponentModel.INotifyPropertyChanged> 的类型用于 <xref:System.Windows.Forms.BindingSource> 控件。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="1c1e1-131">如何：使用 BindingSource 在 Windows 窗体控件中反映数据源更新</span><span class="sxs-lookup"><span data-stu-id="1c1e1-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="1c1e1-132">演示如何使用 <xref:System.Windows.Forms.BindingSource> 组件响应数据源中的更改。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="1c1e1-133">如何：使用 BindingSource 组件跨窗体共享绑定数据</span><span class="sxs-lookup"><span data-stu-id="1c1e1-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="1c1e1-134">演示如何使用 <xref:System.Windows.Forms.BindingSource> 将多个窗体绑定到相同的数据源。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1c1e1-135">参考</span><span class="sxs-lookup"><span data-stu-id="1c1e1-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="1c1e1-136">提供关于 <xref:System.Windows.Forms.BindingSource> 组件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="1c1e1-137">提供关于 <xref:System.Windows.Forms.BindingNavigator> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1c1e1-138">相关章节</span><span class="sxs-lookup"><span data-stu-id="1c1e1-138">Related Sections</span></span>  
 [<span data-ttu-id="1c1e1-139">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="1c1e1-139">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="1c1e1-140">包含描述 Windows 窗体数据绑定体系结构的主题链接。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="1c1e1-141">另请参阅[在 Visual Studio 中将控件绑定到数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="1c1e1-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
