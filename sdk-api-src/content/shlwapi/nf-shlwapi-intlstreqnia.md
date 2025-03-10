---
UID: NF:shlwapi.IntlStrEqNIA
title: IntlStrEqNIA macro (shlwapi.h)
description: Performs a case-insensitive comparison of a specified number of characters from the beginning of two localized strings.
helpviewer_keywords: ["IntlStrEqNI","IntlStrEqNI function [Windows Shell]","IntlStrEqNIA","IntlStrEqNIW","_win32_IntlStrEqNI","shell.IntlStrEqNI","shlwapi/IntlStrEqNI","shlwapi/IntlStrEqNIA","shlwapi/IntlStrEqNIW"]
old-location: shell\IntlStrEqNI.htm
tech.root: shell
ms.assetid: 3d201726-b24a-4739-84fb-49b54d3f0f07
ms.date: 12/05/2018
ms.keywords: IntlStrEqNI, IntlStrEqNI function [Windows Shell], IntlStrEqNIA, IntlStrEqNIW, _win32_IntlStrEqNI, shell.IntlStrEqNI, shlwapi/IntlStrEqNI, shlwapi/IntlStrEqNIA, shlwapi/IntlStrEqNIW
req.header: shlwapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 Professional, Windows XP [desktop apps only]
req.target-min-winversvr: Windows 2000 Server [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: IntlStrEqNIW (Unicode) and IntlStrEqNIA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Shlwapi.lib
req.dll: Shlwapi.dll (version 5.0 or later)
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - IntlStrEqNIA
 - shlwapi/IntlStrEqNIA
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Shlwapi.dll
api_name:
 - IntlStrEqNI
 - IntlStrEqNIA
 - IntlStrEqNIW
---

# IntlStrEqNIA macro


## -description

Performs a case-insensitive comparison of a specified number of characters from the beginning of two localized strings.

## -parameters

### -param s1 [in]

Type: <b>LPCTSTR</b>

A pointer to a null-terminated string.

### -param s2 [in]

Type: <b>LPCTSTR</b>

A pointer to a null-terminated string.

### -param nChar [in]

Type: <b>int</b>

The number of characters to be compared, starting from the beginning of the strings.

## -remarks

This function retrieves the thread locale and uses <a href="https://docs.microsoft.com/windows/desktop/api/stringapiset/nf-stringapiset-comparestringw">CompareString</a> to do a case-insensitive comparison of the first <i>nChar</i> characters. It is equivalent to:

<pre class="syntax" xml:space="preserve"><code>IntlStrEqWorker(FALSE, pszStr1, pszStr2, nChar)</code></pre>




> [!NOTE]
> The shlwapi.h header defines IntlStrEqNI as an alias which automatically selects the ANSI or Unicode version of this function based on the definition of the UNICODE preprocessor constant. Mixing usage of the encoding-neutral alias with code that not encoding-neutral can lead to mismatches that result in compilation or runtime errors. For more information, see [Conventions for Function Prototypes](/windows/win32/intl/conventions-for-function-prototypes).

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/shlwapi/nf-shlwapi-intlstreqworkera">IntlStrEqWorker</a>

