---
UID: NF:imapi2.IWriteEngine2EventArgs.get_FreeSystemBuffer
title: IWriteEngine2EventArgs::get_FreeSystemBuffer (imapi2.h)
description: Retrieves the number of unused bytes in the internal data buffer that is used for writing to disc.
helpviewer_keywords: ["IWriteEngine2EventArgs interface [IMAPI]","get_FreeSystemBuffer method","IWriteEngine2EventArgs.get_FreeSystemBuffer","IWriteEngine2EventArgs::get_FreeSystemBuffer","get_FreeSystemBuffer","get_FreeSystemBuffer method [IMAPI]","get_FreeSystemBuffer method [IMAPI]","IWriteEngine2EventArgs interface","imapi.iwriteengine2eventargs_get_freesystembuffer","imapi2/IWriteEngine2EventArgs::get_FreeSystemBuffer"]
old-location: imapi\iwriteengine2eventargs_get_freesystembuffer.htm
tech.root: imapi
ms.assetid: d62eeb31-cf47-4456-832c-9a29c045b11c
ms.date: 12/05/2018
ms.keywords: IWriteEngine2EventArgs interface [IMAPI],get_FreeSystemBuffer method, IWriteEngine2EventArgs.get_FreeSystemBuffer, IWriteEngine2EventArgs::get_FreeSystemBuffer, get_FreeSystemBuffer, get_FreeSystemBuffer method [IMAPI], get_FreeSystemBuffer method [IMAPI],IWriteEngine2EventArgs interface, imapi.iwriteengine2eventargs_get_freesystembuffer, imapi2/IWriteEngine2EventArgs::get_FreeSystemBuffer
req.header: imapi2.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista, Windows XP with SP2 [desktop apps only]
req.target-min-winversvr: Windows Server 2003 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Imapi2.idl
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
 - IWriteEngine2EventArgs::get_FreeSystemBuffer
 - imapi2/IWriteEngine2EventArgs::get_FreeSystemBuffer
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - imapi2.h
api_name:
 - IWriteEngine2EventArgs.get_FreeSystemBuffer
---

# IWriteEngine2EventArgs::get_FreeSystemBuffer


## -description

Retrieves the number of unused bytes in the internal data buffer that is used for writing to disc.

## -parameters

### -param value [out]

Size, in bytes, of the unused portion  of the internal data buffer that is used for writing to disc.

## -returns

S_OK is returned on success, but other success codes may be returned as a result of implementation. The following error codes are commonly returned on operation failure, but do not represent the only possible error values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
Pointer is not valid.

Value: 0x80004003

</td>
</tr>
</table>

## -remarks

This method returns the same value as if you subtracted <a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-iwriteengine2eventargs-get_usedsystembuffer">IWriteEngine2EventArgs::get_UsedSystemBuffer</a> from <a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-iwriteengine2eventargs-get_totalsystembuffer">IWriteEngine2EventArgs::get_TotalSystemBuffer</a>.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nn-imapi2-iwriteengine2eventargs">IWriteEngine2EventArgs</a>



<a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-iwriteengine2eventargs-get_totalsystembuffer">IWriteEngine2EventArgs::get_TotalSystemBuffer</a>



<a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-iwriteengine2eventargs-get_usedsystembuffer">IWriteEngine2EventArgs::get_UsedSystemBuffer</a>

