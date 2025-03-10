---
UID: NS:directxmath.XMINT4
title: XMINT4 (directxmath.h)
description: A 4D vector where each component is a signed integer.
helpviewer_keywords: ["XMINT4","XMINT4 structure [DirectX Math Support APIs]","directxmath/XMINT4","dxmath.xmint4"]
old-location: dxmath\xmint4.htm
tech.root: dxmath
ms.assetid: T:Microsoft.directx_sdk.reference.XMINT4
ms.date: 12/05/2018
ms.keywords: XMINT4, XMINT4 structure [DirectX Math Support APIs], directxmath/XMINT4, dxmath.xmint4
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
 - XMINT4
 - directxmath/XMINT4
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DirectXMath.h
api_name:
 - XMINT4
---

# XMINT4 structure


## -description

A 4D vector where each component is a signed integer.

For a list of more functionality such as constructors and operators that are available 
  using <code>XMINT4</code> when you
  are programming in C++, see <a href="https://docs.microsoft.com/windows/desktop/dxmath/ovw-xmint4-extensions">XMINT4 Extensions</a>.
<div class="alert"><b>Note</b>  See <a href="https://docs.microsoft.com/windows/desktop/dxmath/pg-xnamath-internals">DirectXMath Library Type Equivalences</a> for information about
  equivalent <a href="https://docs.microsoft.com/windows/desktop/direct3d9/d3ddecltype">D3DDECLTYPE</a>, <a href="https://docs.microsoft.com/windows/desktop/direct3d9/d3dformat">D3DFORMAT</a>, and
  <a href="https://docs.microsoft.com/windows/desktop/api/dxgiformat/ne-dxgiformat-dxgi_format">DXGI_FORMAT</a> objects.</div><div> </div>

## -struct-fields

### -field x

Signed integer value describing the x coordinate of the vector.

### -field y

Signed integer value describing the y coordinate of the vector.

### -field z

Signed integer value describing the z coordinate of the vector.

### -field w

Signed integer value describing the w coordinate of the vector.

### -field operator=

TBD

### -field XMINT4

TBD

## -remarks

You can use <a href="https://docs.microsoft.com/windows/desktop/api/directxmath/nf-directxmath-xmloadsint4">XMLoadSInt4</a> to load <code>XMINT4</code> into instances 
   of <a href="https://docs.microsoft.com/windows/desktop/dxmath/xmvector-data-type">XMVECTOR</a>.

You can use <a href="https://docs.microsoft.com/windows/desktop/api/directxmath/nf-directxmath-xmstoresint4">XMStoreSInt4</a> to store instances of <code>XMVECTOR</code> 
     into an instance of <code>XMINT4</code>.

<b>Namespace:</b> Use DirectX

<h3><a id="Platform_Requirements"></a><a id="platform_requirements"></a><a id="PLATFORM_REQUIREMENTS"></a>Platform Requirements</h3>
Microsoft Visual Studio 2010 or Microsoft Visual Studio 2012 with the Windows SDK for Windows 8. Supported for Win32 desktop apps, Windows Store apps, and Windows Phone 8 apps.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/dxmath/ovw-xnamath-reference-structures">DirectXMath Library Structures</a>



<a href="https://docs.microsoft.com/windows/desktop/dxmath/ovw-xmint4-extensions">XMINT4 Extensions</a>

