---
title: 演练：创建基于 Windows 的可访问应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
dev_langs:
- csharp
- vb
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
ms.openlocfilehash: 63d328c1dae9eb18be0631a0007a92ad10461afb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971576"
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a>演练：创建基于 Windows 的可访问应用程序

创建具有辅助功能的应用程序具有重要的商业意义。 很多政府都有针对软件购买的辅助功能法规。 Certified for Windows 徽标包括辅助功能需求。 据估计，仅美国就有 3 千万居民（其中很多为潜在客户）受到软件辅助功能的影响。

此演练将针对 Certified for Windows 徽标的 5 项辅助功能需求。 根据这些要求，具有辅助功能的应用程序将：

- 支持控件面板大小、颜色、字体和输入设置。 当用户更改控件面板设置时，菜单栏、标题栏、边框和状态栏都将调整大小。 此应用程序中不需要对控件或代码进行任何其他更改。

- 支持高对比度模式。

- 提供对所有功能的已记录的键盘访问。

- 以可视方式和以编程方式公开键盘焦点的位置。

- 避免仅靠声音传达重要信息。

有关详细信息，请参阅[用于设计支持辅助功能的应用程序的资源](/visualstudio/ide/reference/resources-for-designing-accessible-applications)。

有关支持不同键盘布局的信息，请参阅[开发全球通用应用程序的最佳做法](/dotnet/standard/globalization-localization/best-practices-for-developing-world-ready-apps)。

## <a name="creating-the-project"></a>创建项目

此演练为一个可接受比萨订单的应用程序创建用户界面。 它包含以下内容：一个用于输入客户名称的 <xref:System.Windows.Forms.TextBox>一个用于选择比萨大小的 <xref:System.Windows.Forms.RadioButton> 组，一个用于选择浇头的 <xref:System.Windows.Forms.CheckedListBox>分别标记为“订购”和“取消”的两个 Button 控件，以及一个具有“退出”命令的“菜单”。

用户输入客户名称、比萨大小和想要的浇头。 当用户单击“订购”按钮时，将在消息框中显示订单一览表及其价格，然后将控件清除并为下个订单做好准备。 当用户单击“取消”按钮时，将控件清除并为下个订单做好准备。 当用户单击“退出”菜单项时，程序关闭。

本演练的重点不是零售订单系统的代码，而是用户界面的辅助功能。 本演练说明几个常用控件（包括按钮、单选按钮、文本框和标签）的辅助功能。

#### <a name="to-begin-making-the-application"></a>开始生成应用程序

- 在 Visual Basic 或 Visual c # 中创建新的 Windows 应用程序。 将项目命名为 **PizzaOrder**。 有关详细信息，请参阅 [创建新解决方案和项目](/visualstudio/ide/creating-solutions-and-projects)。

## <a name="adding-the-controls-to-the-form"></a>将控件添加到窗体

将控件添加到窗体时，请牢记以下指南以生成具有辅助功能的应用程序：

- 设置 <xref:System.Windows.Forms.Control.AccessibleDescription%2A> 和 <xref:System.Windows.Forms.Control.AccessibleName%2A> 属性。 在此示例中，<xref:System.Windows.Forms.Control.AccessibleRole%2A> 的默认设置已经足够。 有关辅助功能属性的详细信息，请参阅[为 Windows 窗体上的控件提供辅助功能信息](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md)。

- 将字体大小设置为 10 号或更大。

  > [!NOTE]
  > 如果在启动时将窗体的字体大小设置为 10，则随后添加到窗体的所有控件的字体大小均为 10。

- 确保任何描述 TextBox 控件的 Label 控件均按 Tab 顺序紧排在相应的 TextBox 控件之前。

- 使用 "&" 字符将访问键添加到 <xref:System.Windows.Forms.Control.Text%2A> 用户可能想要导航到的任何控件的属性。

- 使用 "&" 字符将访问键添加到 <xref:System.Windows.Forms.Control.Text%2A> 用户可能想要导航到的控件之前的标签属性。 将标签的 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 属性设置为 `true`，以便在用户按下访问键时将焦点设置到按 Tab 键顺序的下一控件。

- 将访问键添加到所有菜单项。

#### <a name="to-make-your-windows-application-accessible"></a>使 Windows 应用程序具有辅助功能

