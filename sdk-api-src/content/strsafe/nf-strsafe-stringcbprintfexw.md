---
UID: NF:strsafe.StringCbPrintfExW
title: StringCbPrintfExW function (strsafe.h)
description: Writes formatted data to the specified string.
helpviewer_keywords: ["STRSAFE_FILL_BEHIND_NULL","STRSAFE_FILL_ON_FAILURE","STRSAFE_IGNORE_NULLS","STRSAFE_NO_TRUNCATION","STRSAFE_NULL_ON_FAILURE","StringCbPrintfEx","StringCbPrintfEx function [Menus and Other Resources]","StringCbPrintfExA","StringCbPrintfExW","_shell_StringCbPrintfEx","_shell_stringcbprintfex_cpp","menurc.stringcbprintfex","strsafe/StringCbPrintfEx","strsafe/StringCbPrintfExA","strsafe/StringCbPrintfExW","winui._shell_stringcbprintfex"]
old-location: menurc\stringcbprintfex.htm
tech.root: menurc
ms.assetid: VS|winui|~\winui\windowsuserinterface\resources\strings\stringreference\stringfunctions\stringcbprintfex.htm
ms.date: 12/05/2018
ms.keywords: STRSAFE_FILL_BEHIND_NULL, STRSAFE_FILL_ON_FAILURE, STRSAFE_IGNORE_NULLS, STRSAFE_NO_TRUNCATION, STRSAFE_NULL_ON_FAILURE, StringCbPrintfEx, StringCbPrintfEx function [Menus and Other Resources], StringCbPrintfExA, StringCbPrintfExW, _shell_StringCbPrintfEx, _shell_stringcbprintfex_cpp, menurc.stringcbprintfex, strsafe/StringCbPrintfEx, strsafe/StringCbPrintfExA, strsafe/StringCbPrintfExW, winui._shell_stringcbprintfex
req.header: strsafe.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP with SP2 [desktop apps \| UWP apps]
req.target-min-winversvr: Windows Server 2003 with SP1 [desktop apps \| UWP apps]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: StringCbPrintfExW (Unicode) and StringCbPrintfExA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - StringCbPrintfExW
 - strsafe/StringCbPrintfExW
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Strsafe.h
api_name:
 - StringCbPrintfEx
 - StringCbPrintfExA
 - StringCbPrintfExW
---

# StringCbPrintfExW function


## -description

Writes formatted data to the specified string. The size of the destination buffer is provided to the function to ensure that it does not write past the end of this buffer.

<b>StringCbPrintfEx</b> adds to the functionality of <a href="https://docs.microsoft.com/windows/desktop/api/strsafe/nf-strsafe-stringcbprintfa">StringCbPrintf</a> by returning a pointer to the end of the destination string as well as the number of bytes left unused in that string. Flags may also be passed to the function for additional control.

<b>StringCbPrintfEx</b> is a replacement for the following functions:
<ul>
<li><a href="https://msdn.microsoft.com/library/ybk95axf.aspx">sprintf, swprintf, _stprintf</a></li>
<li>
<a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-wsprintfa">wsprintf</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows/desktop/api/shlwapi/nf-shlwapi-wnsprintfa">wnsprintf</a>
</li>
<li><a href="https://msdn.microsoft.com/library/2ts7cx93.aspx">_snprintf, _snwprintf, _sntprintf</a></li>
</ul>

## -parameters

### -param pszDest [out]

Type: <b>LPTSTR</b>

The destination buffer, which receives the formatted, null-terminated string created from <i>pszFormat</i> and its arguments.

### -param cbDest [in]

Type: <b>size_t</b>

The size of the destination buffer, in bytes. This value must be sufficiently large to accommodate the final formatted string plus the terminating null character. The maximum number of bytes allowed is <code>STRSAFE_MAX_CCH * sizeof(TCHAR)</code>.

### -param ppszDestEnd [out, optional]

Type: <b>LPTSTR*</b>

The address of a pointer to the end of <i>pszDest</i>. If <i>ppszDestEnd</i> is non-<b>NULL</b> and any data is copied into the destination buffer, this points to the terminating null character at the end of the string.

### -param pcbRemaining [out, optional]

Type: <b>size_t*</b>

The number of unused bytes in <i>pszDest</i>, including those used for the terminating null character. If <i>pcbRemaining</i> is <b>NULL</b>, the count is not kept or returned.

### -param dwFlags [in]

Type: <b>DWORD</b>

