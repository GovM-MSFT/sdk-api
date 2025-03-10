---
UID: NS:wmsdkidl._WMT_PAYLOAD_FRAGMENT
title: WMT_PAYLOAD_FRAGMENT (wmsdkidl.h)
description: The WMT_PAYLOAD_FRAGMENT structure contains the information needed to extract a payload fragment from a buffer and identifies the payload to which the fragment belongs.
helpviewer_keywords: ["WMT_PAYLOAD_FRAGMENT","WMT_PAYLOAD_FRAGMENT structure [windows Media Format]","wmformat.wmt_payload_fragment","wmsdkidl/WMT_PAYLOAD_FRAGMENT"]
old-location: wmformat\wmt_payload_fragment.htm
tech.root: wmformat
ms.assetid: 5a99c772-0e8a-4f6d-a13f-9bf7b4fa7d89
ms.date: 12/05/2018
ms.keywords: WMT_PAYLOAD_FRAGMENT, WMT_PAYLOAD_FRAGMENT structure [windows Media Format], wmformat.wmt_payload_fragment, wmsdkidl/WMT_PAYLOAD_FRAGMENT
req.header: wmsdkidl.h
req.include-header: Wmsdk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 Professional [desktop apps only],Windows Media Format 9 Series SDK, or later versions of the SDK
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WMT_PAYLOAD_FRAGMENT
req.redist: 
ms.custom: 19H1
f1_keywords:
 - _WMT_PAYLOAD_FRAGMENT
 - wmsdkidl/_WMT_PAYLOAD_FRAGMENT
 - WMT_PAYLOAD_FRAGMENT
 - wmsdkidl/WMT_PAYLOAD_FRAGMENT
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wmsdkidl.h
api_name:
 - WMT_PAYLOAD_FRAGMENT
---

# WMT_PAYLOAD_FRAGMENT structure


## -description

The <b>WMT_PAYLOAD_FRAGMENT</b> structure contains the information needed to extract a payload fragment from a buffer and identifies the payload to which the fragment belongs. An array of <b>WMT_PAYLOAD_FRAGMENT</b> structures is used as a member of the <b>WMT_FILESINK_DATA_UNIT</b> structure to provide access to each payload fragment in a packet.

## -struct-fields

### -field dwPayloadIndex

<b>DWORD</b> containing the payload index. This identifies the payload item to which this fragment belongs.

### -field segmentData

A <b>WMT_BUFFER_SEGMENT</b> structure specifying the buffer segment containing the payload fragment.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/wmformat/structures">Structures</a>

