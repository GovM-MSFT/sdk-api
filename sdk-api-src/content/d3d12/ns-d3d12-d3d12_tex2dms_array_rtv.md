---
UID: NS:d3d12.D3D12_TEX2DMS_ARRAY_RTV
title: D3D12_TEX2DMS_ARRAY_RTV (d3d12.h)
description: Describes the subresources from an array of multi sampled 2D textures to use in a render-target view.
helpviewer_keywords: ["D3D12_TEX2DMS_ARRAY_RTV","D3D12_TEX2DMS_ARRAY_RTV structure","d3d12/D3D12_TEX2DMS_ARRAY_RTV","direct3d12.d3d12_tex2dms_array_rtv"]
old-location: direct3d12\d3d12_tex2dms_array_rtv.htm
tech.root: direct3d12
ms.assetid: 9EA35677-1680-4F57-BDE1-5649C1D48661
ms.date: 12/05/2018
ms.keywords: D3D12_TEX2DMS_ARRAY_RTV, D3D12_TEX2DMS_ARRAY_RTV structure, d3d12/D3D12_TEX2DMS_ARRAY_RTV, direct3d12.d3d12_tex2dms_array_rtv
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
req.typenames: D3D12_TEX2DMS_ARRAY_RTV
req.redist: 
ms.custom: 19H1
f1_keywords:
 - D3D12_TEX2DMS_ARRAY_RTV
 - d3d12/D3D12_TEX2DMS_ARRAY_RTV
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
 - D3D12_TEX2DMS_ARRAY_RTV
---

# D3D12_TEX2DMS_ARRAY_RTV structure


## -description

Describes the subresources from an array of multi sampled 2D textures to use in a render-target view.

## -struct-fields

### -field FirstArraySlice

The index of the first texture to use in an array of textures.

### -field ArraySize

The number of textures to use.

## -remarks

Use this structure with a <a href="https://docs.microsoft.com/windows/desktop/api/d3d12/ns-d3d12-d3d12_render_target_view_desc">D3D12_RENDER_TARGET_VIEW_DESC</a> structure to view the resource as an array of multi sampled 2D textures.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/direct3d12/direct3d-12-structures">Core Structures</a>

