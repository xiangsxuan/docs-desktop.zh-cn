---
title: 更安全的文件和数据访问
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [Windows Forms], file access
- registry [Windows Forms]
- data access [Windows Forms]
- database access (Windows Forms security)
- data [Windows Forms], secure access
- file access [Windows Forms]
- security [Windows Forms], data access
ms.assetid: 3cd3e55b-2f5e-40dd-835d-f50f7ce08967
ms.openlocfilehash: 880b5414143b827dabb0ff1fb0a16649ace5a035
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972731"
---
# <a name="more-secure-file-and-data-access-in-windows-forms"></a><span data-ttu-id="4ff1d-102">Windows 窗体中更加安全的文件和数据访问</span><span class="sxs-lookup"><span data-stu-id="4ff1d-102">More Secure File and Data Access in Windows Forms</span></span>

<span data-ttu-id="4ff1d-103">.NET Framework 使用权限来帮助保护资源和数据。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-103">The .NET Framework uses permissions to help protect resources and data.</span></span> <span data-ttu-id="4ff1d-104">你的应用程序可以读取或写入数据的位置取决于授予该应用程序的权限。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-104">Where your application can read or write data depends on the permissions granted to the application.</span></span> <span data-ttu-id="4ff1d-105">在部分信任环境中运行应用程序时，可能不具有对数据的访问权限，或可能必须更改访问数据的方式。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-105">When your application runs in a partial trust environment, you might not have access to your data or you might have to change the way you access the data.</span></span>  
  
 <span data-ttu-id="4ff1d-106">遇到安全限制时，你有两个选择：断言该权限（假设已将该权限授予你的应用程序），或者使用编写为用于部分信任中的功能版本。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-106">When you encounter a security restriction, you have two options: assert the permission (assuming it has been granted to your application), or use a version of the feature written to work in partial trust.</span></span> <span data-ttu-id="4ff1d-107">以下各节探讨如何使用文件、数据库和在部分信任环境中运行的应用程序中的注册表访问。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-107">The following sections discuss how to work with file, database, and registry access from applications that are running in a partial trust environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ff1d-108">默认情况下，生成 ClickOnce 部署的工具默认情况下，这些部署从运行它们的计算机请求完全信任。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-108">By default, tools that generate ClickOnce deployments default these deployments to requesting Full Trust from the computers on which they run.</span></span> <span data-ttu-id="4ff1d-109">如果你决定要在部分信任环境中运行所增加的安全优势，则必须在 Visual Studio 或 Windows SDK 工具之一 ( # A0 或 MageUI.exe) 中更改此默认值。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-109">If you decide you want the added security benefits of running in partial trust, you must change this default in either Visual Studio or one of the Windows SDK tools (Mage.exe or MageUI.exe).</span></span> <span data-ttu-id="4ff1d-110">有关 Windows 窗体安全性以及如何确定应用程序的适当信任级别的详细信息，请参阅 [Windows 窗体概述中的安全性](security-in-windows-forms-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-110">For more information about Windows Forms security, and on how to determine the appropriate trust level for your application, see [Security in Windows Forms Overview](security-in-windows-forms-overview.md).</span></span>  
  
## <a name="file-access"></a><span data-ttu-id="4ff1d-111">文件访问</span><span class="sxs-lookup"><span data-stu-id="4ff1d-111">File Access</span></span>  

 <span data-ttu-id="4ff1d-112"><xref:System.Security.Permissions.FileIOPermission>类控制 .NET Framework 中的文件和文件夹访问。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-112">The <xref:System.Security.Permissions.FileIOPermission> class controls file and folder access in the .NET Framework.</span></span> <span data-ttu-id="4ff1d-113">默认情况下，安全系统不会向本地 Intranet 和 Internet 区域等部分信任环境授予 <xref:System.Security.Permissions.FileIOPermission>。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-113">By default, the security system does not grant the <xref:System.Security.Permissions.FileIOPermission> to partial trust environments such as the local intranet and Internet zones.</span></span> <span data-ttu-id="4ff1d-114">但是，如果修改应用程序的设计或使用不同的方法访问文件，那么需要文件访问权限的应用程序仍可以在这些环境中正常工作。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-114">However, an application that requires file access can still function in these environments if you modify the design of your application or use different methods to access files.</span></span> <span data-ttu-id="4ff1d-115">默认情况下，将向本地 Intranet 区域授予以下权限：具有相同的站点访问权限和相同的目录访问权限、连回其源站点、从其安装目录进行读取。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-115">By default, the local intranet zone is granted the right to have same site access and same directory access, to connect back to the site of its origin, and to read from its installation directory.</span></span> <span data-ttu-id="4ff1d-116">默认情况下，仅向 Internet 区域授予连回其源站点的权限。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-116">By default, the Internet zone, is only granted the right to connect back to the site of its origin.</span></span>  
  
### <a name="user-specified-files"></a><span data-ttu-id="4ff1d-117">用户指定的文件</span><span class="sxs-lookup"><span data-stu-id="4ff1d-117">User-Specified Files</span></span>  

 <span data-ttu-id="4ff1d-118">针对不具有文件访问权限的一种应对方法是：提示用户通过使用 <xref:System.Windows.Forms.OpenFileDialog> 或 <xref:System.Windows.Forms.SaveFileDialog> 类提供特定文件信息。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-118">One way to deal with not having file access permission is to prompt the user to provide specific file information by using the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> class.</span></span> <span data-ttu-id="4ff1d-119">这种用户交互有助于在一定程度上确保应用程序无法恶意加载专用文件或覆盖重要文件。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-119">This user interaction helps provide some assurance that the application cannot maliciously load private files or overwrite important files.</span></span> <span data-ttu-id="4ff1d-120"><xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 和 <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 方法通过打开用户指定的文件的文件流提供读写文件访问权限。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-120">The <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> and <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> methods provide read and write file access by opening the file stream for the file that the user specified.</span></span> <span data-ttu-id="4ff1d-121">这些方法还有助于通过隐藏文件路径保护用户文件。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-121">The methods also help protect the user's file by obscuring the file's path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ff1d-122">这些权限根据应用程序是位于 Internet 区域中还是 Intranet 区域中而有所不同。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-122">These permissions differ depending on whether your application is in the Internet zone or Intranet zone.</span></span> <span data-ttu-id="4ff1d-123">Internet 区域的应用程序只能使用 <xref:System.Windows.Forms.OpenFileDialog>，而 Intranet 应用程序则具有不受限制的文件对话框权限。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-123">Internet zone applications can only use the <xref:System.Windows.Forms.OpenFileDialog>, whereas Intranet applications have unrestricted file dialog permission.</span></span>  
  
 <span data-ttu-id="4ff1d-124"><xref:System.Security.Permissions.FileDialogPermission> 类指定应用程序可使用的文件对话框类型。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-124">The <xref:System.Security.Permissions.FileDialogPermission> class specifies what type of file dialog box your application can use.</span></span> <span data-ttu-id="4ff1d-125">下表显示使用每种 <xref:System.Windows.Forms.FileDialog> 类所必须具有的值。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-125">The following table shows the value you must have to use each <xref:System.Windows.Forms.FileDialog> class.</span></span>  
  
|<span data-ttu-id="4ff1d-126">类</span><span class="sxs-lookup"><span data-stu-id="4ff1d-126">Class</span></span>|<span data-ttu-id="4ff1d-127">所需的访问值</span><span class="sxs-lookup"><span data-stu-id="4ff1d-127">Required access value</span></span>|  
|-----------|---------------------------|  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Open>|  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Save>|  
  
> [!NOTE]
> <span data-ttu-id="4ff1d-128">实际调用 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 方法前并不需要这一特定权限。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-128">The specific permission is not requested until the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is actually called.</span></span>  
  
 <span data-ttu-id="4ff1d-129">显示文件对话框的权限不会授予应用程序对 <xref:System.Windows.Forms.FileDialog>、<xref:System.Windows.Forms.OpenFileDialog> 和 <xref:System.Windows.Forms.SaveFileDialog> 类所有成员的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-129">Permission to display a file dialog box does not grant your application full access to all members of the <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog>, and <xref:System.Windows.Forms.SaveFileDialog> classes.</span></span> <span data-ttu-id="4ff1d-130">有关调用每个方法所需的确切权限，请参阅 .NET Framework 类库文档中该方法的参考主题。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-130">For the exact permissions that are required to call each method, see the reference topic for that method in the .NET Framework class library documentation.</span></span>  
  
 <span data-ttu-id="4ff1d-131">以下代码示例使用 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 方法将用户指定的文件打开为 <xref:System.Windows.Forms.RichTextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-131">The following code example uses the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open a user-specified file into a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="4ff1d-132">该示例需要 <xref:System.Security.Permissions.FileDialogPermission> 和关联的 <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> 枚举值。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-132">The example requires <xref:System.Security.Permissions.FileDialogPermission> and the associated <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> enumeration value.</span></span> <span data-ttu-id="4ff1d-133">该示例演示如何处理 <xref:System.Security.SecurityException> 以确定是否应禁用保存功能。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-133">The example demonstrates how to handle the <xref:System.Security.SecurityException> to determine whether the save feature should be disabled.</span></span> <span data-ttu-id="4ff1d-134">此示例要求你的 <xref:System.Windows.Forms.Form> 具有名为 `ButtonOpen` 的 <xref:System.Windows.Forms.Button> 控件和名为 `RtfBoxMain` 的 <xref:System.Windows.Forms.RichTextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-134">This example requires that your <xref:System.Windows.Forms.Form> has a <xref:System.Windows.Forms.Button> control named `ButtonOpen`, and a <xref:System.Windows.Forms.RichTextBox> control named `RtfBoxMain`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ff1d-135">在示例中未展示保存功能的编程逻辑。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-135">The programming logic for the save feature is not shown in the example.</span></span>  
  
```vb  
Private Sub ButtonOpen_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles ButtonOpen.Click
  
    Dim editingFileName as String = ""  
    Dim saveAllowed As Boolean = True  
  
    ' Displays the OpenFileDialog.  
    If (OpenFileDialog1.ShowDialog() = DialogResult.OK) Then  
        Dim userStream as System.IO.Stream  
        Try
            ' Opens the file stream for the file selected by the user.  
            userStream =OpenFileDialog1.OpenFile()
            Me.RtfBoxMain.LoadFile(userStream, _  
                RichTextBoxStreamType.PlainText)  
        Finally  
            userStream.Close()  
        End Try  
  
        ' Tries to get the file name selected by the user.  
        ' Failure means that the application does not have  
        ' unrestricted permission to the file.  
        Try
            editingFileName = OpenFileDialog1.FileName  
        Catch ex As Exception  
            If TypeOf ex Is System.Security.SecurityException Then
                ' The application does not have unrestricted permission
                ' to the file so the save feature will be disabled.  
                saveAllowed = False
            Else
                Throw ex  
            End If  
        End Try  
    End If  
End Sub  
```  
  
```csharp  
private void ButtonOpen_Click(object sender, System.EventArgs e)
{  
    String editingFileName = "";  
    Boolean saveAllowed = true;  
  
    // Displays the OpenFileDialog.  
    if (openFileDialog1.ShowDialog() == DialogResult.OK)
    {  
        // Opens the file stream for the file selected by the user.  
        using (System.IO.Stream userStream = openFileDialog1.OpenFile())
        {  
            this.RtfBoxMain.LoadFile(userStream,  
                RichTextBoxStreamType.PlainText);  
            userStream.Close();  
        }  
  
        // Tries to get the file name selected by the user.  
        // Failure means that the application does not have  
        // unrestricted permission to the file.  
        try
        {  
            editingFileName = openFileDialog1.FileName;  
        }
        catch (Exception ex)
        {  
            if (ex is System.Security.SecurityException)
            {  
                // The application does not have unrestricted permission
                // to the file so the save feature will be disabled.  
                saveAllowed = false;
            }
            else
            {  
                throw ex;  
            }  
        }  
    }  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="4ff1d-136">在 Visual c # 中，确保添加代码以启用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-136">In Visual C#, ensure that you add code to enable the event handler.</span></span> <span data-ttu-id="4ff1d-137">通过使用上一示例中的代码，以下代码显示了如何启用事件处理程序。`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span><span class="sxs-lookup"><span data-stu-id="4ff1d-137">By using the code from the previous example, the following code shows how to enable the event handler.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span></span>  
  
### <a name="other-files"></a><span data-ttu-id="4ff1d-138">其他文件</span><span class="sxs-lookup"><span data-stu-id="4ff1d-138">Other Files</span></span>  

 <span data-ttu-id="4ff1d-139">有时你将需要读取或写入到用户未指定的文件，例如当你必须保存应用程序设置时。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-139">Sometimes you will need to read or write to files that the user does not specify, such as when you must persist application settings.</span></span> <span data-ttu-id="4ff1d-140">在本地 Intranet 和 Internet 区域中，你的应用程序将无权在本地文件中存储数据。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-140">In the local intranet and Internet zones, your application will not have permission to store data in a local file.</span></span> <span data-ttu-id="4ff1d-141">但是，它将能够在独立存储中存储数据。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-141">However, your application will be able to store data in isolated storage.</span></span> <span data-ttu-id="4ff1d-142">独立存储是一个抽象的数据隔离舱（而非具体的存储位置），它包含一个或多个独立存储文件（称为存储区），这些文件包含存储数据的实际目录位置。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-142">Isolated storage is an abstract data compartment (not a specific storage location) that contains one or more isolated storage files, called stores, that contain the actual directory locations where data is stored.</span></span> <span data-ttu-id="4ff1d-143">文件访问权限（如 <xref:System.Security.Permissions.FileIOPermission>）不是必须具有的权限；<xref:System.Security.Permissions.IsolatedStoragePermission> 类控制独立存储权限。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-143">File access permissions like <xref:System.Security.Permissions.FileIOPermission> are not required; instead, the <xref:System.Security.Permissions.IsolatedStoragePermission> class controls the permissions for isolated storage.</span></span> <span data-ttu-id="4ff1d-144">默认情况下，在本地 Intranet 和 Internet 区域中运行的应用程序可以使用独立存储来存储数据；但是，磁盘配额等设置可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-144">By default, applications that are running in the local intranet and Internet zones can store data using isolated storage; however, settings like disk quota can vary.</span></span> <span data-ttu-id="4ff1d-145">有关独立存储的详细信息，请参阅 [独立存储](/dotnet/standard/io/isolated-storage)。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-145">For more information about isolated storage, see [Isolated Storage](/dotnet/standard/io/isolated-storage).</span></span>  
  
 <span data-ttu-id="4ff1d-146">下面的示例使用独立存储将数据写入位于某个存储区中的文件。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-146">The following example uses isolated storage to write data to a file located in a store.</span></span> <span data-ttu-id="4ff1d-147">该示例需要 <xref:System.Security.Permissions.IsolatedStorageFilePermission> 和 <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> 枚举值。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-147">The example requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> and the <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> enumeration value.</span></span> <span data-ttu-id="4ff1d-148">该示例演示了将 <xref:System.Windows.Forms.Button> 控件的某些属性值读取和写入到独立存储中的文件。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-148">The example demonstrates reading and writing certain property values of the <xref:System.Windows.Forms.Button> control to a file in isolated storage.</span></span> <span data-ttu-id="4ff1d-149">应用程序启动后将调用 `Read` 函数，将在应用程序结束之前调用 `Write` 函数。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-149">The `Read` function would be called after the application starts and the `Write` function would be called before the application ends.</span></span> <span data-ttu-id="4ff1d-150">该示例要求 `Read` 和 `Write` 函数作为的成员存在 <xref:System.Windows.Forms.Form> ，其中包含 <xref:System.Windows.Forms.Button> 名为的控件 `MainButton` 。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-150">The example requires that the `Read` and `Write` functions exist as members of a <xref:System.Windows.Forms.Form> that contains a <xref:System.Windows.Forms.Button> control named `MainButton`.</span></span>  
  
```vb  
' Reads the button options from the isolated storage. Uses Default values
' for the button if the options file does not exist.  
Public Sub Read()
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try  
        ' Checks to see if the options.txt file exists.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
  
            ' Opens the file because it exists.  
            Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _
                 (filename, IO.FileMode.Open,isoStore)  
            Dim reader as System.IO.StreamReader  
            Try
                reader = new System.IO.StreamReader(isos)  
  
                ' Reads the values stored.  
                Dim converter As System.ComponentModel.TypeConverter  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _
                    (GetType(Color))  
  
                Me.MainButton.BackColor = _
                        CType(converter.ConvertFromString _
                         (reader.ReadLine()), Color)  
                me.MainButton.ForeColor = _  
                        CType(converter.ConvertFromString _
                         (reader.ReadLine()), Color)  
  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _
                    (GetType(Font))  
                me.MainButton.Font = _  
                        CType(converter.ConvertFromString _
                         (reader.ReadLine()), Font)  
  
            Catch ex As Exception  
                Debug.WriteLine("Cannot read options " + _  
                    ex.ToString())  
            Finally  
                reader.Close()  
            End Try  
        End If  
  
    Catch ex As Exception  
        Debug.WriteLine("Cannot read options " + ex.ToString())  
    End Try  
End Sub  
  
' Writes the button options to the isolated storage.  
Public Sub Write()
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try
        ' Checks if the file exists, and if it does, tries to delete it.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
            isoStore.DeleteFile(filename)  
        End If  
    Catch ex As Exception  
        Debug.WriteLine("Cannot delete file " + ex.ToString())  
    End Try  
  
    ' Creates the options.txt file and writes the button options to it.  
    Dim writer as System.IO.StreamWriter  
    Try
        Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _
             (filename, IO.FileMode.CreateNew, isoStore)  
  
        writer = New System.IO.StreamWriter(isos)  
        Dim converter As System.ComponentModel.TypeConverter  
  
        converter = System.ComponentModel.TypeDescriptor.GetConverter _
           (GetType(Color))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.BackColor))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.ForeColor))  
  
        converter = System.ComponentModel TypeDescriptor.GetConverter _
           (GetType(Font))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.Font))  
  
    Catch ex as Exception  
        Debug.WriteLine("Cannot write options " + ex.ToString())  
  
    Finally  
        writer.Close()  
    End Try  
End Sub  
```  
  
```csharp  
// Reads the button options from the isolated storage. Uses default values
// for the button if the options file does not exist.  
public void Read()
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try  
    {  
        // Checks to see if the options.txt file exists.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)
        {  
            // Opens the file because it exists.  
            System.IO.IsolatedStorage.IsolatedStorageFileStream isos =
                new System.IO.IsolatedStorage.IsolatedStorageFileStream  
                    (filename, System.IO.FileMode.Open,isoStore);  
            System.IO.StreamReader reader = null;  
            try
            {  
                reader = new System.IO.StreamReader(isos);  
  
                // Reads the values stored.  
                TypeConverter converter ;  
                converter = TypeDescriptor.GetConverter(typeof(Color));  
  
                this.MainButton.BackColor =
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
                this.MainButton.ForeColor =
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
  
                converter = TypeDescriptor.GetConverter(typeof(Font));  
                this.MainButton.Font =
                  (Font)(converter.ConvertFromString(reader.ReadLine()));  
            }  
            catch (Exception ex)  
            {
                System.Diagnostics.Debug.WriteLine  
                     ("Cannot read options " + ex.ToString());  
            }  
            finally  
            {  
                reader.Close();  
            }  
        }  
    }
    catch (Exception ex)
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot read options " + ex.ToString());  
    }  
}  
  
// Writes the button options to the isolated storage.  
public void Write()
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try
    {  
        // Checks if the file exists and, if it does, tries to delete it.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)
        {  
            isoStore.DeleteFile(filename);  
        }  
    }  
    catch (Exception ex)
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot delete file " + ex.ToString());  
    }  
  
    // Creates the options file and writes the button options to it.  
    System.IO.StreamWriter writer = null;  
    try
    {  
        System.IO.IsolatedStorage.IsolatedStorageFileStream isos = new
            System.IO.IsolatedStorage.IsolatedStorageFileStream(filename,
            System.IO.FileMode.CreateNew,isoStore);  
  
        writer = new System.IO.StreamWriter(isos);  
        TypeConverter converter ;  
  
        converter = TypeDescriptor.GetConverter(typeof(Color));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.BackColor));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.ForeColor));  
  
        converter = TypeDescriptor.GetConverter(typeof(Font));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.Font));  
  
    }  
    catch (Exception ex)  
    {
        System.Diagnostics.Debug.WriteLine  
           ("Cannot write options " + ex.ToString());  
    }  
    finally  
    {  
        writer.Close();  
    }  
}  
```  
  
## <a name="database-access"></a><span data-ttu-id="4ff1d-151">数据库访问</span><span class="sxs-lookup"><span data-stu-id="4ff1d-151">Database Access</span></span>  

 <span data-ttu-id="4ff1d-152">访问数据库所需的权限因数据库提供程序而异；但是，只有使用相应权限运行的应用程序可以通过数据连接访问数据库。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-152">The permissions required to access a database vary based on the database provider; however, only applications that are running with the appropriate permissions can access a database through a data connection.</span></span> <span data-ttu-id="4ff1d-153">有关访问数据库所需权限的详细信息，请参阅 [代码访问安全性和 ADO.NET](/dotnet/framework/data/adonet/code-access-security)。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-153">For more information about the permissions that are required to access a database, see [Code Access Security and ADO.NET](/dotnet/framework/data/adonet/code-access-security).</span></span>  
  
 <span data-ttu-id="4ff1d-154">如果因为要使应用程序以部分信任权限运行而不能直接访问数据库，作为一种替代方法，可将 Web 服务作为备份方法来访问你的数据。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-154">If you cannot directly access a database because you want your application to run in partial trust, you can use a Web service as an alternative means to access your data.</span></span> <span data-ttu-id="4ff1d-155">Web 服务是一种软件，可通过网络以编程方式进行访问。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-155">A Web service is a piece of software that can be programmatically accessed over a network.</span></span> <span data-ttu-id="4ff1d-156">通过 Web 服务，应用程序可以跨代码组区域共享数据。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-156">With Web services, applications can share data across code group zones.</span></span> <span data-ttu-id="4ff1d-157">默认情况下，本地 Intranet 和 Internet 区域中的应用程序被授予了访问其源站点的权限，使其能够调用同一台服务器上托管的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-157">By default, applications in the local intranet and Internet zones are granted the right to access their sites of origin, which enables them to call a Web service hosted on the same server.</span></span> <span data-ttu-id="4ff1d-158">有关详细信息，请参阅 ASP.NET AJAX 或[Windows Communication Foundation](/dotnet/framework/wcf/index)[中的 Web 服务](/previous-versions/aspnet/bb398785(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-158">For more information see [Web Services in ASP.NET AJAX](/previous-versions/aspnet/bb398785(v=vs.100)) or [Windows Communication Foundation](/dotnet/framework/wcf/index).</span></span>  
  
## <a name="registry-access"></a><span data-ttu-id="4ff1d-159">注册表访问</span><span class="sxs-lookup"><span data-stu-id="4ff1d-159">Registry Access</span></span>  

 <span data-ttu-id="4ff1d-160"><xref:System.Security.Permissions.RegistryPermission> 类控制对操作系统注册表的访问。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-160">The <xref:System.Security.Permissions.RegistryPermission> class controls access to the operating system registry.</span></span> <span data-ttu-id="4ff1d-161">默认情况下，只有在本地运行的应用程序可以访问注册表。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-161">By default, only applications that are running locally can access the registry.</span></span>  <span data-ttu-id="4ff1d-162"><xref:System.Security.Permissions.RegistryPermission> 仅授予应用程序尝试进行注册表访问的权限；它不保证访问一定成功，因为操作系统仍对注册表强制安全。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-162"><xref:System.Security.Permissions.RegistryPermission> only grants an application the right to try registry access; it does not guarantee access will succeed, because the operating system still enforces security on the registry.</span></span>  
  
 <span data-ttu-id="4ff1d-163">由于无法在部分信任环境下访问注册表，所以可能需要寻找其他方法来存储你的数据。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-163">Because you cannot access the registry under partial trust, you may need to find other methods of storing your data.</span></span> <span data-ttu-id="4ff1d-164">存储应用程序设置时，请使用独立存储而非注册表。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-164">When you store application settings, use isolated storage instead of the registry.</span></span> <span data-ttu-id="4ff1d-165">独立存储也可用于存储其他特定于应用程序的文件。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-165">Isolated storage can also be used to store other application-specific files.</span></span> <span data-ttu-id="4ff1d-166">由于默认授予了应用程序访问其源站点的权限，因此还可以存储有关服务器或源站点的全局应用程序信息。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-166">You can also store global application information about the server or site of origin, because by default an application is granted the right to access the site of its origin.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ff1d-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ff1d-167">See also</span></span>

- [<span data-ttu-id="4ff1d-168">Windows 窗体中的更加安全的打印</span><span class="sxs-lookup"><span data-stu-id="4ff1d-168">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)
- [<span data-ttu-id="4ff1d-169">Windows 窗体中额外的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="4ff1d-169">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="4ff1d-170">Windows 窗体中的安全性概述</span><span class="sxs-lookup"><span data-stu-id="4ff1d-170">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="4ff1d-171">Windows 窗体安全</span><span class="sxs-lookup"><span data-stu-id="4ff1d-171">Windows Forms Security</span></span>](windows-forms-security.md)
- [<span data-ttu-id="4ff1d-172">Mage.exe（清单生成和编辑工具）</span><span class="sxs-lookup"><span data-stu-id="4ff1d-172">Mage.exe (Manifest Generation and Editing Tool)</span></span>](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)
- [<span data-ttu-id="4ff1d-173">MageUI.exe（图形化客户端中的清单生成和编辑工具）</span><span class="sxs-lookup"><span data-stu-id="4ff1d-173">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)
