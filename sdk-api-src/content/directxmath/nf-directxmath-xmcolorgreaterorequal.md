---
UID: NF:directxmath.XMColorGreaterOrEqual
title: XMColorGreaterOrEqual function (directxmath.h)
description: Tests whether all the components of the first color are greater than or equal to the corresponding components of the second color.
helpviewer_keywords: ["Use DirectX..XMColorGreaterOrEqual","XMColorGreaterOrEqual","XMColorGreaterOrEqual method [DirectX Math Support APIs]","dxmath.xmcolorgreaterorequal"]
old-location: dxmath\xmcolorgreaterorequal.htm
tech.root: dxmath
ms.assetid: M:Microsoft.directx_sdk.color.XMColorGreaterOrEqual(XMVECTOR,XMVECTOR)
ms.date: 12/05/2018
ms.keywords: Use DirectX..XMColorGreaterOrEqual, XMColorGreaterOrEqual, XMColorGreaterOrEqual method [DirectX Math Support APIs], dxmath.xmcolorgreaterorequal
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
 - XMColorGreaterOrEqual
 - directxmath/XMColorGreaterOrEqual
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
 - XMColorGreaterOrEqual
---

# XMColorGreaterOrEqual function


## -description

Tests whether all the components of the first color are greater than or equal to the corresponding components of the
  second color.

## -parameters

### -param C1 [in]

<b>XMVECTOR</b> describing the first color to compare.

### -param C2 [in]

<b>XMVECTOR</b> describing the second color to compare.

## -returns

Returns true if every component of <i>C1</i> is greater than or equal to the corresponding component in
       <i>C2</i>. Returns false otherwise.

## -remarks

<h3><a id="Platform_Requirements"></a><a id="platform_requirements"></a><a id="PLATFORM_REQUIREMENTS"></a>Platform Requirements</h3>
Microsoft Visual Studio 2010 or Microsoft Visual Studio 2012 with the Windows SDK for Windows 8. Supported for Win32 desktop apps, Windows Store apps, and Windows Phone 8 apps.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/dxmath/ovw-xnamath-reference-functions-color">DirectXMath Library Color Functions</a>

