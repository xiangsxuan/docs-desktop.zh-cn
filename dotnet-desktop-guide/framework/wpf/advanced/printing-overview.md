---
title: 打印概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print path [WPF], XPS
- printers [WPF], XPSDrv-based
- printing [WPF]
- PrintQueue class PrintServer class [WPF]
- XML Paper Specification (XPS) file format
- XPS (XML Paper Specification) file format
- XPSDrv-based printers
- GDI print path [WPF]
ms.assetid: 0de8ac41-9aa6-413d-a121-7aa6f41539b1
ms.openlocfilehash: e4aeeaadf8548065859e96e62b4de83759a9cec1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973153"
---
# <a name="printing-overview"></a>打印概述
使用 Microsoft .NET 框架，使用 Windows Presentation Foundation (WPF) 的应用程序开发人员具有丰富的一组新的打印和打印系统管理 Api。 在 Windows Vista 中，某些打印系统增强功能还可供开发人员使用非托管代码创建 Windows 窗体应用程序和开发人员使用。 这一新功能的核心是新的 XML 纸张规范 (XPS) 文件格式和 XPS 打印路径。  
  
 本主题包含以下各节：  
  
<a name="introduction_to_XPS"></a>
## <a name="about-xps"></a>关于 XPS  
 XPS 是一种电子文档格式，是一种假脱机文件格式和页面描述语言。 这是一种打开的文档格式，它使用 XML、开放打包约定 (OPC) 和其他行业标准来创建跨平台文档。 XPS 简化了创建、共享、打印、查看和存档数字文档的过程。 有关 XPS 的其他信息，请参阅 [Xps 文档](/windows/desktop/printdocs/documents)。  
  
 以 [编程方式打印 Xps 文件](how-to-programmatically-print-xps-files.md)中演示了使用 WPF 打印基于 XPS 的内容的几种方法。 在查看本主题中的内容时，参考这些示例会很有帮助。  (非托管代码开发人员应查看 [MXDC_ESCAPE 函数](/windows/desktop/printdocs/mxdc-escape)的文档。 Windows 窗体开发人员必须在命名空间中使用 API <xref:System.Drawing.Printing> ，该命名空间不支持完整的 XPS 打印路径，但支持混合的 GDI 到 XPS 打印路径。 请参阅下面的 **打印路径体系结构**。）  
  
<a name="XPS_print_path_intro"></a>
## <a name="xps-print-path"></a>XPS 打印路径  
 XML 纸张规范 (XPS) 打印路径是一种新的 Windows 功能，可重新定义如何在 Windows 应用程序中处理打印。 由于 XPS 可以替换文档表示语言 (如 RTF) 、打印后台处理程序格式 (如 WMF) ）和页面描述语言（如 PCL 或 Postscript (），新的打印路径将应用程序发布中的 XPS 格式维护到打印驱动程序或设备中的最终处理。  
  
 XPS 打印路径是基于 XPS 打印机驱动程序模型构建的， (XPSDrv) ，它为开发人员提供了几个优点，如 "你所见即所得" (WYSIWYG) 打印、改进的颜色支持和显著改进的打印性能。  (有关 XPSDrv 的详细信息，请参阅 [Windows 驱动程序工具包文档](/windows-hardware/drivers/)。 )   
  
 XPS 文档的打印后台处理程序的操作本质上与以前版本的 Windows 相同。 但是，它已得到增强，除了现有的 GDI 打印路径以外，还支持 XPS 打印路径。 新的打印路径本机使用 XPS 假脱机文件。 虽然为以前版本的 Windows 编写的用户模式打印机驱动程序将继续工作，但 XPS 打印机驱动程序 (XPSDrv) 以便使用 XPS 打印路径。  
  
 XPS 打印路径的优点非常重要，包括：  
  
- WYSIWYG 打印支持  
  
- 对高级颜色配置文件的本机支持（包括 32 位/通道 (bpc)、CMYK、已命名的颜色、n 墨迹）以及对透明和渐变的本机支持。  
  
- 提高了 .NET Framework 和基于 Win32 的应用程序的打印性能。  
  
- 行业标准 XPS 格式。  
  
 对于基本打印方案，提供了一个简单且直观的 API，其中包含用于用户界面、配置和作业提交的单一入口点。 对于高级方案，为 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 自定义（或根本没有 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]）、同步或异步打印以及批量打印功能添加了附加支持。 这两个选项在完全或部分信任模式下都提供打印支持。  
  
 XPS 的设计考虑了扩展性。 通过使用扩展性框架，可以采用模块化方式将特性和功能添加到 XPS。 扩展性功能包括：  
  
- 打印架构。 公共架构将定期进行更新，并可以实现设备功能的迅速扩展。 （请参阅下面的 **PrintTicket 和 PrintCapabilities**。）  
  
- 可扩展筛选器管道。 XPS 打印机驱动程序 (XPSDrv) 筛选器管道设计用于启用 XPS 文档的直接和可缩放打印。 有关详细信息，请参阅 [XPSDrv 打印机驱动程序](/windows-hardware/drivers/print/xpsdrv-printer-drivers)。
  
### <a name="print-path-architecture"></a>打印路径体系结构  
 尽管 Win32 和 .NET Framework 应用程序都支持 XPS，但 Win32 和 Windows 窗体应用程序都使用 GDI 进行 XPS 转换，以便为 XPS 打印机驱动程序 (XPSDrv) 创建 XPS 格式的内容。 这些应用程序不是使用 XPS 打印路径所必需的，并且可以继续使用增强型图元文件 (EMF) 打印。 但是，大多数 XPS 功能和增强功能仅适用于面向 XPS 打印路径的应用程序。  
  
 为了使 Win32 和 Windows 窗体应用程序能够使用基于 XPSDrv 的打印机，XPS 打印机驱动程序 (XPSDrv) 支持从 GDI 转换为 XPS 格式。 XPSDrv 模型还提供了用于 XPS 到 GDI 格式的转换器，以便 Win32 应用程序可以打印 XPS 文档。 对于 WPF 应用程序， <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> <xref:System.Windows.Xps.XpsDocumentWriter> 每当写入操作的目标打印队列没有 XPSDrv 驱动程序时，将由类的和方法自动完成 XPS 到 GDI 格式的转换。  (Windows 窗体应用程序不能打印 XPS 文档。 )   
  
 下图描述了打印子系统，并定义了 Microsoft 提供的部分以及由软件和硬件供应商定义的部分：  
  
 ![屏幕截图显示了 XPS 打印系统。](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>基本 XPS 打印  
 WPF 定义基本和高级 API。 对于不需要广泛的打印自定义或访问完整的 XPS 功能集的那些应用程序，可以使用基本打印支持。 基本打印支持通过一个打印对话框控件公开，该控件要求最低的配置，并采用熟悉的 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]。 使用此简化的打印模型可以获得多种 XPS 功能。  
  
#### <a name="printdialog"></a>PrintDialog  
 <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>控件为 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 、配置和 XPS 作业提交提供单一入口点。 若要了解如何实例化和使用该控件，请参阅[调用打印对话框](how-to-invoke-a-print-dialog.md)。  
  
### <a name="advanced-xps-printing"></a>高级 XPS 打印  
 若要访问完整的 XPS 功能集，必须使用高级打印 API。 下面更详细地介绍了几个相关的 API。 有关 XPS 打印路径 Api 的完整列表，请参阅 <xref:System.Windows.Xps> 和 <xref:System.Printing> 命名空间引用。  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket 和 PrintCapabilities  
 <xref:System.Printing.PrintTicket>和 <xref:System.Printing.PrintCapabilities> 类是高级 XPS 功能的基础。 这两种类型的对象均是面向打印的功能（例如排序规则、双面打印、装订等）的 XML 格式的结构。这些结构由打印架构定义。 <xref:System.Printing.PrintTicket> 指示打印机如何处理打印作业。 <xref:System.Printing.PrintCapabilities> 类定义打印机的各种功能。 通过查询打印机的功能，可以创建充分利用打印机的受支持功能的 <xref:System.Printing.PrintTicket>。 同样，可以避免不受支持的功能。  
  
 下面的示例演示如何使用代码查询打印机的 <xref:System.Printing.PrintCapabilities> 和创建 <xref:System.Printing.PrintTicket>。  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer 和 PrintQueue  
 <xref:System.Printing.PrintServer> 类表示一个网络打印服务器，而 <xref:System.Printing.PrintQueue> 类则表示一台打印机以及与其关联的输出作业队列。 这些 Api 共同允许对服务器的打印作业进行高级管理。 <xref:System.Printing.PrintServer> 或其派生类之一用于管理 <xref:System.Printing.PrintQueue>。 <xref:System.Printing.PrintQueue.AddJob%2A> 方法用于将新的打印作业插入队列。  
  
 下面的示例演示如何使用代码创建 <xref:System.Printing.LocalPrintServer> 和访问其默认的 <xref:System.Printing.PrintQueue>。  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 <xref:System.Windows.Xps.XpsDocumentWriter>，它具有多个 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> 和 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 方法，用于将 XPS 文档写入 <xref:System.Printing.PrintQueue> 。 例如， <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> 方法用于输出 XPS 文档并进行 <xref:System.Printing.PrintTicket> 同步。 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29>方法用于输出 XPS 文档和 <xref:System.Printing.PrintTicket> 异步。  
  
 下面的示例演示如何使用代码创建 <xref:System.Windows.Xps.XpsDocumentWriter>。  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 <xref:System.Printing.PrintQueue.AddJob%2A> 方法还提供打印方法。 请参阅[以编程方式打印 XPS 文件](how-to-programmatically-print-xps-files.md)。 以获取详细信息。  
  
<a name="GDI_Print_Path_intro"></a>
## <a name="gdi-print-path"></a>GDI 打印路径  
 虽然 WPF 应用程序以本机方式支持 XPS 打印路径，但 Win32 和 Windows 窗体应用程序也可以利用某些 XPS 功能。 XPS 打印机驱动程序 (XPSDrv) 可以将基于 GDI 的输出转换为 XPS 格式。 对于高级方案，使用 [MICROSOFT XPS 文档转换器 (MXDC) ](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)支持内容的自定义转换。 同样，WPF 应用程序还可以通过调用 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> 类的或 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 方法之一 <xref:System.Windows.Xps.XpsDocumentWriter> ，并指定非 XpsDrv 打印机作为目标打印队列来输出到 GDI 打印路径。  

对于不需要 XPS 功能或支持的应用程序，当前的 GDI 打印路径保持不变。  
  
- 有关 GDI 打印路径和各种 XPS 转换选项的其他参考资料，请参阅 [MICROSOFT XPS 文档转换器 (MXDC) ](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) 和 [XPSDrv 打印机驱动程序](/windows-hardware/drivers/print/xpsdrv-printer-drivers)。  
  
<a name="XPS_Driver_Model_intro"></a>
## <a name="xpsdrv-driver-model"></a>XPSDrv 驱动程序模型  
 XPS 打印路径在打印到启用 XPS 的打印机或驱动程序时使用 XPS 作为本机打印后台处理格式，从而提高了后台处理程序的效率。 简化的假脱机过程消除了在文档进行后台处理之前生成中间后台打印文件（如 EMF 数据文件）的需要。 通过较小的假脱机文件大小，XPS 打印路径可以减少网络流量并提高打印性能。  
  
 EMF 是一种封闭格式，它将应用程序输出表示为对用于呈现服务的 GDI 进行的一系列调用。 与 EMF 不同，XPS 假脱机格式代表实际的文档，而在输出到基于 XPS 的打印机驱动程序 (XPSDrv) 时无需进一步解释。 这些驱动程序可以用这种格式直接对数据进行操作。 此功能消除了使用 EMF 文件和基于 GDI 的打印驱动程序时所需的数据和颜色空间转换。  
  
 如果使用面向 XPS 打印机驱动程序的 XPS 文档 (XPSDrv) 与 EMF 等效项进行比较，则通常会降低假脱机文件大小;但是，有一些例外情况：  
  
- 相当复杂、分为多层或者编写效率低下的向量图形可能比同一图形的位图图形更大。  
  
- 出于屏幕显示的目的，XPS 文件中嵌入了设备字体以及基于计算机的字体，而 GDI 打印后台文件未嵌入设备字体。 这两种字体都划分了子集（请参见下面的内容），而且打印机驱动程序可以在将文件传输给打印机之前删除这些设备字体。  
  
 可通过几种机制来减小后台打印文件的大小：  
  
- **字体子集划分**。 只有实际文档中使用的字符才存储在 XPS 文件中。  
  
- **高级图形支持**。 对透明和渐变基元的本机支持可避免 XPS 文档中的内容光栅化。  
  
- **公共资源的识别**。 将多次使用的资源（如表示公司徽标的图像）视为共享资源，并且只加载一次。  
  
- **ZIP 压缩**。 所有 XPS 文档均使用 ZIP 压缩。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [操作指南主题](printing-how-to-topics.md)
- [WPF 中的文档](documents-in-wpf.md)
- [XPS 文档](/windows/desktop/printdocs/documents)
- [文档序列化和存储](document-serialization-and-storage.md)
- [Microsoft XPS 文档转换器 (MXDC) ](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
