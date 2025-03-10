---
UID: NF:tapi3if.ITLocationInfo.get_CountryID
title: ITLocationInfo::get_CountryID (tapi3if.h)
description: The get_CountryID method gets the identifier for the country/region.
helpviewer_keywords: ["ITLocationInfo interface [TAPI 2.2]","get_CountryID method","ITLocationInfo.get_CountryID","ITLocationInfo::get_CountryID","_tapi3_itlocationinfo_get_countryid","get_CountryID","get_CountryID method [TAPI 2.2]","get_CountryID method [TAPI 2.2]","ITLocationInfo interface","tapi3.itlocationinfo_get_countryid","tapi3if/ITLocationInfo::get_CountryID"]
old-location: tapi3\itlocationinfo_get_countryid.htm
tech.root: tapi3
ms.assetid: c60e384b-ad0a-4e48-a337-b4ffad1b4891
ms.date: 12/05/2018
ms.keywords: ITLocationInfo interface [TAPI 2.2],get_CountryID method, ITLocationInfo.get_CountryID, ITLocationInfo::get_CountryID, _tapi3_itlocationinfo_get_countryid, get_CountryID, get_CountryID method [TAPI 2.2], get_CountryID method [TAPI 2.2],ITLocationInfo interface, tapi3.itlocationinfo_get_countryid, tapi3if/ITLocationInfo::get_CountryID
req.header: tapi3if.h
req.include-header: Tapi3.h
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
req.lib: Uuid.lib
req.dll: Tapi3.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - ITLocationInfo::get_CountryID
 - tapi3if/ITLocationInfo::get_CountryID
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Tapi3.dll
api_name:
 - ITLocationInfo.get_CountryID
---

# ITLocationInfo::get_CountryID


## -description

The 
<b>get_CountryID</b> method gets the identifier for the country/region.

## -parameters

### -param plCountryID [out]

Country/region ID.

## -returns

This method can return one of these values.

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
Method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The <i>ulCountryID</i> parameter is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
The <i>ulCountryID</i> parameter is not a valid pointer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
Insufficient memory exists to perform the operation.

</td>
</tr>
</table>

## -remarks

The value that this method returns corresponds to the <b>dwCountryID</b> member of TAPI 2's 
<a href="https://docs.microsoft.com/windows/desktop/api/tapi/ns-tapi-linelocationentry">LINELOCATIONENTRY</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/tapi3if/nn-tapi3if-itlocationinfo">ITLocationInfo</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tapi/ns-tapi-linelocationentry">LINELOCATIONENTRY</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tapi/nf-tapi-linegettranslatecaps">lineGetTranslateCaps</a>

