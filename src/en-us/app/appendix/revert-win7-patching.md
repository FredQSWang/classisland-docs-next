# Windows 7 Rolling Back Repair Way

We've discovered that the previous method of setting Environment Variables can cause some .NET Core Applications, such as Seewo Easinote, to fail. Users who previously installed the .NET 8 version of ClassIsland on Windows 7 and installed the Memory Leak Fix should uninstall the fix and install the .NET 6 Compatible Version of ClassIsland.
The specific steps are as follows:

1. Run `Powershell` **as Administrator** and then run the following command to delete the Environment Variables you set previously:

    ``` powershell
    [System.Environment]::SetEnvironmentVariable("DOTNET_GCName", $null, "User")
    [System.Environment]::SetEnvironmentVariable("DOTNET_GCName", $null, "Machine")
    [System.Environment]::SetEnvironmentVariable("DOTNET_EnableWriteXorExecute", $null, "User")
    [System.Environment]::SetEnvironmentVariable("DOTNET_EnableWriteXorExecute", $null, "Machine")
    ```

2. Restart your computer

3. 按照文章[安装与开始](../setup.md#检查系统需求)的方法安装 .NET 6 版本的 ClassIsland，替换原来 .NET 8 版本的 ClassIsland。只需替换 `ClassIsland.exe` ，不需要操作其它文件。

Follow the instructions in the article [Installation & Getting Started](../setup.md#Check System Requirements) to install the .NET 6 Version of ClassIsland, replacing the original .NET 8 Version of ClassIsland. You only need to replace `ClassIsland.exe`; no other files need to be modified.
