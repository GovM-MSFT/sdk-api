---
UID: NF:dvbsiparser.IDvbSiParser.GetPAT
title: IDvbSiParser::GetPAT (dvbsiparser.h)
description: This topic applies to Update Rollup 2 for Microsoft Windows XP Media Center Edition 2005 and later.
helpviewer_keywords: ["GetPAT","GetPAT method [Microsoft TV Technologies]","GetPAT method [Microsoft TV Technologies]","IDvbSiParser interface","IDvbSiParser interface [Microsoft TV Technologies]","GetPAT method","IDvbSiParser.GetPAT","IDvbSiParser::GetPAT","IDvbSiParserGetPAT","dvbsiparser/IDvbSiParser::GetPAT","mstv.idvbsiparser_getpat"]
old-location: mstv\idvbsiparser_getpat.htm
tech.root: mstv
ms.assetid: 09413d56-e735-4ecf-a505-7d9e2c31d190
ms.date: 12/05/2018
ms.keywords: GetPAT, GetPAT method [Microsoft TV Technologies], GetPAT method [Microsoft TV Technologies],IDvbSiParser interface, IDvbSiParser interface [Microsoft TV Technologies],GetPAT method, IDvbSiParser.GetPAT, IDvbSiParser::GetPAT, IDvbSiParserGetPAT, dvbsiparser/IDvbSiParser::GetPAT, mstv.idvbsiparser_getpat
req.header: dvbsiparser.h
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
 - IDvbSiParser::GetPAT
 - dvbsiparser/IDvbSiParser::GetPAT
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dvbsiparser.h
api_name:
 - IDvbSiParser.GetPAT
---

# IDvbSiParser::GetPAT


## -description

This topic applies to Update Rollup 2 for Microsoft Windows XP Media Center Edition 2005 and later.
        



The <b>GetPAT</b> method retrieves the program association table (PAT).

## -parameters

### -param ppPAT [out]

Address of a variable that receives an <a href="https://docs.microsoft.com/windows/desktop/api/mpeg2psiparser/nn-mpeg2psiparser-ipat">IPAT</a> interface pointer. The caller must release the interface.

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
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
NULL pointer argument.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>MPEG2_E_SECTION_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The filter did not receive the table in the allotted time.

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

The method fails if the filter does not receive a matching table within a predetermined length of time.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/dvbsiparser/nn-dvbsiparser-idvbsiparser">IDvbSiParser Interface</a>

