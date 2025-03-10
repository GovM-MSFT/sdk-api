---
UID: NF:msopc.IOpcSignaturePartReferenceEnumerator.MoveNext
title: IOpcSignaturePartReferenceEnumerator::MoveNext (msopc.h)
description: Moves the current position of the enumerator to the next IOpcSignaturePartReference interface pointer.
helpviewer_keywords: ["IOpcSignaturePartReferenceEnumerator interface [Open Packaging Conventions]","MoveNext method","IOpcSignaturePartReferenceEnumerator.MoveNext","IOpcSignaturePartReferenceEnumerator::MoveNext","MoveNext","MoveNext method [Open Packaging Conventions]","MoveNext method [Open Packaging Conventions]","IOpcSignaturePartReferenceEnumerator interface","msopc/IOpcSignaturePartReferenceEnumerator::MoveNext","opc.iopcsignaturepartreferenceenumerator_movenext"]
old-location: opc\iopcsignaturepartreferenceenumerator_movenext.htm
tech.root: OPC
ms.assetid: 2bf3c448-b09a-4102-bc3a-c65515d2a0a8
ms.date: 12/05/2018
ms.keywords: IOpcSignaturePartReferenceEnumerator interface [Open Packaging Conventions],MoveNext method, IOpcSignaturePartReferenceEnumerator.MoveNext, IOpcSignaturePartReferenceEnumerator::MoveNext, MoveNext, MoveNext method [Open Packaging Conventions], MoveNext method [Open Packaging Conventions],IOpcSignaturePartReferenceEnumerator interface, msopc/IOpcSignaturePartReferenceEnumerator::MoveNext, opc.iopcsignaturepartreferenceenumerator_movenext
req.header: msopc.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 7 [desktop apps only]
req.target-min-winversvr: Windows Server 2008 R2 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: OpcDigitalSignature.idl
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
 - IOpcSignaturePartReferenceEnumerator::MoveNext
 - msopc/IOpcSignaturePartReferenceEnumerator::MoveNext
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - msopc.h
api_name:
 - IOpcSignaturePartReferenceEnumerator.MoveNext
---

# IOpcSignaturePartReferenceEnumerator::MoveNext


## -description

Moves the current position of the enumerator to the next <a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/msopc/nn-msopc-iopcsignaturepartreference">IOpcSignaturePartReference</a> interface pointer.

## -parameters

### -param hasNext [out, retval]

A Boolean value that indicates the status of the <a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/msopc/nn-msopc-iopcsignaturepartreference">IOpcSignaturePartReference</a> interface pointer at the current position.

The value of <i>hasNext</i> is only valid when the method succeeds.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>TRUE</dt>
</dl>
</td>
<td width="60%">
The current position of the enumerator has been advanced to the next pointer and that pointer is valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>FALSE</dt>
</dl>
</td>
<td width="60%">
The current position of the enumerator has been advanced past the end of the collection and is no longer valid.

</td>
</tr>
</table>

## -returns

The method returns an <b>HRESULT</b>. Possible values include, but are not limited to, those in the following table.

<table>
<tr>
<th>Return code/value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
The <i>hasNext</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>OPC_E_ENUM_CANNOT_MOVE_NEXT</b></dt>
<dt>0x80510051</dt>
</dl>
</td>
<td width="60%">
The current position is already past the last item of the enumerator.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>OPC_E_ENUM_COLLECTION_CHANGED</b></dt>
<dt>0x80510050</dt>
</dl>
</td>
<td width="60%">
The enumerator is invalid because the underlying set has changed.

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/desktop/opc/core-packaging-interfaces">Core Packaging Interfaces</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/opc/packaging-api-overview">Getting Started with the Packaging API</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/msopc/nn-msopc-iopcsignaturepartreferenceenumerator">IOpcSignaturePartReferenceEnumerator</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/msopc/nn-msopc-iopcsignaturepartreferenceset">IOpcSignaturePartReferenceSet</a>



<b>Overviews</b>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/opc/packaging-programming-guide">Packaging API Programming Guide</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/opc/packaging-programming-reference">Packaging API Reference</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/opc/packaging-programming-samples">Packaging API Samples</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/opc/packaging-digital-signature-interfaces">Packaging Digital Signature Interfaces</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/dd371635(v=vs.85)">Packaging Interfaces</a>



<b>Reference</b>

