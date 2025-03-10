---
UID: NF:pdh.PdhGetDefaultPerfCounterW
title: PdhGetDefaultPerfCounterW function (pdh.h)
description: Retrieves the name of the default counter for the specified object. This name can be used to set the initial counter selection in the Browse Counter dialog box. To use handles to data sources, use the PdhGetDefaultPerfCounterH function.
helpviewer_keywords: ["PdhGetDefaultPerfCounter","PdhGetDefaultPerfCounter function [Perf]","PdhGetDefaultPerfCounterA","PdhGetDefaultPerfCounterW","_win32_pdhgetdefaultperfcounter","base.pdhgetdefaultperfcounter","pdh/PdhGetDefaultPerfCounter","pdh/PdhGetDefaultPerfCounterA","pdh/PdhGetDefaultPerfCounterW","perf.pdhgetdefaultperfcounter"]
old-location: perf\pdhgetdefaultperfcounter.htm
tech.root: perf
ms.assetid: 0eb78071-3496-40e9-91b0-3c06547c88d5
ms.date: 12/05/2018
ms.keywords: PdhGetDefaultPerfCounter, PdhGetDefaultPerfCounter function [Perf], PdhGetDefaultPerfCounterA, PdhGetDefaultPerfCounterW, _win32_pdhgetdefaultperfcounter, base.pdhgetdefaultperfcounter, pdh/PdhGetDefaultPerfCounter, pdh/PdhGetDefaultPerfCounterA, pdh/PdhGetDefaultPerfCounterW, perf.pdhgetdefaultperfcounter
req.header: pdh.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP [desktop apps only]
req.target-min-winversvr: Windows Server 2003 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: PdhGetDefaultPerfCounterW (Unicode) and PdhGetDefaultPerfCounterA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Pdh.lib
req.dll: Pdh.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - PdhGetDefaultPerfCounterW
 - pdh/PdhGetDefaultPerfCounterW
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Pdh.dll
api_name:
 - PdhGetDefaultPerfCounter
 - PdhGetDefaultPerfCounterA
 - PdhGetDefaultPerfCounterW
---

# PdhGetDefaultPerfCounterW function


## -description

Retrieves the name of the default counter for the specified object. This name can be used to set the initial counter selection in the Browse Counter dialog box.
			

To use handles to data sources, use the 
<a href="https://docs.microsoft.com/windows/desktop/api/pdh/nf-pdh-pdhgetdefaultperfcounterha">PdhGetDefaultPerfCounterH</a> function.

## -parameters

### -param szDataSource [in]

Should be <b>NULL</b>. 



					If you specify a log file, <i>szDefaultCounterName</i> will be a <b>null</b> string.

### -param szMachineName [in]

<b>Null</b>-terminated string that specifies the name of the computer used to verify the object name. If <b>NULL</b>, the local computer is used to verify the object name.

### -param szObjectName [in]

<b>Null</b>-terminated string that specifies the name of the object whose default counter name you want to retrieve.

### -param szDefaultCounterName [out]

Caller-allocated buffer that receives the <b>null</b>-terminated default counter name. Set to <b>NULL</b> if <i>pcchBufferSize</i> is zero.

### -param pcchBufferSize [in, out]

Size of the <i>szDefaultCounterName</i> buffer, in <b>TCHARs</b>. If zero on input, the function returns PDH_MORE_DATA and sets this parameter to the required buffer size. If the buffer is larger than the required size, the function sets this parameter to the actual size of the buffer that was used. If the specified size on input is greater than zero but less than the required size, you should not rely on the returned size to reallocate the buffer.

## -returns

If the function succeeds, it returns ERROR_SUCCESS.
						

If the function fails, the return value is a 
<a href="https://docs.microsoft.com/windows/desktop/Debug/system-error-codes">system error code</a> or a 
<a href="https://docs.microsoft.com/windows/desktop/PerfCtrs/pdh-error-codes">PDH error code</a>. The following are possible values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>PDH_MORE_DATA</b></dt>
</dl>
</td>
<td width="60%">
The <i>szDefaultCounterName</i> buffer is too small to contain the counter name. This return value is expected if <i>pcchBufferSize</i> is zero on input. If the specified size on input is greater than zero but less than the required size, you should not rely on the returned size to reallocate the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>PDH_INVALID_ARGUMENT</b></dt>
</dl>
</td>
<td width="60%">
A required parameter is not valid. For example, on some releases you could receive this error if the specified size on input is greater than zero but less than the required size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>PDH_MEMORY_ALLOCATION_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
Unable to allocate memory in order to complete the function.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>PDH_CSTATUS_NO_MACHINE</b></dt>
</dl>
</td>
<td width="60%">
The specified computer is offline or unavailable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>PDH_CSTATUS_NO_COUNTERNAME</b></dt>
</dl>
</td>
<td width="60%">
The default counter name cannot be read or found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>PDH_CSTATUS_NO_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The specified object could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>PDH_CSTATUS_NO_COUNTER</b></dt>
</dl>
</td>
<td width="60%">
The object did not specify a default counter.

</td>
</tr>
</table>

## -remarks

You should call this function twice, the first time to get the required buffer size (set <i>szDefaultCounterName</i> to <b>NULL</b> and <i>pcchBufferSize</i> to 0), and the second time to get the data.





> [!NOTE]
> The pdh.h header defines PdhGetDefaultPerfCounter as an alias which automatically selects the ANSI or Unicode version of this function based on the definition of the UNICODE preprocessor constant. Mixing usage of the encoding-neutral alias with code that not encoding-neutral can lead to mismatches that result in compilation or runtime errors. For more information, see [Conventions for Function Prototypes](/windows/win32/intl/conventions-for-function-prototypes).

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/pdh/nf-pdh-pdhgetdefaultperfcounterha">PdhGetDefaultPerfCounterH</a>



<a href="https://docs.microsoft.com/windows/desktop/api/pdh/nf-pdh-pdhgetdefaultperfobjecta">PdhGetDefaultPerfObject</a>

