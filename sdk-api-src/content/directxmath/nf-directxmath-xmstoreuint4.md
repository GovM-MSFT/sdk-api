---
UID: NF:directxmath.XMStoreUInt4
title: XMStoreUInt4 function (directxmath.h)
description: Stores unsigned integer data from an XMVECTOR in an XMUINT4 structure.
helpviewer_keywords: ["Use DirectX..XMStoreUInt4","XMStoreUInt4","XMStoreUInt4 method [DirectX Math Support APIs]","dxmath.xmstoreuint4"]
old-location: dxmath\xmstoreuint4.htm
tech.root: dxmath
ms.assetid: M:Microsoft.directx_sdk.storing.XMStoreUInt4(XMUINT4@,XMVECTOR)
ms.date: 12/05/2018
ms.keywords: Use DirectX..XMStoreUInt4, XMStoreUInt4, XMStoreUInt4 method [DirectX Math Support APIs], dxmath.xmstoreuint4
req.header: directxmath.h
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
req.namespace: Use DirectX.
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
 - XMStoreUInt4
 - directxmath/XMStoreUInt4
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - DirectXMath.h
api_name:
 - XMStoreUInt4
---

# XMStoreUInt4 function


## -description

Stores unsigned integer data from an <a href="https://docs.microsoft.com/windows/desktop/dxmath/xmvector-data-type">XMVECTOR</a> 
  in an <b>XMUINT4</b> structure.

## -parameters

### -param pDestination [out]

Address of an  <a href="https://docs.microsoft.com/windows/desktop/api/directxmath/ns-directxmath-xmuint4">XMUINT4</a> structure in which to store the data.

### -param V

Vector containing the data to store.

## -returns

None.

## -remarks

For 16-byte aligned memory, it may be faster to use <a href="https://docs.microsoft.com/windows/desktop/api/directxmath/nf-directxmath-xmstoreint4a">XMStoreInt4A</a> 
    with a casting operator.

The following pseudocode shows the operation of this function.


```

XMVECTOR N;	

assert(pDestination);

N = XMVectorClamp(V, XMVectorZero(), MaxUInt );
N = XMVectorRound(N);

pDestination->x = (uint32_t)N.v[0];
pDestination->y = (uint32_t)N.v[1];
pDestination->z = (uint32_t)N.v[2];
pDestination->w = (uint32_t)N.v[3];

    
```


<h3><a id="Platform_Requirements"></a><a id="platform_requirements"></a><a id="PLATFORM_REQUIREMENTS"></a>Platform Requirements</h3>
Microsoft Visual Studio 2010 or Microsoft Visual Studio 2012 with the Windows SDK for Windows 8. Supported for Win32 desktop apps, Windows Store apps, and Windows Phone 8 apps.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/dxmath/ovw-xnamath-reference-functions-storage">DirectXMath Library Vector Store Functions</a>