One or more of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_FILL_BEHIND_NULL"></a><a id="strsafe_fill_behind_null"></a><dl>
<dt><b>STRSAFE_FILL_BEHIND_NULL</b></dt>
<dt>0x00000200</dt>
</dl>
</td>
<td width="60%">
If the function succeeds, the low byte of <i>dwFlags</i> (0) is used to fill the uninitialized portion of <i>pszDest</i> following the terminating null character.

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_IGNORE_NULLS"></a><a id="strsafe_ignore_nulls"></a><dl>
<dt><b>STRSAFE_IGNORE_NULLS</b></dt>
<dt>0x00000100</dt>
</dl>
</td>
<td width="60%">
Treat <b>NULL</b> string pointers like empty strings (TEXT("")).

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_FILL_ON_FAILURE"></a><a id="strsafe_fill_on_failure"></a><dl>
<dt><b>STRSAFE_FILL_ON_FAILURE</b></dt>
<dt>0x00000400</dt>
</dl>
</td>
<td width="60%">
If the function fails, the low byte of <i>dwFlags</i> (0) is used to fill the entire <i>pszDest</i> buffer, and the buffer is null-terminated. In the case of a <b>STRSAFE_E_INSUFFICIENT_BUFFER</b> failure, any truncated string returned is overwritten.

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_NULL_ON_FAILURE"></a><a id="strsafe_null_on_failure"></a><dl>
<dt><b>STRSAFE_NULL_ON_FAILURE</b></dt>
<dt>0x00000800</dt>
</dl>
</td>
<td width="60%">
If the function fails, <i>pszDest</i> is set to an empty string (TEXT("")). In the case of a <b>STRSAFE_E_INSUFFICIENT_BUFFER</b> failure, any truncated string is overwritten.

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_NO_TRUNCATION"></a><a id="strsafe_no_truncation"></a><dl>
<dt><b>STRSAFE_NO_TRUNCATION</b></dt>
<dt>0x00001000</dt>
</dl>
</td>
<td width="60%">
As in the case of <b>STRSAFE_NULL_ON_FAILURE</b>, if the function fails, <i>pszDest</i> is set to an empty string (TEXT("")). In the case of a <b>STRSAFE_E_INSUFFICIENT_BUFFER</b> failure, any truncated string is overwritten.

</td>
</tr>
</table>

### -param pszFormat [in]

Type: <b>LPCTSTR</b>

The format string. This string must be null-terminated. For more information, see <a href="https://docs.microsoft.com/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions">Format Specification Syntax</a>.

### -param arg7 [in]

The arguments to be inserted into the <i>pszFormat</i> string.

## -returns

Type: <b>HRESULT</b>

This function can return one of the following values. It is strongly recommended that you use the <a href="https://docs.microsoft.com/windows/desktop/api/winerror/nf-winerror-succeeded">SUCCEEDED</a> and <a href="https://docs.microsoft.com/windows/desktop/api/winerror/nf-winerror-failed">FAILED</a> macros to test the return value of this function.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
There was sufficient space for the result to be copied to <i>pszDest</i> without truncation, and the buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STRSAFE_E_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The value in <i>cbDest</i> is either 0 or larger than <code>STRSAFE_MAX_CCH * sizeof(TCHAR)</code>, or the destination buffer is already full.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STRSAFE_E_INSUFFICIENT_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
The copy operation failed due to insufficient buffer space. Depending on the value of <i>dwFlags</i>, the destination buffer may contain a truncated, null-terminated version of the intended result. In situations where truncation is acceptable, this may not necessarily be seen as a failure condition.

</td>
</tr>
</table>
 

Note that this function returns an <b>HRESULT</b> value, unlike the functions that it replaces.

## -remarks

Compared to  the functions it replaces, <b>StringCbPrintfEx</b> provides additional processing for proper buffer handling in your code. Poor buffer handling is implicated in many security issues that involve buffer overruns. <b>StringCbPrintfEx</b>always null-terminates a nonzero-length destination buffer.

Behavior is undefined if the strings pointed to by <i>pszDest</i>, <i>pszFormat</i>, or any argument strings overlap.

Neither <i>pszFormat</i> nor <i>pszDest</i> should be <b>NULL</b> unless the <b>STRSAFE_IGNORE_NULLS</b> flag is specified, in which case both may be <b>NULL</b>. However, an error due to insufficient space may still be returned even though <b>NULL</b> values are ignored.

<b>StringCbPrintfEx</b> can be used in its generic form, or in its more specific forms. The data type of the string determines the form of this function that you should use.

<table class="clsStd">
<tr>
<th>String Data Type</th>
<th>String Literal</th>
<th>Function</th>
</tr>
<tr>
<td><b>char</b></td>
<td>"string"</td>
<td><b>StringCbPrintfExA</b></td>
</tr>
<tr>
<td><b>TCHAR</b></td>
<td>TEXT("string")</td>
<td><b>StringCbPrintfEx</b></td>
</tr>
<tr>
<td><b>WCHAR</b></td>
<td>L"string"</td>
<td><b>StringCbPrintfExW</b></td>
</tr>
</table>
 





> [!NOTE]
> The strsafe.h header defines StringCbPrintfEx as an alias which automatically selects the ANSI or Unicode version of this function based on the definition of the UNICODE preprocessor constant. Mixing usage of the encoding-neutral alias with code that not encoding-neutral can lead to mismatches that result in compilation or runtime errors. For more information, see [Conventions for Function Prototypes](/windows/win32/intl/conventions-for-function-prototypes).

## -see-also

<b>Reference</b>



<a href="https://docs.microsoft.com/windows/desktop/api/strsafe/nf-strsafe-stringcbvprintfexa">StringCbVPrintfEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/strsafe/nf-strsafe-stringcchprintfa">StringCchPrintf</a>



<a href="https://docs.microsoft.com/windows/desktop/api/strsafe/nf-strsafe-stringcchprintfexa">StringCchPrintfEx</a>

