---
title: 将玻璃框扩展到 WPF 应用
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
ms.openlocfilehash: b78547aa8b414c585bb2e5c9c6680ed159731bc3
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972862"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="85975-102">将玻璃框扩展到 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="85975-102">Extend Glass Frame Into a WPF Application</span></span>

<span data-ttu-id="85975-103">本主题演示如何将 Windows Vista 玻璃框架扩展到 Windows Presentation Foundation (WPF) 应用程序的工作区。</span><span class="sxs-lookup"><span data-stu-id="85975-103">This topic demonstrates how to extend the Windows Vista glass frame into the client area of a Windows Presentation Foundation (WPF) application.</span></span>

> [!NOTE]
> <span data-ttu-id="85975-104">此示例仅适用于运行桌面窗口管理器 (DWM) 启用了玻璃的 Windows Vista 计算机。</span><span class="sxs-lookup"><span data-stu-id="85975-104">This example will only work on a Windows Vista machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> <span data-ttu-id="85975-105">Windows Vista Home Basic 版本不支持透明玻璃效果。</span><span class="sxs-lookup"><span data-stu-id="85975-105">Windows Vista Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="85975-106">通常会在其他版本的 Windows Vista 上呈现透明玻璃效果的区域呈现为不透明。</span><span class="sxs-lookup"><span data-stu-id="85975-106">Areas that would typically render with the transparent glass effect on other editions of Windows Vista are rendered opaque.</span></span>

## <a name="example"></a><span data-ttu-id="85975-107">示例</span><span class="sxs-lookup"><span data-stu-id="85975-107">Example</span></span>

<span data-ttu-id="85975-108">下图说明了扩展到 Internet Explorer 7 的地址栏中的玻璃框：</span><span class="sxs-lookup"><span data-stu-id="85975-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7:</span></span>

![显示在 IE7 地址栏后扩展的玻璃帧的屏幕截图。](./media/extend-glass-frame-into-a-wpf-application/internet-explorer-glass-frame-extended-address-bar.png)

<span data-ttu-id="85975-110">若要在 WPF 应用程序上扩展玻璃帧，需要访问非托管 API。</span><span class="sxs-lookup"><span data-stu-id="85975-110">To extend the glass frame on a WPF application, access to unmanaged API is needed.</span></span> <span data-ttu-id="85975-111">下面的代码示例对两个 API 调用 (pinvoke) ，以将框架扩展到客户端区域。</span><span class="sxs-lookup"><span data-stu-id="85975-111">The following code example does a Platform Invoke (pinvoke) for the two API needed to extend the frame into the client area.</span></span> <span data-ttu-id="85975-112">其中每个 API 在名为 **NonClientRegionAPI** 的类中声明。</span><span class="sxs-lookup"><span data-stu-id="85975-112">Each of these API are declared in a class called **NonClientRegionAPI**.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential)]
public struct MARGINS
{
    public int cxLeftWidth;      // width of left border that retains its size
    public int cxRightWidth;     // width of right border that retains its size
    public int cyTopHeight;      // height of top border that retains its size
    public int cyBottomHeight;   // height of bottom border that retains its size
};

[DllImport("DwmApi.dll")]
public static extern int DwmExtendFrameIntoClientArea(
    IntPtr hwnd,
    ref MARGINS pMarInset);
```

```vb
<StructLayout(LayoutKind.Sequential)>
Public Structure MARGINS
    Public cxLeftWidth As Integer ' width of left border that retains its size
    Public cxRightWidth As Integer ' width of right border that retains its size
    Public cyTopHeight As Integer ' height of top border that retains its size
    Public cyBottomHeight As Integer ' height of bottom border that retains its size
End Structure

