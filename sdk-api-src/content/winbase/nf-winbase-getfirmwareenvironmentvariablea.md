---
UID: NF:winbase.GetFirmwareEnvironmentVariableA
title: GetFirmwareEnvironmentVariableA function (winbase.h)
description: Retrieves the value of the specified firmware environment variable.
helpviewer_keywords: ["GetFirmwareEnvironmentVariable","GetFirmwareEnvironmentVariable function","GetFirmwareEnvironmentVariableA","GetFirmwareEnvironmentVariableW","base.getfirmwareenvironmentvariable","winbase/GetFirmwareEnvironmentVariable","winbase/GetFirmwareEnvironmentVariableA","winbase/GetFirmwareEnvironmentVariableW"]
old-location: base\getfirmwareenvironmentvariable.htm
tech.root: winprog
ms.assetid: 18e74e54-ecfe-46bf-8c9d-9eb16d22f3ba
ms.date: 12/05/2018
ms.keywords: GetFirmwareEnvironmentVariable, GetFirmwareEnvironmentVariable function, GetFirmwareEnvironmentVariableA, GetFirmwareEnvironmentVariableW, base.getfirmwareenvironmentvariable, winbase/GetFirmwareEnvironmentVariable, winbase/GetFirmwareEnvironmentVariableA, winbase/GetFirmwareEnvironmentVariableW
req.header: winbase.h
req.include-header: Windows.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista, Windows XP with SP1 [desktop apps \| UWP apps]
req.target-min-winversvr: Windows Server 2003 [desktop apps \| UWP apps]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: GetFirmwareEnvironmentVariableW (Unicode) and GetFirmwareEnvironmentVariableA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Kernel32.lib
req.dll: Kernel32.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - GetFirmwareEnvironmentVariableA
 - winbase/GetFirmwareEnvironmentVariableA
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Kernel32.dll
 - API-MS-Win-Core-firmware-l1-1-0.dll
 - kernel32legacy.dll
 - API-MS-Win-DownLevel-Kernel32-l2-1-0.dll
api_name:
 - GetFirmwareEnvironmentVariable
 - GetFirmwareEnvironmentVariableA
 - GetFirmwareEnvironmentVariableW
---

# GetFirmwareEnvironmentVariableA function


## -description

Retrieves the value of the specified firmware environment variable.

## -parameters

### -param lpName [in]

The name of the firmware environment variable. The pointer must not be <b>NULL</b>.

### -param lpGuid [in]

The GUID that represents the namespace of the firmware environment variable. The GUID must be  a string in the format  "{<i>xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx</i>}" where 'x' represents a hexadecimal value.

### -param pBuffer [out]

A pointer to a buffer that receives the value of the specified firmware environment variable.

### -param nSize [in]

The size of the <i>pBuffer</i> buffer, in bytes.

## -returns

If the function succeeds, the return value is the number of bytes stored in the <i>pBuffer</i> buffer.

If the function fails, the return value is zero. To get extended error information, call 
<a href="https://docs.microsoft.com/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror">GetLastError</a>. Possible error codes include ERROR_INVALID_FUNCTION.

## -remarks

Starting with Windows 10, version 1803, Universal Windows apps can read and write Unified Extensible Firmware Interface (UEFI) firmware variables. See <a href="https://docs.microsoft.com/windows/desktop/SysInfo/access-uefi-firmware-variables-from-a-universal-windows-app">Access UEFI firmware variables from a Universal Windows App</a>for details.

To read a firmware environment variable, the user account that the app is running under must have the <a href="https://docs.microsoft.com/windows/desktop/SecAuthZ/privilege-constants">SE_SYSTEM_ENVIRONMENT_NAME</a> privilege. A Universal Windows app must be run from an administrator account and follow the requirements outlined in <a href="https://docs.microsoft.com/windows/desktop/SysInfo/access-uefi-firmware-variables-from-a-universal-windows-app">Access UEFI firmware variables from a Universal Windows App</a>.

Starting with Windows 10, version 1803, reading Unified Extensible Firmware Interface (UEFI) variables is also supported from User-Mode Driver Framework (UMDF) drivers. Writing UEFI variables from UMDF drivers is not supported.

The exact set of firmware environment variables is determined by the boot firmware. The location of these environment variables is also specified by the firmware.  For example, on a UEFI-based system, NVRAM contains firmware environment variables that specify system boot settings. For information about specific variables used, see the <a href="https://www.uefi.org/specifications">UEFI specification</a>. For more information about UEFI and Windows, see <a href="https://docs.microsoft.com/windows-hardware/drivers/bringup/uefi-in-windows">UEFI and Windows</a>.

Firmware variables are not supported on a legacy BIOS-based system. The <b>GetFirmwareEnvironmentVariable</b> function will always fail on a legacy BIOS-based system, or if Windows was installed using legacy BIOS on a system that supports both legacy BIOS and UEFI. To identify these conditions, call the function with a dummy firmware environment name such as an empty string ("") for the <i>lpName</i> parameter and a dummy GUID such as "{00000000-0000-0000-0000-000000000000}" for the <i>lpGuid</i> parameter. On a legacy BIOS-based system, or on a system that supports both legacy BIOS and UEFI where Windows was installed using legacy BIOS, the function will fail with  ERROR_INVALID_FUNCTION. On a UEFI-based system, the function will  fail with an error specific to the firmware, such as ERROR_NOACCESS, to indicate that the dummy GUID namespace does not exist. 

If you are creating a backup application, you can use this function to save all the boot settings for the system so they can be restored using the <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-setfirmwareenvironmentvariablea">SetFirmwareEnvironmentVariable</a> 
	 function if needed. 

<b>GetFirmwareEnvironmentVariable</b> is the user-mode equivalent of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exgetfirmwareenvironmentvariable">ExGetFirmwareEnvironmentVariable</a> kernel-mode routine.





> [!NOTE]
> The winbase.h header defines GetFirmwareEnvironmentVariable as an alias which automatically selects the ANSI or Unicode version of this function based on the definition of the UNICODE preprocessor constant. Mixing usage of the encoding-neutral alias with code that not encoding-neutral can lead to mismatches that result in compilation or runtime errors. For more information, see [Conventions for Function Prototypes](/windows/win32/intl/conventions-for-function-prototypes).

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/SysInfo/access-uefi-firmware-variables-from-a-universal-windows-app">Access UEFI firmware variables from a Universal Windows App</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-getfirmwareenvironmentvariableexa">GetFirmwareEnvironmentVariableEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-setfirmwareenvironmentvariablea">SetFirmwareEnvironmentVariable</a>



<a href="https://docs.microsoft.com/windows/desktop/SysInfo/system-information-functions">System
		  Information Functions</a>

