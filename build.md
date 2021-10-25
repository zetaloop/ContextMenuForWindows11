# project desc
1. ContextMenuCustomHost project read the menu item (json) from "LocalState\custom_commands", and then display it as a secondary menu
2. ContextMenuCustomApp project is used to configure the menu items
3. ContextMenuCustomPackage project is used to support "runFullTrust"

# how to build

## build ContextMenuCustomHost
1. isntall nuget package: Microsoft.Windows.CppWinRT and Microsoft.Windows.ImplementationLibrary
2. clean project, select debug or release,repeat this step every time you modify the configuration   
(you can change the output to ContextMenuCustomApp debug or release bin folder)

## build ContextMenuCustomApp
1. just build

## build ContextMenuCustomPackage
1. set this project as startup project
2. build and run

# publish
1. clean all
2. select release,rebuild ContextMenuCustomHost project
3. publish on ContextMenuCustomPackage

# install
1. install vc++ runtime  (Visual Studio 2015, 2017, 2019, and 2022)   
https://docs.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-160

2. deploy

run in powershell
```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

./Install.ps1

Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope CurrentUser
```