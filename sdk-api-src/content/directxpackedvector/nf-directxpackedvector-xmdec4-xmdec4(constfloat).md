---
UID: NF:directxpackedvector.XMDEC4.XMDEC4(constfloat)
title: XMDEC4::XMDEC4(const float) (directxpackedvector.h)
description: Initializes a new instance of XMDEC4 from a four element float array argument.
helpviewer_keywords: ["XMDEC4","XMDEC4 constructor [DirectX Math Support APIs]","XMDEC4 constructor [DirectX Math Support APIs]","XMDEC4 structure","XMDEC4 structure [DirectX Math Support APIs]","XMDEC4 constructor","XMDEC4.XMDEC4","XMDEC4.XMDEC4()","XMDEC4.XMDEC4(const float)","XMDEC4::XMDEC4","XMDEC4::XMDEC4(const float)","dxmath.xmdec4_ctor_1"]
old-location: 
tech.root: dxmath
ms.assetid: 89558567-1467-4133-a768-e65d967814c8
ms.date: 05/06/2019
ms.keywords: XMDEC4, XMDEC4 constructor [DirectX Math Support APIs], XMDEC4 constructor [DirectX Math Support APIs],XMDEC4 structure, XMDEC4 structure [DirectX Math Support APIs],XMDEC4 constructor, XMDEC4.XMDEC4, XMDEC4.XMDEC4(), XMDEC4.XMDEC4(const float), XMDEC4::XMDEC4, XMDEC4::XMDEC4(const float), dxmath.xmdec4_ctor_1
req.header: directxpackedvector.h
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
req.namespace: DirectX::PackedVector
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
 - XMDEC4::XMDEC4
 - directxpackedvector/XMDEC4::XMDEC4
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - DirectXPackedVector.h
api_name:
 - XMDEC4.XMDEC4
---

# XMDEC4::XMDEC4(const float)


## -description

Initializes a new instance of <a href="https://docs.microsoft.com/windows/desktop/api/directxpackedvector/ns-directxpackedvector-xmdec4">XMDEC4</a> from a four element <code>float</code> array argument.

This constructor initializes a new instance of **XMDEC4** from a from a four element float array argument.

<div class="alert"><b>Note</b>  This constructor is only available under C++.</div>

## -parameters

### -param pArray

Four element floating point array containing the values used to initialize the four components of a new instance of **XMDEC4**.

## -remarks

As **XMDEC4** represents a four component integer vector, the fractional part of an element of *pArray* will be truncated.

Array elements are mapped to the vector components of a new instance of XMDEC4 as follows:
	
| Vector Component | Array Element | Range |
|------------------|---------------|-------|
| x | pArray[0] | -511, 511 |
| y | pArray[1] | -511, 511 |
| z | pArray[2] | -511, 511 |
| w | pArray[3] | -1, 1 |

Elements of *pArray* will be clamped to the permitted range prior to assignment to the appropriate member of **XMDEC4**.

The following pseudocode demonstrates the operation of this constructor, which takes advantage of the union of the four components of the **XMDEC4** vector with an instance of <code>uint32_t</code> in the definition of the    structure:

```cpp
XMDEC4 instance;
_x1=min( max( pArray[0], -511.0 ), 511.0 );
_y1=min( max( pArray[1], -511.0 ), 511.0 );
_z1=min( max( pArray[2], -511.0 ), 511.0 );
_w1=min( max( pArray[3], -1.0 ), 1.0 );

instance.v =  ( (int32_t)_w1 << 30) |
              (((int32_t)_z1 & 0x3FF) << 20) |
              (((int32_t)_y1 & 0x3FF) << 10) |
              (((int32_t)_x1 & 0x3FF));
```

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/directxpackedvector/ns-directxpackedvector-xmdec4">XMDEC4</a>

<a href="https://docs.microsoft.com/windows/desktop/dxmath/xmdec4-ctor">XMDEC4 Constructors</a>

