---
UID: NF:mpeg2psiparser.IPMT.GetRecordDescriptorByTag
title: IPMT::GetRecordDescriptorByTag (mpeg2psiparser.h)
description: The GetRecordDescriptorByTag method searches a record in the PMT for a descriptor with a specified descriptor tag.
helpviewer_keywords: ["GetRecordDescriptorByTag","GetRecordDescriptorByTag method [Microsoft TV Technologies]","GetRecordDescriptorByTag method [Microsoft TV Technologies]","IPMT interface","IPMT interface [Microsoft TV Technologies]","GetRecordDescriptorByTag method","IPMT.GetRecordDescriptorByTag","IPMT::GetRecordDescriptorByTag","IPMTGetRecordDescriptorByTag","mpeg2psiparser/IPMT::GetRecordDescriptorByTag","mstv.ipmt_getrecorddescriptorbytag"]
old-location: mstv\ipmt_getrecorddescriptorbytag.htm
tech.root: mstv
ms.assetid: 7ed3dd22-331a-419a-ab30-5645e259e36a
ms.date: 12/05/2018
ms.keywords: GetRecordDescriptorByTag, GetRecordDescriptorByTag method [Microsoft TV Technologies], GetRecordDescriptorByTag method [Microsoft TV Technologies],IPMT interface, IPMT interface [Microsoft TV Technologies],GetRecordDescriptorByTag method, IPMT.GetRecordDescriptorByTag, IPMT::GetRecordDescriptorByTag, IPMTGetRecordDescriptorByTag, mpeg2psiparser/IPMT::GetRecordDescriptorByTag, mstv.ipmt_getrecorddescriptorbytag
req.header: mpeg2psiparser.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - IPMT::GetRecordDescriptorByTag
 - mpeg2psiparser/IPMT::GetRecordDescriptorByTag
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Mpeg2PsiParser.h
api_name:
 - IPMT.GetRecordDescriptorByTag
---

# IPMT::GetRecordDescriptorByTag


## -description

The <b>GetRecordDescriptorByTag</b> method searches a record in the PMT for a descriptor with a specified descriptor tag.

## -parameters

### -param dwRecordIndex [in]

Specifies the record number, indexed from zero. Call the <a href="https://docs.microsoft.com/windows/desktop/api/mpeg2psiparser/nf-mpeg2psiparser-ipmt-getcountofrecords">IPMT::GetCountOfRecords</a> method to get the number of records in the PMT.

### -param bTag [in]

Specifies the descriptor tag for which to search.

### -param pdwCookie [in, out]

Pointer to a variable that specifies the start position in the descriptor list. This parameter is optional. If the value of <i>pdwCookie</i> is <b>NULL</b>, the search starts from the first descriptor in the list. Otherwise, the search starts from the position given in <i>pdwCookie</i>. When the method returns, the <i>pdwCookie</i> parameter contains the position of the next matching descriptor, if any. You can use this parameter to iterate through the descriptor list, looking for every instance of a particular descriptor tag.

### -param ppDescriptor [out]

Address of a variable that receives an <a href="https://docs.microsoft.com/windows/desktop/api/mpeg2psiparser/nn-mpeg2psiparser-igenericdescriptor">IGenericDescriptor</a> interface pointer. Use this interface to retrieve the information in the descriptor. The caller must release the interface.

## -returns

The method returns an <b>HRESULT</b>. Possible values include those in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>MPEG2_E_OUT_OF_BOUNDS</b></dt>
</dl>
</td>
<td width="60%">
Index out of bounds.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>MPEG2_E_NOT_PRESENT</b></dt>
</dl>
</td>
<td width="60%">
The specified tag was not found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>MPEG2_S_MORE_DATA_AVAILABLE</b></dt>
</dl>
</td>
<td width="60%">
The record contains at least one more descriptor with this tag.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>MPEG2_S_NO_MORE_DATA_AVAILABLE</b></dt>
</dl>
</td>
<td width="60%">
The record does not contain any more descriptors with this tag.

</td>
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
</table>

## -remarks

If the value of <i>pdwCookie</i> is not <b>NULL</b>, the method returns either MPEG2_S_NO_MORE_DATA_AVAILABLE or MPEG2_S_MORE_DATA_AVAILABLE to indicate whether the record contains additional tags that match the search criteria.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/mpeg2psiparser/nn-mpeg2psiparser-ipmt">IPMT Interface</a>

