---
UID: NF:d3d12.ID3D12Device.CreateReservedResource
title: ID3D12Device::CreateReservedResource
description: Creates a resource that is reserved, and not yet mapped to any pages in a heap.
helpviewer_keywords: ["CreateReservedResource","CreateReservedResource method","CreateReservedResource method","ID3D12Device interface","ID3D12Device interface","CreateReservedResource method","ID3D12Device.CreateReservedResource","ID3D12Device::CreateReservedResource","d3d12/ID3D12Device::CreateReservedResource","direct3d12.id3d12device_createreservedresource"]
old-location: direct3d12\id3d12device_createreservedresource.htm
tech.root: direct3d12
ms.assetid: 37E74129-1B5C-4997-A584-D7E9F92342EA
ms.date: 12/05/2018
ms.keywords: CreateReservedResource, CreateReservedResource method, CreateReservedResource method,ID3D12Device interface, ID3D12Device interface,CreateReservedResource method, ID3D12Device.CreateReservedResource, ID3D12Device::CreateReservedResource, d3d12/ID3D12Device::CreateReservedResource, direct3d12.id3d12device_createreservedresource
req.header: d3d12.h
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
req.lib: D3D12.lib
req.dll: D3D12.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - ID3D12Device::CreateReservedResource
 - d3d12/ID3D12Device::CreateReservedResource
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - D3D12.dll
api_name:
 - ID3D12Device.CreateReservedResource
---

## -description

Creates a resource that is reserved, and not yet mapped to any pages in a heap.

## -parameters

### -param pDesc [in]

Type: **const [D3D12_RESOURCE_DESC](/windows/win32/api/d3d12/ns-d3d12-d3d12_resource_desc)\***

A pointer to a **D3D12_RESOURCE_DESC** structure that describes the resource.

### -param InitialState [in]

Type: **[D3D12_RESOURCE_STATES](/windows/win32/api/d3d12/ne-d3d12-d3d12_resource_states)**

The initial state of the resource, as a bitwise-OR'd combination of **D3D12_RESOURCE_STATES** enumeration constants.

### -param pOptimizedClearValue [in, optional]

Type: **const [D3D12_CLEAR_VALUE](/windows/win32/api/d3d12/ns-d3d12-d3d12_clear_value)\***

Specifies a **D3D12_CLEAR_VALUE** structure that describes the default value for a clear color.

*pOptimizedClearValue* specifies a value for which clear operations are most optimal. When the created resource is a texture with either the [D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET](/windows/win32/api/d3d12/ne-d3d12-d3d12_resource_flags) or **D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL** flags, you should choose the value with which the clear operation will most commonly be called. You can call the clear operation with other values, but those operations won't be as efficient as when the value matches the one passed in to resource creation.

When you use [D3D12_RESOURCE_DIMENSION_BUFFER](/windows/win32/api/d3d12/ne-d3d12-d3d12_resource_dimension), you must set *pOptimizedClearValue* to `nullptr`.

### -param riid [in]

Type: **REFIID**

A reference to the globally unique identifier (**GUID**) of the resource interface to return in *ppvResource*. See **Remarks**.

While *riidResource* is most commonly the **GUID** of [ID3D12Resource](/windows/win32/api/d3d12/nn-d3d12-id3d12resource), it may be the **GUID** of any interface. If the resource object doesn't support the interface for this **GUID**, then creation fails with **E_NOINTERFACE**.

### -param ppvResource [out, optional]

Type: **void\*\***

An optional pointer to a memory block that receives the requested interface pointer to the created resource object.

*ppvResource* can be `nullptr`, to enable capability testing. When *ppvResource* is `nullptr`, no object is created, and **S_FALSE** is returned when *pDesc* is valid.

## -returns

Type: **[HRESULT](/windows/win32/com/structure-of-com-error-codes)**

If the function succeeds, it returns **S_OK**. Otherwise, it returns an [**HRESULT**](/windows/win32/com/structure-of-com-error-codes) [error code](/windows/win32/com/com-error-codes-10).

|Return value|Description|
|-|-|
|E_OUTOFMEMORY|There is insufficient memory to create the resource.|

See [Direct3D 12 return codes](/windows/win32/direct3d12/d3d12-graphics-reference-returnvalues) for other possible return values.

## -remarks

**CreateReservedResource** is equivalent to [D3D11_RESOURCE_MISC_TILED](/windows/win32/api/d3d11/ne-d3d11-d3d11_resource_misc_flag) in Direct3D 11. It creates a resource with virtual memory only, no backing store.

You need to map the resource to physical memory (that is, to a heap) using <a href="/windows/win32/api/d3d12/nf-d3d12-id3d12commandqueue-copytilemappings">CopyTileMappings</a> and <a href="/windows/win32/api/d3d12/nf-d3d12-id3d12commandqueue-updatetilemappings">UpdateTileMappings</a>.

These resource types can only be created when the adapter supports tiled resource tier 1 or greater. The tiled resource tier defines the behavior of accessing a resource that is not mapped to a heap.

## -see-also

<a href="/windows/win32/api/d3d12/nf-d3d12-id3d12device-createcommittedresource">CreateCommittedResource</a>

<a href="/windows/win32/api/d3d12/nf-d3d12-id3d12device-createplacedresource">CreatePlacedResource</a>

<a href="/windows/win32/api/d3d12/nn-d3d12-id3d12device">ID3D12Device</a>

