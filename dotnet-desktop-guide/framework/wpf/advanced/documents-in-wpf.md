---
title: 文档
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- documents [WPF], packaging
- documents [WPF], text layout
- documents [WPF], XPS
- 'XPS documents [WPF], , '
- documents [WPF], controls
- documents [WPF], types of
- documents [WPF], browser-viewable
ms.assetid: 6e8db7bc-050a-4070-aa72-bb8c46e87ff8
ms.openlocfilehash: 5791f799a13850dcd599d0ed4834964daa0664b2
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665557"
---
# <a name="documents-in-wpf"></a>WPF 中的文档
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供了一系列文档功能，使创建的高保真内容更易于访问和读取，而不是在以前的 Windows 版本中使用。 除增强功能和质量外，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 还对文档显示、打包和安全性能提供集成服务。 本主题介绍 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 文档类型和文档打包。  

<a name="types_of_documents"></a>
## <a name="types-of-documents"></a>文档类型  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 基于文档用途将文档分成两大类别；这些文档类别分别称为“固定文档”和“流文档”。  
  
 固定文档适用于需要精确的 "所见即所得内容" 的应用程序 (WYSIWYG) 表示形式，与所用的显示器或打印机硬件无关。 固定文档的典型用途包括桌面发布、字处理和窗体布局，在这些情况下，遵循原始页面设计非常关键。 作为其布局的一部分，固定文档独立于所使用的显示或打印设备来对内容元素进行精确地定位安放。 例如，一个固定文档页面在 96 dpi 显示器上显示的效果与在 600 dpi 激光打印机或 4800 dpi 照相排字机上输出的效果是完全一样的。 虽然文档质量会根据每台设备的功能达到最优化，但是页面布局在所有情况下都保持不变。  
  
 比较而言，流文档旨在优化查看和可读性，因此，当易读性是文档的主要使用要求时，最适合使用流文档。 流文档根据运行时变量（例如，窗口大小、设备分辨率和可选的用户首选项）来动态调整和重新排列内容，而不是设置为一个预定义的布局。 网页就是流文档的一个简单示例，网页上的页面内容会动态调整格式以适应当前窗口。 流文档会基于运行时环境来优化用户的查看和阅读体验。 例如，在高分辨率的 19 英寸显示器上或小型 2x3 英寸 PDA 屏幕上，同一流文档会动态调整格式以实现最佳可读性。 此外，流文档还具有很多内置功能，包括搜索、能够优化可读性的查看模式以及更改字体大小和外观的功能。  有关流文档的演示、示例和详细信息，请参阅[流文档概述](flow-document-overview.md)。  
  
