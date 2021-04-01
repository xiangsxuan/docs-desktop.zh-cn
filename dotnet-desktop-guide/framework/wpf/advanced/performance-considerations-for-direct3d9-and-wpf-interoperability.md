---
title: Direct3D9 和 WPF 互操作的性能注意事项
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: 2445732c27d210a41da26303d6a9ce07ef6fcc94
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971749"
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Direct3D9 和 WPF 互操作性的性能注意事项
可以使用类来承载 Direct3D9 内容 <xref:System.Windows.Interop.D3DImage> 。 托管 Direct3D9 内容会影响应用程序的性能。 本主题介绍在 Windows Presentation Foundation (WPF) 应用程序中承载 Direct3D9 内容时优化性能的最佳做法。 这些最佳实践包括 <xref:System.Windows.Interop.D3DImage> 使用 Windows Vista、WINDOWS XP 和多监视器显示器时如何使用和最佳实践。  
  
> [!NOTE]
> 有关演示这些最佳实践的代码示例，请参阅 [WPF 和 Direct3D9 互操作](wpf-and-direct3d9-interoperation.md)。  
  
## <a name="use-d3dimage-sparingly"></a>慎用 D3DImage  
 在实例中托管的 Direct3D9 内容的 <xref:System.Windows.Interop.D3DImage> 呈现速度不像在纯 Direct3D 应用程序中一样快。 复制图面并刷新命令缓冲区可能会耗费大量的操作。 随着实例数量的 <xref:System.Windows.Interop.D3DImage> 增加，会发生更多刷新，并且性能会下降。 因此，您应该 <xref:System.Windows.Interop.D3DImage> 谨慎使用。  
  
## <a name="best-practices-on-windows-vista"></a>Windows Vista 上的最佳做法  
 若要在 Windows Vista 上获得最佳性能，并使用配置为使用 Windows 显示驱动程序模型 (WDDM) 的显示器，请在设备上创建 Direct3D9 表面 `IDirect3DDevice9Ex` 。 这会启用表面共享。 视频卡必须支持 `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` `D3DCAPS2_CANSHARERESOURCE` Windows Vista 上的和驱动程序功能。 任何其他设置都会导致通过软件复制表面，这会显著降低性能。  
  
> [!NOTE]
> 如果 Windows Vista 具有配置为使用 Windows XP 显示驱动程序模型 (XDDM) 的显示器，则无论设置如何，都将始终通过软件复制该曲面。 如果使用了适当的设置和视频卡，则在使用 WDDM 时，Windows Vista 上将显示更好的性能，因为在硬件中执行 surface 副本。  
  
## <a name="best-practices-on-windows-xp"></a>Windows XP 上的最佳做法  
 若要在使用 Windows XP 显示驱动程序模型 (XDDM) 的 Windows XP 上获得最佳性能，请在调用方法时创建一个正常运行的可锁定表面 `IDirect3DSurface9::GetDC` 。 在内部， `BitBlt` 方法在硬件中跨设备传输表面。 `GetDC`方法始终适用于 XRGB 图面。 但是，如果客户端计算机运行的是带有 SP3 或 SP2 的 Windows XP，并且客户端也具有用于分层窗口功能的修补程序，则此方法仅适用于 ARGB 图面。 视频卡必须支持 `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` 驱动程序功能。  
  
 16位桌面显示深度可能会显著降低性能。 建议使用32位桌面。  
  
 如果要针对 Windows Vista 和 Windows XP 进行开发，请在 Windows XP 上测试性能。 Windows XP 上的视频内存不足是个问题。 此外， <xref:System.Windows.Interop.D3DImage> 在 windows XP 上，由于需要额外的视频内存复制，windows XP 比 Windows VISTA WDDM 使用的视频内存和带宽更多。 因此，对于同一视频硬件，在 Windows XP 和 Windows Vista 上，性能会更糟。  
  
> [!NOTE]
> Windows XP 和 Windows Vista 上都提供了 XDDM;但是，WDDM 仅适用于 Windows Vista。  
  
## <a name="general-best-practices"></a>常规最佳做法  
 创建设备时，请使用 `D3DCREATE_MULTITHREADED` 创建标志。 这会降低性能，但 WPF 呈现系统会从另一个线程调用此设备上的方法。 请确保正确遵循锁定协议，以便没有两个线程同时访问设备。  
  
 如果您的呈现在 WPF 托管线程上执行，则强烈建议您使用 `D3DCREATE_FPU_PRESERVE` 创建标志创建设备。 如果没有此设置，D3D 呈现可以降低 WPF 双精度操作的准确性，并引入呈现问题。  
  
 平铺 <xref:System.Windows.Interop.D3DImage> 是快速的，除非在没有硬件支持的情况下平铺非 pow2 表面，或者平 <xref:System.Windows.Media.DrawingBrush> 铺 <xref:System.Windows.Media.VisualBrush> 包含的或 <xref:System.Windows.Interop.D3DImage> 。  
  
## <a name="best-practices-for-multi-monitor-displays"></a>多监视器显示器的最佳实践  
 如果你使用的是具有多个监视器的计算机，则应遵循前面所述的最佳实践。 对于多监视器配置，还有一些其他性能注意事项。  
  
 创建后台缓冲区时，将在特定设备和适配器上创建它，但 WPF 可能会在任何适配器上显示前台缓冲区。 跨适配器复制以更新前台缓冲区可能非常昂贵。 在配置为将 WDDM 用于多个视频卡和设备的 Windows Vista 上 `IDirect3DDevice9Ex` ，如果前一个缓冲区位于不同的适配器上，但仍处于同一视频卡，则不会产生性能损失。 但是，在 Windows XP 和具有多个视频卡的 XDDM 上，当前台缓冲区显示在不同于后台缓冲区的适配器上时，将会出现明显的性能下降。 有关详细信息，请参阅 [WPF 和 Direct3D9 互操作](wpf-and-direct3d9-interoperation.md)。  
  
## <a name="performance-summary"></a>性能摘要  
 下表显示了前台缓冲区更新的性能，作为操作系统、像素格式和 surface lockability 的函数。 前台缓冲区和后台缓冲区假定位于同一适配器上。 硬件更新的速度通常比软件更新的速度要快得多，具体取决于适配器配置。  
  
|Surface 像素格式|Windows Vista、WDDM 和9Ex|其他 Windows Vista 配置|Windows XP SP3 或 SP2 w/修补程序|Windows XP SP2|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|D3DFMT_X8R8G8B8 (不可锁定) |**硬件更新**|软件更新|软件更新|软件更新|  
|D3DFMT_X8R8G8B8 (锁定) |**硬件更新**|软件更新|**硬件更新**|**硬件更新**|  
|D3DFMT_A8R8G8B8 (不可锁定) |**硬件更新**|软件更新|软件更新|软件更新|  
|D3DFMT_A8R8G8B8 (锁定) |**硬件更新**|软件更新|**硬件更新**|软件更新|  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Interop.D3DImage>
- [WPF 和 Direct3D9 互操作](wpf-and-direct3d9-interoperation.md)
- [演练：创建在 WPF 中承载的 Direct3D9 内容](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [演练：在 WPF 中承载 Direct3D9 内容](walkthrough-hosting-direct3d9-content-in-wpf.md)
