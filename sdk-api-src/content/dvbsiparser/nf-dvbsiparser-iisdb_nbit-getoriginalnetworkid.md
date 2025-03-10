---
UID: NF:dvbsiparser.IISDB_NBIT.GetOriginalNetworkId
title: IISDB_NBIT::GetOriginalNetworkId (dvbsiparser.h)
description: Gets an identifier that identifies the broadcaster that originated the MPEG-2 transport stream from an Integrated Services Digital Broadcasting (ISDB) network broadcaster information table (NBIT).
helpviewer_keywords: ["GetOriginalNetworkId","GetOriginalNetworkId method [Microsoft TV Technologies]","GetOriginalNetworkId method [Microsoft TV Technologies]","IISDB_NBIT interface","IISDB_NBIT interface [Microsoft TV Technologies]","GetOriginalNetworkId method","IISDB_NBIT.GetOriginalNetworkId","IISDB_NBIT::GetOriginalNetworkId","dvbsiparser/IISDB_NBIT::GetOriginalNetworkId","mstv.iisdb_nbit_getoriginalnetworkid"]
old-location: mstv\iisdb_nbit_getoriginalnetworkid.htm
tech.root: mstv
ms.assetid: 762b7d48-c74e-4d5a-9c99-890d613553fa
ms.date: 12/05/2018
ms.keywords: GetOriginalNetworkId, GetOriginalNetworkId method [Microsoft TV Technologies], GetOriginalNetworkId method [Microsoft TV Technologies],IISDB_NBIT interface, IISDB_NBIT interface [Microsoft TV Technologies],GetOriginalNetworkId method, IISDB_NBIT.GetOriginalNetworkId, IISDB_NBIT::GetOriginalNetworkId, dvbsiparser/IISDB_NBIT::GetOriginalNetworkId, mstv.iisdb_nbit_getoriginalnetworkid
req.header: dvbsiparser.h
req.include-header: Dvbsiparser.idl
req.target-type: Windows
req.target-min-winverclnt: Windows 7 [desktop apps only]
req.target-min-winversvr: None supported
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
 - IISDB_NBIT::GetOriginalNetworkId
 - dvbsiparser/IISDB_NBIT::GetOriginalNetworkId
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
 - IISDB_NBIT.GetOriginalNetworkId
---

# IISDB_NBIT::GetOriginalNetworkId


## -description

Gets an identifier that identifies the broadcaster that originated the
  MPEG-2 transport stream from an Integrated Services Digital Broadcasting (ISDB) network broadcaster information table (NBIT).

## -parameters

### -param pwVal [out]

Receives the original network ID.

## -returns

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/dvbsiparser/nn-dvbsiparser-iisdb_nbit">IISDB_NBIT</a>

