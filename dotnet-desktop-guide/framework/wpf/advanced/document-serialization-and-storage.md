---
title: 文档序列化和存储
ms.date: 03/30/2017
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
ms.openlocfilehash: 6703825d4453b2e0e65036fa2d9c856139ee473c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973104"
---
# <a name="document-serialization-and-storage"></a>文档序列化和存储

Microsoft .NET Framework 提供了一个功能强大的环境，用于创建和显示高质量的文档。  支持固定文档和流文档、高级查看控件、与强大的2D 和3D 图形功能结合使用的增强功能将 .NET Framework 应用程序提升到新的质量和用户体验。  能够灵活地管理文档的内存中表示形式是 .NET Framework 的一项重要功能，能够有效保存和加载数据存储中的文档几乎每个应用程序都需要。  将文档从内部的内存中表示形式转换为外部数据存储的过程称为序列化。  反之，读取数据存储并重新创建原始内存中实例的过程则称为反序列化。

<a name="AboutSerialization"></a>

## <a name="about-document-serialization"></a>关于文档序列化

理论上，对于应用程序来说，从内存中序列化文档和将文档反序列到原来的内存中都是透明的。  应用程序调用序列化程序“write”方法来保存文档，而反序列化程序“read”方法则访问数据存储并在内存中重新创建原始实例。  对于应用程序来说，只要序列化和反序列化进程将文档重新创建为其原始格式，数据存储的特定格式通常无关紧要。

应用程序通常提供多个序列化选项，用户可以使用这些选项将文档保存到不同的介质或保存为不同格式。  例如，应用程序可提供“另存为”选项将文档存储到磁盘文件、数据库或 Web 服务。  同样，不同的序列化程序可将文档存储为不同的格式，例如 HTML、RTF、XML、XPS 或第三方格式。  对于应用程序，序列化定义了一个接口，该接口可以隔离每个特定序列化程序的实现内部的存储介质的详细信息。  除了封装存储详细信息的优势外，.NET Framework api 还 <xref:System.Windows.Documents.Serialization> 提供了其他几项重要功能。

### <a name="features-of-net-framework-30-document-serializers"></a>.NET Framework 3.0 文档序列化程序的功能

- 通过直接访问高级别文档对象（逻辑树和视觉对象），可以有效存储已分页的内容、二维/三维元素、图像、媒体、超链接、注释以及其他支持内容。

- 同步和异步操作。

- 支持具有以下增强功能的插件序列化程序：

  - 供所有 .NET Framework 应用程序使用的系统范围的访问。

  - 简单应用程序插件的发现功能。

  - 第三方自定义插件的简单部署、安装和更新。

  - 对自定义运行时设置和选项的用户界面支持。

### <a name="xps-print-path"></a>XPS 打印路径

Microsoft .NET Framework XPS 打印路径还提供了一种可扩展的机制，用于通过打印输出来写入文档。  XPS 既作为文档文件格式，也用作 Windows Vista 的本机打印后台处理格式。  XPS 文档可以直接发送到与 XPS 兼容的打印机，而无需转换为中间格式。  有关打印路径输出选项和功能的其他信息，请参阅[打印概述](printing-overview.md)。

<a name="PluginSerializers"></a>

## <a name="plug-in-serializers"></a>插件序列化程序

<xref:System.Windows.Documents.Serialization>Api 为插件序列化程序和链接的序列化程序提供支持，这些插件序列化程序与应用程序分开安装，在运行时绑定，并使用 <xref:System.Windows.Documents.Serialization.SerializerProvider> 发现机制进行访问。  插件序列化程序提供增强功能，可以简化部署和系统范围的使用。  还可以为部分信任环境（如 XAML 浏览器应用程序）实现链接的序列化程序， (Xbap) ，其中插件序列化程序不可访问。  基于类的派生实现的链接序列化 <xref:System.Windows.Documents.Serialization.SerializerWriter> 程序将被编译并直接链接到应用程序中。  插件序列化程序和链接序列化程序都是通过相同的公共方法和事件来运行的，这样可以方便地在同一应用程序中使用其中一种或两种序列化程序。

