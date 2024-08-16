---
label: Setting up the Engine
description: "FNF: Doido Engine Documentation"
---

# Setting up the Engine

## Dependencies
All platforms:
- [git-scm](https://git-scm.com/)
- [Haxe (4.3.3 or greater)](https://haxe.org/)

Windows Only:
- Microsoft Visual Studio Community (Refer to step 3 of setup for installation tutorial)

## First setup
1. Install `git-scm` and `Haxe`

2. Setup platform
- **Windows:** Run the following commands
```
cd ..
curl -# -O https://download.visualstudio.microsoft.com/download/pr/3105fcfe-e771-41d6-9a1c-fc971e7d03a7/8eb13958dc429a6e6f7e0d6704d43a55f18d02a253608351b6bf6723ffdaf24e/vs_Community.exe
vs_Community.exe --add Microsoft.VisualStudio.Component.VC.Tools.x86.x64 --add Microsoft.VisualStudio.Component.Windows10SDK.19041 -p
del vs_Community.exe
```
3. Open up any terminal in the engine folder (such as CMD or Powershell) and run the following commands
```
haxelib install lime 8.1.2
haxelib install openfl 9.3.3
haxelib install flixel 5.8.0
haxelib install flixel-addons 3.2.2
haxelib install flixel-ui 2.6.1
haxelib install flxanimate 3.0.4
haxelib git hxdiscord_rpc https://github.com/MAJigsaw77/hxdiscord_rpc
haxelib run lime setup 
```
4. Build the game
- Run the command `lime test PLATFORM`, where platform is where you are building the engine for (ex: Windows, HTML5, Linux)
- First time you build the engine will take longer than usual, so don't worry and be patient!