<a name="document_viewer"></a>
## <a name="document-controls-and-text-layout"></a>文档控件和文本布局  
 .NET Framework 提供了一组预建的控件，这些控件可简化在应用程序中使用固定文档、流文档和常规文本。  使用控件支持显示固定文档内容 <xref:System.Windows.Controls.DocumentViewer> 。  流文档内容的显示由三个不同的控件支持： <xref:System.Windows.Controls.FlowDocumentReader> 、 <xref:System.Windows.Controls.FlowDocumentPageViewer> 和， <xref:System.Windows.Controls.FlowDocumentScrollViewer> 它们映射到不同的用户方案 (参阅下面) 的部分。  其他 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件提供简化的布局以支持常规文本使用（请参阅下面的[用户界面中的文本](#text_in_the_user_interface)）。  
  
### <a name="fixed-document-control---documentviewer"></a>固定文档控件 - DocumentViewer  
 <xref:System.Windows.Controls.DocumentViewer>控件设计用于显示 <xref:System.Windows.Documents.FixedDocument> 内容。 <xref:System.Windows.Controls.DocumentViewer>控件提供直观的用户界面，该界面为常见操作（包括打印输出、复制到剪贴板、缩放和文本搜索功能）提供内置支持。 此控件通过常见的滚动机制提供对页面内容的访问。 与所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件一样， <xref:System.Windows.Controls.DocumentViewer> 支持完整或部分 restyling，这使得控件能够直观地集成到几乎任何应用程序或环境中。  
  
 <xref:System.Windows.Controls.DocumentViewer> 旨在以只读方式显示内容;编辑或修改内容不可用，因此不受支持。  
  
<a name="flow_document"></a>
### <a name="flow-document-controls"></a>流文档概述  

> [!NOTE]
> 有关流文档功能以及如何创建它们的详细信息，请参阅 [流文档概述](flow-document-overview.md)。  
  
 流文档内容的显示由三个控件支持： <xref:System.Windows.Controls.FlowDocumentReader> 、 <xref:System.Windows.Controls.FlowDocumentPageViewer> 和 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 。  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> 包括使用户能够在各种查看模式之间进行动态选择的功能，包括单页 (一次) 查看模式、一次两页的 (书籍阅读格式) 查看模式和连续滚动 (查看模式的无限。  有关这些查看模式的详细信息，请参阅 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> 。  如果不需要在不同查看模式之间动态切换的功能， <xref:System.Windows.Controls.FlowDocumentPageViewer> 并提供了 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 在特定查看模式下固定的轻型流内容查看器。  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer 和 FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> 以一次一页的查看模式显示内容，同时以 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 连续滚动模式显示内容。  <xref:System.Windows.Controls.FlowDocumentPageViewer>和 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 都固定到特定的查看模式。 比较为 <xref:System.Windows.Controls.FlowDocumentReader> ，其中包括允许用户在枚举) 提供的各种查看模式 (之间进行动态选择的功能 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> ，成本比或更高 <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer> 。  
  
 默认情况下，总是显示垂直滚动条，而水平滚动条则在需要时显示。 的默认 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 值 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 不包含工具栏，但是， <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> 属性可用于启用内置工具栏。  
  
<a name="text_in_the_user_interface"></a>
### <a name="text-in-the-user-interface"></a>用户界面中的文本  
 除可将文本添加到文档外，文本显然还可以用于应用程序 UI（如窗体）中。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 包括多个用于在屏幕中绘制文本的控件。 每个控件都面向不同的方案，并具有自己的功能和限制列表。 通常， <xref:System.Windows.Controls.TextBlock> 当要求提供有限文本支持时，应使用元素，例如中的 brief 句子 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 。 <xref:System.Windows.Controls.Label> 需要最少文本支持时，可以使用。 有关详细信息，请参阅 [TextBlock 概述](../controls/textblock-overview.md)。  
  
<a name="packaging"></a>
## <a name="document-packaging"></a>文档打包  
 这些 <xref:System.IO.Packaging> api 提供了一种高效的方法，可将应用程序数据、文档内容和相关资源组织到一个易于访问、可移植且易于分发的容器中。 ZIP 文件是 <xref:System.IO.Packaging.Package> 能够将多个对象保存为单个单元的类型的示例。 打包 Api 提供了一个默认 <xref:System.IO.Packaging.ZipPackage> 实现，该实现使用开放式打包约定标准和 XML 和 ZIP 文件体系结构设计。 使用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 打包 api 可以轻松创建包，并可以存储和访问这些包中的对象。 存储在中的对象 <xref:System.IO.Packaging.Package> 称为 <xref:System.IO.Packaging.PackagePart> ( "part" ) 。 包还可包括已签名的数字证书，这些证书可用于标识部件的发信方以及验证包内容是否尚未修改。  包还包括一 <xref:System.IO.Packaging.PackageRelationship> 项功能，该功能允许将附加信息添加到包或与特定部分关联，而无需实际修改现有部件的内容。  包服务还支持 Microsoft Windows Rights Management (RM) 。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 包体系结构用作大量关键技术的基础：  
  
- XPS 文档符合 XML 纸张规范 (XPS) 。  
  
- Microsoft Office“12”开放式 XML 格式文档 (.docx)。  
  
- 用于个人应用程序设计的自定义存储格式。  
  
 基于打包 Api， <xref:System.Windows.Xps.Packaging.XpsDocument> 专为存储 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 固定内容文档而设计。 <xref:System.Windows.Xps.Packaging.XpsDocument>是自包含文档，可在查看器中打开、在控件中显示 <xref:System.Windows.Controls.DocumentViewer> 、路由到打印假脱机或直接输出到 XPS 兼容的打印机。  
  
 以下各节提供了有关随提供的和 api 的附加信息 <xref:System.IO.Packaging.Package> <xref:System.Windows.Xps.Packaging.XpsDocument> [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
<a name="packages"></a>
### <a name="package-components"></a>包组件  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 打包 API 允许将应用程序数据和文档组织成单个可移植单元。 ZIP 文件是最常见的包类型之一，并且是 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 附带的默认包类型。  <xref:System.IO.Packaging.Package> 本身是 <xref:System.IO.Packaging.ZipPackage> 使用开放标准 XML 和 ZIP 文件体系结构实现的抽象类。  <xref:System.IO.Packaging.Package.Open%2A>默认情况下，该方法使用 <xref:System.IO.Packaging.ZipPackage> 来创建和使用 ZIP 文件。 包可以包含三种基本类型的项：  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|应用程序内容、数据、文档和资源文件。|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[X.509 证书] 用于标识、身份验证和验证。|  
|<xref:System.IO.Packaging.PackageRelationship>|与包或特定部件相关的补充信息。|  
  
<a name="PackageParts"></a>
#### <a name="packageparts"></a>PackageParts  
 <xref:System.IO.Packaging.PackagePart> ( "part" ) 是一个抽象类，它引用存储在中的对象 <xref:System.IO.Packaging.Package> 。 在 ZIP 文件中，包的各个部件与存储在 ZIP 文件中的各个文件相对应。  <xref:System.IO.Packaging.ZipPackagePart> 为中存储的可序列化对象提供默认实现 <xref:System.IO.Packaging.ZipPackage> 。  与文件系统类似，包中包含的部件存储在分层目录或“文件夹样式”组织中。  使用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 打包 api，应用程序可以 <xref:System.IO.Packaging.PackagePart> 使用单个 ZIP 文件容器来编写、存储和读取多个对象。  
  
<a name="PackageDigitalSignatures"></a>
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignatures  
 为安全， <xref:System.IO.Packaging.PackageDigitalSignature> ( "数字签名" ) 可与包中的部件相关联。 <xref:System.IO.Packaging.PackageDigitalSignature>包含提供两个功能的 [509]：  
  
1. 标识部件的发信方并对其进行身份验证。  
  
2. 验证部件是否尚未被修改。  
  
 数字签名不会阻止修改部件，但如果该部件已经以任何方式发生改变，则对该数字签名的验证检查将失败。 然后应用程序可采取适当的操作（例如，阻止打开部件，或通知用户该部件已修改，是不安全的）。  
  
<a name="PackageRelationships"></a>
#### <a name="packagerelationships"></a>PackageRelationships  
 <xref:System.IO.Packaging.PackageRelationship> ( "relationship" ) 提供一种机制，用于将附加信息与包或包中的部件相关联。 关系是一种包级别的设备，可以在未修改实际部件内容的情况下将其他信息与部件关联。 在许多情况下，直接向部件内容中插入新数据通常是不可行的：  
  
- 部件及其内容架构的实际类型未知。  
  
- 即使已知，内容架构可能也不会提供添加新信息的方式。  
  
- 部件可能已进行数字签名或加密，不能进行任何修改。  
  
 包关系提供一种可检测到的方式，用于添加其他信息并将该信息与各个部件或整个包关联。 包关系具有两种主要功能：  
  
1. 定义一个部件与另一个部件之间的依赖关系。  
  
2. 定义添加注释或与部件相关的其他数据的信息关系。  
  
 <xref:System.IO.Packaging.PackageRelationship>提供了一种快速、可发现的方式来定义依赖项，并添加与包或包的一部分关联的其他信息。  
  
<a name="Dependency_Relationships"></a>
##### <a name="dependency-relationships"></a>依赖关系  
 依赖关系用于描述一个部件对其他部件的依赖性。 例如，包可能包含包含一个或多个图像标记的 HTML 部件 \<img> 。 此图像标记指的是作为包的其他内部部件或外部部件（可通过 Internet 访问）定位的图像。 创建 <xref:System.IO.Packaging.PackageRelationship> 与 HTML 文件关联的可快速轻松地发现和访问从属资源。 浏览器或查看器应用程序可以直接访问部件关系，并在无需了解架构或未分析文档的情况下立即开始汇编从属资源。  
  
<a name="Information_Relationships"></a>
##### <a name="information-relationships"></a>信息关系  
 与注释或批注类似， <xref:System.IO.Packaging.PackageRelationship> 还可以用于存储其他类型的信息以与部件关联，而无需实际修改部件内容本身。  
  
<a name="XPS_Documents"></a>
## <a name="xps-documents"></a>XPS 文档  
 XML 纸张规范 (XPS) 文档是一个包，其中包含一个或多个固定文档以及呈现所需的所有资源和信息。  XPS 也是本机 Windows Vista 打印假脱机文件格式。  <xref:System.Windows.Xps.Packaging.XpsDocument>存储在标准 ZIP 数据集中，并且可以包含 XML 和二进制组件（如图像和字体文件）的组合。 [PackageRelationships](#PackageRelationships) 用于定义内容和完全呈现文档所需的资源之间的依赖关系。  该 <xref:System.Windows.Xps.Packaging.XpsDocument> 设计提供支持多种用途的单个高保真文档解决方案：  
  
- 将固定文档内容和资源读取、写入和存储为单个可移植且易于分发的文件。  
  
- 显示包含 XPS 查看器应用程序的文档。  
  
- 以 Windows Vista 的本机打印后台输出格式输出文档。  
  
- 将文档直接路由到与 XPS 兼容的打印机。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Documents.FixedDocument>
- <xref:System.Windows.Documents.FlowDocument>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.IO.Packaging.ZipPackage>
- <xref:System.IO.Packaging.ZipPackagePart>
- <xref:System.IO.Packaging.PackageRelationship>
- <xref:System.Windows.Controls.DocumentViewer>
- [文本](optimizing-performance-text.md)
- [流文档概述](flow-document-overview.md)
- [打印概述](printing-overview.md)
- [文档序列化和存储](document-serialization-and-storage.md)
