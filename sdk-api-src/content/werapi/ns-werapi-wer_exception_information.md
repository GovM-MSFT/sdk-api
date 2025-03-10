---
UID: NS:werapi._WER_EXCEPTION_INFORMATION
title: WER_EXCEPTION_INFORMATION (werapi.h)
description: Contains exception information for the WerReportAddDump function.
helpviewer_keywords: ["*PWER_EXCEPTION_INFORMATION","PWER_EXCEPTION_INFORMATION","PWER_EXCEPTION_INFORMATION structure pointer [Windows Error Reporting]","WER_EXCEPTION_INFORMATION","WER_EXCEPTION_INFORMATION structure [Windows Error Reporting]","base.wer_exception_information","wer.wer_exception_information","werapi/PWER_EXCEPTION_INFORMATION","werapi/WER_EXCEPTION_INFORMATION"]
old-location: wer\wer_exception_information.htm
tech.root: wer
ms.assetid: 4548068a-e654-40c9-9654-c5178575b42c
ms.date: 12/05/2018
ms.keywords: '*PWER_EXCEPTION_INFORMATION, PWER_EXCEPTION_INFORMATION, PWER_EXCEPTION_INFORMATION structure pointer [Windows Error Reporting], WER_EXCEPTION_INFORMATION, WER_EXCEPTION_INFORMATION structure [Windows Error Reporting], base.wer_exception_information, wer.wer_exception_information, werapi/PWER_EXCEPTION_INFORMATION, werapi/WER_EXCEPTION_INFORMATION'
req.header: werapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista [desktop apps only]
req.target-min-winversvr: Windows Server 2008 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WER_EXCEPTION_INFORMATION, *PWER_EXCEPTION_INFORMATION
req.redist: 
ms.custom: 19H1
f1_keywords:
 - _WER_EXCEPTION_INFORMATION
 - werapi/_WER_EXCEPTION_INFORMATION
 - PWER_EXCEPTION_INFORMATION
 - werapi/PWER_EXCEPTION_INFORMATION
 - WER_EXCEPTION_INFORMATION
 - werapi/WER_EXCEPTION_INFORMATION
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Werapi.h
api_name:
 - WER_EXCEPTION_INFORMATION
---

# WER_EXCEPTION_INFORMATION structure


## -description

Contains exception information for the <a href="https://docs.microsoft.com/windows/desktop/api/werapi/nf-werapi-werreportadddump">WerReportAddDump</a> function.

## -struct-fields

### -field pExceptionPointers

A pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/winnt/ns-winnt-exception_pointers">EXCEPTION_POINTERS</a> structure.

### -field bClientPointers

A process (calling process) can provide error reporting functionality for another process (client process). If this member is <b>TRUE</b>, the exception pointer is located inside the  address space of the client process. If this member is <b>FALSE</b>, the exception pointer is located inside the address space of the calling process.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/werapi/nf-werapi-werreportadddump">WerReportAddDump</a>

