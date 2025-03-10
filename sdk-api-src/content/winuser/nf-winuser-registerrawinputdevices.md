---
UID: NF:winuser.RegisterRawInputDevices
title: RegisterRawInputDevices function (winuser.h)
description: Registers the devices that supply the raw input data.
helpviewer_keywords: ["RegisterRawInputDevices","RegisterRawInputDevices function [Keyboard and Mouse Input]","_win32_RegisterRawInputDevices","_win32_registerrawinputdevices_cpp","inputdev.registerrawinputdevices","winui._win32_registerrawinputdevices","winuser/RegisterRawInputDevices"]
old-location: inputdev\registerrawinputdevices.htm
tech.root: inputdev
ms.assetid: VS|winui|~\winui\windowsuserinterface\userinput\rawinput\rawinputreference\rawinputfunctions\registerrawinputdevices.htm
ms.date: 12/05/2018
ms.keywords: RegisterRawInputDevices, RegisterRawInputDevices function [Keyboard and Mouse Input], _win32_RegisterRawInputDevices, _win32_registerrawinputdevices_cpp, inputdev.registerrawinputdevices, winui._win32_registerrawinputdevices, winuser/RegisterRawInputDevices
req.header: winuser.h
req.include-header: Windows.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP [desktop apps only]
req.target-min-winversvr: Windows Server 2003 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: User32.lib
req.dll: User32.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - RegisterRawInputDevices
 - winuser/RegisterRawInputDevices
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - User32.dll
 - Ext-MS-Win-NTUser-Misc-l1-2-0.dll
 - Ext-MS-Win-NTUser-Misc-l1-3-0.dll
 - ext-ms-win-ntuser-misc-l1-3-1.dll
 - Ext-MS-Win-RTCore-NTUser-Rawinput-L1-1-0.dll
 - MinUser.dll
api_name:
 - RegisterRawInputDevices
---

# RegisterRawInputDevices function


## -description

Registers the devices that supply the raw input data.

## -parameters

### -param pRawInputDevices [in]

Type: <b>PCRAWINPUTDEVICE</b>

An array of <a href="https://docs.microsoft.com/windows/desktop/api/winuser/ns-winuser-rawinputdevice">RAWINPUTDEVICE</a> structures that represent the devices that supply the raw input.

### -param uiNumDevices [in]

Type: <b>UINT</b>

The number of <a href="https://docs.microsoft.com/windows/desktop/api/winuser/ns-winuser-rawinputdevice">RAWINPUTDEVICE</a> structures pointed to by <i>pRawInputDevices</i>.

### -param cbSize [in]

Type: <b>UINT</b>

The size, in bytes, of a <a href="https://docs.microsoft.com/windows/desktop/api/winuser/ns-winuser-rawinputdevice">RAWINPUTDEVICE</a> structure.

## -returns

Type: <b>BOOL</b>

<b>TRUE</b> if the function succeeds; otherwise, <b>FALSE</b>. If the function fails, call <a href="https://docs.microsoft.com/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror">GetLastError</a> for more information.

## -remarks

To receive <a href="https://docs.microsoft.com/windows/desktop/inputdev/wm-input">WM_INPUT</a> messages, an application must first register the raw input devices using <b>RegisterRawInputDevices</b>. By default, an application does not receive raw input.

To receive <a href="https://docs.microsoft.com/windows/desktop/inputdev/wm-input-device-change">WM_INPUT_DEVICE_CHANGE</a> messages, an application must specify the  RIDEV_DEVNOTIFY flag for each device class that is specified by the usUsagePage and usUsage fields of the  <a href="https://docs.microsoft.com/windows/desktop/api/winuser/ns-winuser-rawinputdevice">RAWINPUTDEVICE</a> structure  .  By default, an application does not receive  <b>WM_INPUT_DEVICE_CHANGE</b> notifications for raw input device arrival and removal.

If a <a href="https://docs.microsoft.com/windows/desktop/api/winuser/ns-winuser-rawinputdevice">RAWINPUTDEVICE</a> structure has the RIDEV_REMOVE flag set and the hwndTarget parameter is not set to NULL, then parameter validation will fail.

## -see-also

<b>Conceptual</b>



<a href="https://docs.microsoft.com/windows/desktop/api/winuser/ns-winuser-rawinputdevice">RAWINPUTDEVICE</a>



<a href="https://docs.microsoft.com/windows/desktop/inputdev/raw-input">Raw Input</a>



<b>Reference</b>



<a href="https://docs.microsoft.com/windows/desktop/inputdev/wm-input">WM_INPUT</a>