- 将控件添加到窗体并如下所述设置属性。 有关如何在窗体上排列控件的模型，请查看表结尾处的图片。

   |Object|属性|值|
   |------------|--------------|-----------|
   |Form1|AccessibleDescription|订购窗体|
   ||AccessibleName|订购窗体|
   ||字号|10|
   ||文本|比萨饼订购窗体|
   |PictureBox|名称|徽标|
   ||AccessibleDescription|一片比萨饼|
   ||AccessibleName|公司徽标|
   ||图像|任何图标或位图|
   |Label|名称|companyLabel|
   ||文本|美味比萨|
   ||TabIndex|1|
   ||AccessibleDescription|公司名称|
   ||AccessibleName|公司名称|
   ||背景色|蓝色|
   ||前景色|Yellow|
   ||字体大小|18|
   |Label|名称|customerLabel|
   ||文本|名称(&N)|
   ||TabIndex|2|
   ||AccessibleDescription|客户名称标签|
   ||AccessibleName|客户名称标签|
   ||UseMnemonic|正确|
   |TextBox|名称|customerName|
   ||文本|（无）|
   ||TabIndex|3|
   ||AccessibleDescription|客户名称|
   ||AccessibleName|客户名称|
   |GroupBox|名称|sizeOptions|
   ||AccessibleDescription|比萨大小选项|
   ||AccessibleName|比萨大小选项|
   ||文本|比萨大小|
   ||TabIndex|4|
   |RadioButton|名称|smallPizza|
   ||文本|小号 $6.00 (&S)|
   ||已选中|正确|
   ||TabIndex|0|
   ||AccessibleDescription|小号比萨|
   ||AccessibleName|小号比萨|
   |RadioButton|名称|largePizza|
   ||文本|大号 $10.00 (&L)|
   ||TabIndex|1|
   ||AccessibleDescription|大号披萨|
   ||AccessibleName|大号披萨|
   |Label|名称|toppingsLabel|
   ||文本|浇头(每个$0.75)(&T)|
   ||TabIndex|5|
   ||AccessibleDescription|浇头标签|
   ||AccessibleName|浇头标签|
   ||UseMnemonic|正确|
   |CheckedListBox|名称|浇头|
   ||TabIndex|6|
   ||AccessibleDescription|可用浇头|
   ||AccessibleName|可用浇头|
   ||项目|意大利辣肠、香肠、蘑菇|
   |Button|名称|顺序|
   ||文本|顺序(&O)|
   ||TabIndex|7|
   ||AccessibleDescription|订单合计|
   ||AccessibleName|总订单|
   |Button|名称|cancel|
   ||文本|取消(&C)|
   ||TabIndex|8|
   ||AccessibleDescription|取消订单|
   ||AccessibleName|取消订单|
   |MainMenu|名称|theMainMenu|
   |MenuItem|名称|fileCommands|
   ||文本|文件(&F)|
   |MenuItem|名称|exitApp|
   ||文本|退出(&X)|

   您的窗体将如下图所示：

   !["比萨饼订单" 窗体具有 "名称" 文本框，"大小" 和 "浇头" 选项。](./media/walkthrough-creating-an-accessible-windows-based-application/visual-basic-pizza-order-form.gif)

## <a name="supporting-high-contrast-mode"></a>支持高对比度模式

高对比度模式是一种 Windows 系统设置，它通过使用有益于视力受损用户的对比颜色和字体大小提高可读性。 <xref:System.Windows.Forms.SystemInformation.HighContrast%2A>提供属性以确定是否设置了高对比度模式。

如果 SystemInformation.HighContrast 为`true`，则应用程序应：

- 显示使用系统配色方案的所有用户界面元素

- 通过可视提示或声音传递任何通过颜色传递的信息。 例如，如果特定列表项使用红色字体突出显示，则还可为字体加粗，以便用户得到突出显示项的非颜色提示。

- 忽略文本之后的任何图像或图案

应用程序应在启动时检查 <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> 的设置，并响应系统事件 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>。 每当 <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> 的值更改时，都会引发 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 事件。

在本应用程序中，未使用系统颜色设置的唯一元素是 `lblCompanyName`。 <xref:System.Drawing.SystemColors>类用于将标签的颜色设置更改为用户选择的系统颜色。

#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a>有效地启用高对比度模式

1. 创建一种方法将标签颜色设置为系统颜色。

    ```vb
    Private Sub SetColorScheme()
        If SystemInformation.HighContrast Then
            companyLabel.BackColor = SystemColors.Window
            companyLabel.ForeColor = SystemColors.WindowText
        Else
            companyLabel.BackColor = Color.Blue
            companyLabel.ForeColor = Color.Yellow
        End If
    End Sub
    ```

    ```csharp
    private void SetColorScheme()
    {
        if (SystemInformation.HighContrast)
        {
            companyLabel.BackColor = SystemColors.Window;
            companyLabel.ForeColor = SystemColors.WindowText;
        }
        else
        {
            companyLabel.BackColor = Color.Blue;
            companyLabel.ForeColor = Color.Yellow;
        }
    }
    ```

2. 在窗体构造函数（Visual Basic 中为 `Public Sub New()`，Visual C# 中为 `public Form1()`）调用 `SetColorScheme` 过程。 若要访问 Visual Basic 中的构造函数，需要展开标记了“Windows 窗体设计器生成的代码”的区域。

    ```vb
    Public Sub New()
        MyBase.New()
        InitializeComponent()
        SetColorScheme()
    End Sub
    ```

    ```csharp
    public Form1()
    {
        InitializeComponent();
        SetColorScheme();
    }
    ```

