# Take Command Console WinAPI Functions

[FindWindowClass](#FindWindowClass)  
[FindWindowTitle](#FindWindowTitle)  
[GetCurrentProcessID](#GetCurrentProcessID)  
[GetForegroundWindow](#GetForegroundWindow)  
[GetSystemMenu](#GetSystemMenu)  
[IsWindow](#IsWindow)  
[OpenClipboard](#OpenClipboard)  
[StrFormatByteSize](#StrFormatByteSize)  

<a name=FindWindowClass>
FindWindowClass
</a>

#### FindWindowClass=%@winapi[user32,FindWindow,"%$",0]

Examples:

```
echo %@FindWindowClass[Shell_TrayWnd]
65690

echo %@FindWindowClass[Notepad]
1379358

echo %@FindWindowClass[Progman]
65818
```
---
<a name=FindWindowTitle>
FindWindowTitle
</a>

#### FindWindowTitle=%@winapi[user32,FindWindow,0,"%$"]

Examples:
```
echo %@FindWindowTitle[Untitled - Notepad]
1379358

echo %@FindWindowTitle[Admin: Take Command Console]
394834

echo %@FindWindowTitle[%_winfgwindow]
394834

echo %@findwindowtitle[%_wintitle]
394834

echo %@findwindowtitle[Start]
65938
```
---
<a name="GetCurrentProcessID">
GetCurrentProcessID
</a>

#### GetCurrentProcessID=%@winapi[kernel32.dll,GetCurrentProcessId]

Example:
```
echo %@GetCurrentProcessID[]
14640
```
---
<a name="GetForegroundWindow">
GetForegroundWindow
</a>

#### GetForegroundWindow=%@winapi[user32.dll,GetForegroundWindow]

Example:
```
echo %@GetForegroundWindow[]
394834
```

---
<a name="GetSystemMenu">
GetSystemMenu
</a>

#### GetSystemMenu=%@winapi[user32.dll,GetSystemMenu,%1,0]

Examples:
```
set hWnd=%@GetForegroundWindow[]
echo %hwnd
394834

echo %@GetSystemMenu[%hwnd]
198257
```

---
<a name="IsWindow">
IsWindow
</a>

#### IsWindow=%@winapi[user32.dll,IsWindow,%1]

Example:
```
set fgWnd=%@getforegroundwindow[]
echo %@IsWindow[%fgWnd]
1
```

---
<a name="OpenClipboard">
OpenClipboard
</a>

#### OpenClipboard=%@winapi[user32.dll,OpenClipboard,0]

Example:
```
echo %@winapi[user32.dll,OpenClipboard,0]
1
```

If the function succeeds, the return value is non-zero.  
If the function fails, the return value is zero.

---
<a name="StrFormatByteSize">
StrFormatByteSize
</a>

#### StrFormatByteSize=%@winapi[shlwapi.dll,StrFormatByteSizeA,%1,aBUFFER,256]

Examples:
```
echo %@StrFormatByteSize[1024]
1.00 KB

echo %@StrFormatByteSize[10240]
10.0 KB

echo %@StrFormatByteSize[102400]
100 KB

echo %@StrFormatByteSize[1024000]
0.97 MB

echo %@StrFormatByteSize[10240000]
9.76 MB
```