<DllImport("DwmApi.dll")>
Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer
End Function
```

<span data-ttu-id="85975-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) 是将框扩展到工作区的 DWM 函数。</span><span class="sxs-lookup"><span data-stu-id="85975-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="85975-114">它采用两个参数：一个窗口句柄和一个 [MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) 结构。</span><span class="sxs-lookup"><span data-stu-id="85975-114">It takes two parameters; a window handle and a [MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) structure.</span></span> <span data-ttu-id="85975-115">[MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) 用于告知 DWM 应向工作区扩展多少额外框。</span><span class="sxs-lookup"><span data-stu-id="85975-115">[MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>

## <a name="example"></a><span data-ttu-id="85975-116">示例</span><span class="sxs-lookup"><span data-stu-id="85975-116">Example</span></span>

<span data-ttu-id="85975-117">若要使用 [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) 函数，必须获取窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="85975-117">To use the [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) function, a window handle must be obtained.</span></span> <span data-ttu-id="85975-118">在 WPF 中，可以从的属性获取窗口句柄 <xref:System.Windows.Interop.HwndSource.Handle%2A> <xref:System.Windows.Interop.HwndSource> 。</span><span class="sxs-lookup"><span data-stu-id="85975-118">In WPF, the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="85975-119">在下面的示例中，将框架扩展到窗口事件的工作区中 <xref:System.Windows.FrameworkElement.Loaded> 。</span><span class="sxs-lookup"><span data-stu-id="85975-119">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>

```csharp
void OnLoaded(object sender, RoutedEventArgs e)
{
   try
   {
      // Obtain the window handle for WPF application
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);

      // Get System Dpi
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);
      float DesktopDpiX = desktop.DpiX;
      float DesktopDpiY = desktop.DpiY;

      // Set Margins
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();

      // Extend glass frame into client area
      // Note that the default desktop Dpi is 96dpi. The  margins are
      // adjusted for the system Dpi.
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));

      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);
      //
      if (hr < 0)
      {
         //DwmExtendFrameIntoClientArea Failed
      }
   }
   // If not Vista, paint background white.
   catch (DllNotFoundException)
   {
      Application.Current.MainWindow.Background = Brushes.White;
   }
}
```

## <a name="example"></a><span data-ttu-id="85975-120">示例</span><span class="sxs-lookup"><span data-stu-id="85975-120">Example</span></span>

<span data-ttu-id="85975-121">以下示例演示一个简单的窗口，在该窗口中框扩展到工作区。</span><span class="sxs-lookup"><span data-stu-id="85975-121">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="85975-122">该帧在包含两个对象的上边框的上方扩展 <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="85975-122">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>

```xaml
<Window x:Class="SDKSample.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Title="Extended Glass in WPF" Height="300" Width="400"
    Loaded="OnLoaded" Background="Transparent"
    >
  <Grid ShowGridLines="True">
    <DockPanel Name="mainDock">
      <!-- The border is used to compute the rendered height with margins.
           topBar contents will be displayed on the extended glass frame.-->
      <Border Name="topBar" DockPanel.Dock="Top" >
        <Grid Name="grid">
          <Grid.ColumnDefinitions>
            <ColumnDefinition MinWidth="100" Width="*"/>
            <ColumnDefinition Width="Auto"/>
          </Grid.ColumnDefinitions>
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>
        </Grid>
      </Border>
      <Grid DockPanel.Dock="Top" >
        <Grid.ColumnDefinitions>
          <ColumnDefinition/>
        </Grid.ColumnDefinitions>
        <TextBox Grid.Column="0" AcceptsReturn="True"/>
      </Grid>
    </DockPanel>
  </Grid>
</Window>
```

<span data-ttu-id="85975-123">下图说明扩展到 WPF 应用程序中的玻璃帧：</span><span class="sxs-lookup"><span data-stu-id="85975-123">The following image illustrates the glass frame extended into a WPF application:</span></span>

![显示扩展到 WPF 应用程序中的玻璃框的屏幕截图。](./media/extend-glass-frame-into-a-wpf-application/glass-frame-extended-wpf-application.png)

## <a name="see-also"></a><span data-ttu-id="85975-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85975-125">See also</span></span>

- [<span data-ttu-id="85975-126">桌面窗口管理器概述</span><span class="sxs-lookup"><span data-stu-id="85975-126">Desktop Window Manager Overview</span></span>](/windows/desktop/dwm/dwm-overview)
- [<span data-ttu-id="85975-127">桌面窗口管理器模糊概述</span><span class="sxs-lookup"><span data-stu-id="85975-127">Desktop Window Manager Blur Overview</span></span>](/windows/desktop/dwm/blur-ovw)
- [<span data-ttu-id="85975-128">DwmExtendFrameIntoClientArea</span><span class="sxs-lookup"><span data-stu-id="85975-128">DwmExtendFrameIntoClientArea</span></span>](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)
