---
title: XAML 安全注意事项
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: 1864910b339c74e3033fb4d6d8baebffada1a4f8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974076"
---
# <a name="xaml-security-considerations"></a>XAML 安全注意事项

本文介绍了使用 XAML 和 .NET XAML 服务 API 时，适用于应用程序安全的最佳做法。

## <a name="untrusted-xaml-in-applications"></a>应用程序中的不受信任 XAML

在最常见的意义上，不受信任的 XAML 是指应用程序未特别包含或发出的任何 XAML 源。

在 `resx` 受信任和签名的程序集中编译为或存储为类型资源的 XAML 本质上是不受信任的。 您可以信任 XAML，就像完全信任程序集一样。 在大多数情况下，只关注松散 XAML 的信任方面，它是从流或其他 i/o 加载的 XAML 源。 松散 XAML 不是具有部署和打包基础结构的应用程序模型的特定组件或功能。 但是，程序集可能实现涉及加载松散 XAML 的行为。

对于不受信任的 XAML，你应该将其视为不受信任的代码。 使用沙盒或其他形式来防止可能不受信任的 XAML 访问受信任的代码。

XAML 功能的性质为 XAML 提供构造对象并设置其属性的权限。 这些功能还包括访问类型转换器、映射和访问应用程序域中的程序集、使用标记扩展、 `x:Code` 块等。

除了其语言级功能，XAML 还用于许多技术中的 UI 定义。 加载不受信任的 XAML 可能意味着加载恶意欺骗 UI。

## <a name="sharing-context-between-readers-and-writers"></a>在读取器和编写器之间共享上下文

XAML 读取器和 XAML 编写器的 .NET XAML 服务体系结构通常需要将 XAML 读取器共享到 XAML 编写器或共享 XAML 架构上下文。 如果要编写 XAML 节点循环逻辑或提供自定义的保存路径，则可能需要共享对象或上下文。 不要在受信任和不受信任的代码之间共享 XAML 读取器实例、非默认 XAML 架构上下文或 XAML 读取器/编写器类的设置。

大多数情况和操作（涉及基于 CLR 的类型支持的 XAML 对象编写）只需使用默认的 XAML 架构上下文。 默认的 XAML 架构上下文未显式包含可能危及完全信任的设置。 因此，可以安全地在受信任和不受信任的 XAML 读取器/写入器组件之间共享上下文。 但是，如果您这样做，则最好是将此类读取器和编写器保留在不同的 <xref:System.AppDomain> 范围中，其中其中一项专门用于部分信任。

## <a name="xaml-namespaces-and-assembly-trust"></a>XAML 命名空间和程序集信任

XAML 将自定义 XAML 命名空间映射解释为程序集的基本非限定语法和定义，不区分被信任和不受信任的程序集加载到应用程序域中。 因此，不受信任的程序集有可能对受信任程序集的预期 XAML 命名空间映射进行欺骗，并捕获 XAML 源的已声明对象和属性信息。 如果你有安全要求以避免这种情况，应使用以下方法之一来进行预期的 XAML 命名空间映射：

- 在应用程序的 XAML 所进行的任何 XAML 命名空间映射中使用具有强名称的完全限定的程序集名称。

- 通过为 <xref:System.Xaml.XamlSchemaContext> xaml 读取器和 xaml 对象编写器构造特定的，限制程序集到一组固定的引用程序集的映射。 请参阅 <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>。

## <a name="xaml-type-mapping-and-type-system-access"></a>XAML 类型映射和类型系统访问

XAML 支持其自己的类型系统，它通过多种方式与 CLR 实现基本 CLR 类型系统的方式对等。 但是，对于根据类型信息对类型做出信任决策的类型感知方面的某些方面，应遵从 CLR 支持类型中的类型信息。 这是因为 XAML 类型系统的某些特定报告功能作为虚方法保持打开状态，因此不完全受原始 .NET XAML 服务实现的控制。 这些扩展点存在是因为 XAML 类型系统是可扩展的，以匹配 XAML 本身的扩展性及其可能的备用类型映射策略与默认的支持 CLR 的实现和默认 XAML 架构上下文。 有关详细信息，请参阅和的多个属性中的特定 <xref:System.Xaml.XamlType> 说明 <xref:System.Xaml.XamlMember> 。

## <a name="see-also"></a>另请参阅

- <xref:System.Xaml.Permissions.XamlAccessLevel>