3. 使用适当签名创建事件过程，以响应 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 事件。

    ```vb
    Protected Sub UserPreferenceChanged(sender As Object, _
    e As Microsoft.Win32.UserPreferenceChangedEventArgs)
        SetColorScheme()
    End Sub
    ```

    ```csharp
    public void UserPreferenceChanged(object sender,
    Microsoft.Win32.UserPreferenceChangedEventArgs e)
    {
        SetColorScheme();
    }
    ```

4. 在调用 `InitializeComponents` 后将代码添加到窗体构造函数，以便将事件过程挂钩到系统事件。 此方法调用 `SetColorScheme` 过程。

    ```vb
    Public Sub New()
        MyBase.New()
        InitializeComponent()
        SetColorScheme()
        AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _
           AddressOf Me.UserPreferenceChanged
    End Sub
    ```

    ```csharp
    public Form1()
    {
        InitializeComponent();
        SetColorScheme();
        Microsoft.Win32.SystemEvents.UserPreferenceChanged
           += new Microsoft.Win32.UserPreferenceChangedEventHandler(
           this.UserPreferenceChanged);
    }
    ```

5. 在调用基类的 <xref:System.Windows.Forms.Control.Dispose%2A> 方法之前将代码添加到窗体 <xref:System.Windows.Forms.Control.Dispose%2A> 方法，以便在应用程序关闭时释放事件。 若要访问 Visual Basic 中的 <xref:System.Windows.Forms.Control.Dispose%2A> 方法，需要展开标记为“Windows 窗体设计器生成的代码”区域。

    > [!NOTE]
    > 系统事件代码运行独立于主应用程序的线程。 如果不释放事件，挂钩到事件的代码在程序关闭后仍将运行。

    ```vb
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)
        If disposing AndAlso components IsNot Nothing Then
            components.Dispose()
        End If
        RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _
           AddressOf Me.UserPreferenceChanged
        MyBase.Dispose(disposing)
    End Sub
    ```

    ```csharp
    protected override void Dispose(bool disposing)
    {
        if(disposing && components != null)
        {
            components.Dispose();
        }
        Microsoft.Win32.SystemEvents.UserPreferenceChanged
           -= new Microsoft.Win32.UserPreferenceChangedEventHandler(
           this.UserPreferenceChanged);
        base.Dispose( disposing );
    }
    ```

6. 按 F5 运行该应用程序。

## <a name="conveying-important-information-by-means-other-than-sound"></a>通过非声音方式传达重要信息

在此应用程序中，没有信息是仅靠声音传达的。 如果在应用程序中使用声音，则还应通过其他一些方式提供信息。

#### <a name="to-supply-information-by-some-other-means-than-sound"></a>以声音以外的其他方式提供信息

1. 使用 Windows API 函数 FlashWindow 使标题栏闪烁。 有关如何调用 Windows API 函数的示例，请参阅[演练：调用 Windows API](/dotnet/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis)。

    > [!NOTE]
    > 用户可能已启用 Windows SoundSentry 服务，它也会在系统声音通过计算机内置扬声器播放时使窗口闪烁。

2. 在非模式窗口中显示重要信息，以便用户可以响应它。

3. 显示一个获取键盘焦点消息框。 在用户可能键入时避免使用此方法。

4. 在任务栏的状态通知区域中显示一个状态指示器。 有关详细信息，请参阅[使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)。

## <a name="testing-the-application"></a>测试应用程序

在部署应用程序之前，应测试已实现的辅助功能。

#### <a name="to-test-accessibility-features"></a>测试辅助功能

1. 若要测试键盘访问，请拔下鼠标，并仅使用键盘导航每个功能的用户界面。 确保只使用键盘即可执行所有任务。

2. 若要测试高对比度的支持，请在控制面板中选择“辅助功能选项”图标。 单击“显示”选项卡并选择“使用高对比度”复选框。 导航到所有用户界面元素以确保会反映颜色和字体更改。 此外，确保忽略文本后面绘制的图像或图案。

    > [!NOTE]
    > Windows NT 4 的控制面板中没有“辅助功能选项”图标。 因此，更改 SystemInformation.HighContrast 设置的此过程不适用于 Windows NT 4。

3. 其他工具也用于测试应用程序的辅助功能。

4. 若要测试公开键盘焦点，请运行放大镜。 （若要打开它，请单击“开始”菜单，依次指向“程序”、“附件”和“辅助功能”，然后单击“放大镜”）。 使用键盘 Tab 键和鼠标导航用户界面。 确保在“放大镜”中正确跟踪所有导航。

5. 若要测试公开屏幕元素，请运行检查并使用鼠标和 Tab 键选中每个元素。 确保“检查”窗口中名称、状态、角色、位置和值字段中显示的信息对于 UI 中每个对象的用户都有意义。
