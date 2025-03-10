---
UID: NF:chstring.CHString.GetLength
title: CHString::GetLength (chstring.h)
description: The GetLength method gets a count of the number of wide characters in this CHString string. The count does not include a NULL terminator.
helpviewer_keywords: ["?GetLength@CHString@@QBEHXZ","?GetLength@CHString@@QEBAHXZ","CHString interface [Windows Management Instrumentation]","GetLength method","CHString.GetLength","CHString::GetLength","GetLength","GetLength method [Windows Management Instrumentation]","GetLength method [Windows Management Instrumentation]","CHString interface","_hmm_chstring_getlength","chstring/CHString::GetLength","wmi.chstring_getlength"]
old-location: wmi\chstring_getlength.htm
tech.root: wmi
ms.assetid: b898f9d1-b9a2-4c7b-a7c0-1b6b51ae565f
ms.date: 12/05/2018
ms.keywords: ?GetLength@CHString@@QBEHXZ, ?GetLength@CHString@@QEBAHXZ, CHString interface [Windows Management Instrumentation],GetLength method, CHString.GetLength, CHString::GetLength, GetLength, GetLength method [Windows Management Instrumentation], GetLength method [Windows Management Instrumentation],CHString interface, _hmm_chstring_getlength, chstring/CHString::GetLength, wmi.chstring_getlength
req.header: chstring.h
req.include-header: FwCommon.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FrameDyn.lib
req.dll: FrameDynOS.dll; FrameDyn.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - CHString::GetLength
 - chstring/CHString::GetLength
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - FrameDynOS.dll
 - FrameDyn.dll
api_name:
 - CHString.GetLength
 - ?GetLength@CHString@@QBEHXZ
 - ?GetLength@CHString@@QEBAHXZ
---

# CHString::GetLength


## -description

<p class="CCE_Message">[The <a href="https://docs.microsoft.com/windows/desktop/WmiSdk/chstring">CHString</a> class 
    is part of the WMI Provider Framework which is now considered in final state, and no further development, 
    enhancements, or updates will be available for non-security related issues affecting these libraries. The 
    <a href="https://docs.microsoft.com/previous-versions/windows/desktop/wmi_v2/windows-management-infrastructure">MI APIs</a> should be used for all new 
    development.]

The <b>GetLength</b> method gets a count of the number of wide characters in this <a href="https://docs.microsoft.com/windows/desktop/WmiSdk/chstring">CHString</a> string. The count does not include a <b>NULL</b> terminator.

## -parameters

## -returns

Returns a count of the number of wide characters in the string, not the number of bytes.

