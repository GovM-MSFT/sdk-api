---
UID: NF:bdaiface.IEnumPIDMap.Next
title: IEnumPIDMap::Next (bdaiface.h)
description: The Next method retrieves the next n elements in the collection.
helpviewer_keywords: ["IEnumPIDMap interface [DirectShow]","Next method","IEnumPIDMap.Next","IEnumPIDMap::Next","IEnumPIDMapNext","Next","Next method [DirectShow]","Next method [DirectShow]","IEnumPIDMap interface","bdaiface/IEnumPIDMap::Next","dshow.ienumpidmap_next"]
old-location: dshow\ienumpidmap_next.htm
tech.root: dshow
ms.assetid: e7e3a2a7-cc62-478d-b0b8-30d58f0b3372
ms.date: 12/05/2018
ms.keywords: IEnumPIDMap interface [DirectShow],Next method, IEnumPIDMap.Next, IEnumPIDMap::Next, IEnumPIDMapNext, Next, Next method [DirectShow], Next method [DirectShow],IEnumPIDMap interface, bdaiface/IEnumPIDMap::Next, dshow.ienumpidmap_next
req.header: bdaiface.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 Professional [desktop apps only]
req.target-min-winversvr: Windows 2000 Server [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Strmiids.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - IEnumPIDMap::Next
 - bdaiface/IEnumPIDMap::Next
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Strmiids.lib
 - Strmiids.dll
api_name:
 - IEnumPIDMap.Next
---

# IEnumPIDMap::Next


## -description

The <code>Next</code> method retrieves the next <i>n</i> elements in the collection.

## -parameters

### -param cRequest [in]

The number of elements to retrieve.

### -param pPIDMap [in, out]

Address of an array allocated by the caller, containing <i>cRequest</i> elements. The array is filled with <a href="https://docs.microsoft.com/windows/desktop/DirectShow/pid-map">PID_MAP</a> structures that describe the PID mapping.

### -param pcReceived [out]

Pointer to a variable that receives the number of elements actually retrieved. This parameter cannot be <b>NULL</b>. If <i>cRequest</i> equals zero, this parameter receives the total number of items in the collection.

## -returns

Returns an <b>HRESULT</b> value. Possible values include the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Invalid argument; <i>pPidMap</i> and <i>pcReceived</i> cannot be <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
Reached the end of the collection.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
Success.

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/DirectShow/error-and-success-codes">Error and Success Codes</a>



<a href="https://docs.microsoft.com/windows/desktop/api/bdaiface/nn-bdaiface-ienumpidmap">IEnumPIDMap Interface</a>

