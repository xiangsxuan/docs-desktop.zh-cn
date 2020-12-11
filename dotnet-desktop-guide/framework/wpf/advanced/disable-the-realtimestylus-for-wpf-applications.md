---
title: 禁用 RealTimeStylus
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: c2500b494f76c85e4b23823a44a180d85d5092ff
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973007"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="780f5-102">禁用用于 WPF 应用程序的 RealTimeStylus</span><span class="sxs-lookup"><span data-stu-id="780f5-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="780f5-103">Windows Presentation Foundation (WPF) 支持处理 Windows 7 触控输入。</span><span class="sxs-lookup"><span data-stu-id="780f5-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="780f5-104">此支持通过 tablet 平台的实时触笔输入来作为 <xref:System.Windows.UIElement.OnStylusDown%2A> 、 <xref:System.Windows.UIElement.OnStylusUp%2A> 和 <xref:System.Windows.UIElement.OnStylusMove%2A> 事件。</span><span class="sxs-lookup"><span data-stu-id="780f5-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="780f5-105">Windows 7 还提供多点触控输入作为 Win32 WM_TOUCH 窗口消息。</span><span class="sxs-lookup"><span data-stu-id="780f5-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="780f5-106">这两个 Api 在同一 HWND 上相互排斥。</span><span class="sxs-lookup"><span data-stu-id="780f5-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="780f5-107">通过 tablet 平台启用触控输入 (WPF 应用程序的默认值) 禁用 WM_TOUCH 消息。</span><span class="sxs-lookup"><span data-stu-id="780f5-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="780f5-108">因此，若要使用 WM_TOUCH 从 WPF 窗口接收触摸消息，您必须禁用 WPF 中的内置触笔支持。</span><span class="sxs-lookup"><span data-stu-id="780f5-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="780f5-109">这适用于一个方案，例如 WPF 窗口，该窗口承载使用 WM_TOUCH 的组件。</span><span class="sxs-lookup"><span data-stu-id="780f5-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="780f5-110">若要禁用 WPF 侦听触笔输入，请移除由 WPF 窗口添加的任何 tablet 支持。</span><span class="sxs-lookup"><span data-stu-id="780f5-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="780f5-111">示例</span><span class="sxs-lookup"><span data-stu-id="780f5-111">Example</span></span>  
 <span data-ttu-id="780f5-112">下面的示例代码演示如何通过使用反射删除默认 tablet 平台支持。</span><span class="sxs-lookup"><span data-stu-id="780f5-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```csharp  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="780f5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="780f5-113">See also</span></span>

- [<span data-ttu-id="780f5-114">截获触笔输入</span><span class="sxs-lookup"><span data-stu-id="780f5-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