插件序列化程序对应用程序开发人员很有帮助：它向新的存储设计和文件格式提供扩展性，而无需在生成时对每种潜在的格式进行直接编码。  插件序列化程序还通过为自定义或专有文件格式提供部署、安装和更新系统可访问插件的标准方法，使第三方开发人员受益匪浅。

### <a name="using-a-plug-in-serializer"></a>使用插件序列化程序

插件序列化程序易于使用。  <xref:System.Windows.Documents.Serialization.SerializerProvider>类枚举 <xref:System.Windows.Documents.Serialization.SerializerDescriptor> 系统上安装的每个插件的对象。  <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A>属性根据当前配置筛选已安装的插件，并验证应用程序是否可以加载和使用序列化程序。  <xref:System.Windows.Documents.Serialization.SerializerDescriptor>还提供了其他属性（例如 <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> 和 <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A> ），应用程序可以使用这些属性来提示用户选择可用输出格式的序列化程序。  用于 XPS 的默认插件序列化程序随 .NET Framework 提供，并始终枚举。  用户选择输出格式后，将 <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> 使用方法来创建 <xref:System.Windows.Documents.Serialization.SerializerWriter> 特定格式的。  <xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A?displayProperty=nameWithType>然后，可以调用方法将文档流输出到数据存储区。

下面的示例演示了 <xref:System.Windows.Documents.Serialization.SerializerProvider> 在 "PlugInFileFilter" 属性中使用方法的应用程序。  PlugInFileFilter 枚举安装的插件，并使用的可用文件选项生成筛选器字符串 <xref:Microsoft.Win32.SaveFileDialog> 。

[!code-csharp[DocumentSerialize#DocSerializeFileFilter](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]

用户选择了输出文件名后，下面的示例演示 <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> 如何使用方法以指定的格式存储给定的文档。

[!code-csharp[DocumentSerialize#DocSerializePlugIn](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]

<a name="InstallingPluginSerializers"></a>

### <a name="installing-plug-in-serializers"></a>安装插件序列化程序

<xref:System.Windows.Documents.Serialization.SerializerProvider>类为插件序列化程序发现和访问提供高级应用程序接口。  <xref:System.Windows.Documents.Serialization.SerializerProvider> 查找并为应用程序提供系统上已安装并可访问的序列化程序的列表。  已安装序列化程序的具体信息通过注册表设置来定义。  插件序列化程序可以通过使用方法添加到注册表 <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A> ; 或者，如果尚未安装 .NET Framework，插件安装脚本可以直接设置注册表值本身。  此 <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> 方法可用于删除以前安装的插件，或与卸载脚本类似，可以重置注册表设置。

### <a name="creating-a-plug-in-serializer"></a>创建插件序列化程序

插件序列化程序和链接序列化程序使用同一公开的公共方法和事件，并且可同样设计为以同步或异步方式运行。  创建插件序列化程序通常应执行下列三个基本步骤：

1. 首先以链接序列化程序的形式实现和调试序列化程序。  开始时通过创建直接编译和链接到测试应用程序的序列化程序，可以提供对断点以及其他有助于测试的调试服务的完全访问权限。

2. 充分测试序列化程序后， <xref:System.Windows.Documents.Serialization.ISerializerFactory> 会添加一个接口用于创建插件。  <xref:System.Windows.Documents.Serialization.ISerializerFactory>接口允许对包括逻辑树、 <xref:System.Windows.UIElement> 对象、 <xref:System.Windows.Documents.IDocumentPaginatorSource> 和元素的所有 .NET Framework 对象进行完全访问 <xref:System.Windows.Media.Visual> 。  此外， <xref:System.Windows.Documents.Serialization.ISerializerFactory> 还提供了链接的序列化程序所使用的相同同步和异步方法和事件。  由于输出大型文档需要一定时间，因此推荐使用异步操作以维持响应用户交互，并在数据存储出现问题时提供“取消”选项。

3. 创建插件序列化程序之后，实现安装脚本以分发和安装（以及卸载）插件（请参阅上面的“[安装插件序列化程序](#InstallingPluginSerializers)”）。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Documents.Serialization>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- [WPF 中的文档](documents-in-wpf.md)
- [打印概述](printing-overview.md)
- [XML 纸张规范](https://www.ecma-international.org/activities/XML%20Paper%20Specification/XPS%20Standard%20WD%201.6.pdf)
