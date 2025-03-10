---
UID: NS:d3d12.D3D12_TEX3D_SRV
title: D3D12_TEX3D_SRV (d3d12.h)
description: Describes the subresources from a 3D texture to use in a shader-resource view.
helpviewer_keywords: ["D3D12_TEX3D_SRV","D3D12_TEX3D_SRV structure","d3d12/D3D12_TEX3D_SRV","direct3d12.d3d12_tex3d_srv"]
old-location: direct3d12\d3d12_tex3d_srv.htm
tech.root: direct3d12
ms.assetid: 21133B2B-7E12-489A-9AD6-4ACB6E6BAABC
ms.date: 12/05/2018
ms.keywords: D3D12_TEX3D_SRV, D3D12_TEX3D_SRV structure, d3d12/D3D12_TEX3D_SRV, direct3d12.d3d12_tex3d_srv
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: D3D12_TEX3D_SRV
req.redist: 
ms.custom: 19H1
f1_keywords:
 - D3D12_TEX3D_SRV
 - d3d12/D3D12_TEX3D_SRV
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3D12.h
api_name:
 - D3D12_TEX3D_SRV
---

# D3D12_TEX3D_SRV structure


## -description

Describes the subresources from a 3D texture to use in a shader-resource view.

## -struct-fields

### -field MostDetailedMip

Index of the most detailed mipmap level to use; this number is between 0 and <b>MipLevels</b> (from the original Texture3D for which <a href="https://docs.microsoft.com/windows/desktop/api/d3d12/nf-d3d12-id3d12device-createshaderresourceview">ID3D12Device::CreateShaderResourceView</a> creates a view) -1.

### -field MipLevels

The maximum number of mipmap levels for the view of the texture. See the remarks in <a href="https://docs.microsoft.com/windows/desktop/api/d3d12/ns-d3d12-d3d12_tex1d_srv">D3D12_TEX1D_SRV</a>.

Set to -1 to indicate all the mipmap levels from <b>MostDetailedMip</b> on down to least detailed.

### -field ResourceMinLODClamp

A value to clamp sample LOD values to. For example, if you specify 2.0f for the clamp value, you ensure that no individual sample accesses a mip level less than 2.0f.

## -remarks

This structure is one member of a shader-resource-view description, <a href="https://docs.microsoft.com/windows/desktop/api/d3d12/ns-d3d12-d3d12_shader_resource_view_desc">D3D12_SHADER_RESOURCE_VIEW_DESC</a>.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/direct3d12/direct3d-12-structures">Core Structures</a>

