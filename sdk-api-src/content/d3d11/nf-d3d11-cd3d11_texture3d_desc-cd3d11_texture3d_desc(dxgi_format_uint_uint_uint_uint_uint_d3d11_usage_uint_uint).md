---
UID: NF:d3d11.CD3D11_TEXTURE3D_DESC.CD3D11_TEXTURE3D_DESC(DXGI_FORMAT,UINT,UINT,UINT,UINT,UINT,D3D11_USAGE,UINT,UINT)
title: CD3D11_TEXTURE3D_DESC::CD3D11_TEXTURE3D_DESC(DXGI_FORMAT,UINT,UINT,UINT,UINT,UINT,D3D11_USAGE,UINT,UINT) (d3d11.h)
description: Instantiates a new instance of a CD3D11_TEXTURE3D_DESC structure that is initialized with D3D11_TEXTURE3D_DESC values.
helpviewer_keywords: ["CD3D11_TEXTURE3D_DESC","CD3D11_TEXTURE3D_DESC constructor [Direct3D 11]","CD3D11_TEXTURE3D_DESC constructor [Direct3D 11]","CD3D11_TEXTURE3D_DESC interface","CD3D11_TEXTURE3D_DESC interface [Direct3D 11]","CD3D11_TEXTURE3D_DESC constructor","CD3D11_TEXTURE3D_DESC.CD3D11_TEXTURE3D_DESC","CD3D11_TEXTURE3D_DESC.CD3D11_TEXTURE3D_DESC(DXGI_FORMAT","UINT","UINT","UINT","UINT","UINT","D3D11_USAGE","UINT","UINT)","CD3D11_TEXTURE3D_DESC::CD3D11_TEXTURE3D_DESC","CD3D11_TEXTURE3D_DESC::CD3D11_TEXTURE3D_DESC(DXGI_FORMAT","UINT","UINT","UINT","UINT","UINT","D3D11_USAGE","UINT","UINT)","d3d11/CD3D11_TEXTURE3D_DESC::CD3D11_TEXTURE3D_DESC","direct3d11.cd3d11_texture3d_desc_cd3d11_texture3d_desc_d3d11_texture3d_desc_values_"]
old-location: direct3d11\cd3d11_texture3d_desc_cd3d11_texture3d_desc_d3d11_texture3d_desc_values_.htm
tech.root: direct3d11
ms.assetid: 4623BE8D-55C9-4CB2-9F0E-40ABE5667EAD
ms.date: 12/05/2018
ms.keywords: CD3D11_TEXTURE3D_DESC, CD3D11_TEXTURE3D_DESC constructor [Direct3D 11], CD3D11_TEXTURE3D_DESC constructor [Direct3D 11],CD3D11_TEXTURE3D_DESC interface, CD3D11_TEXTURE3D_DESC interface [Direct3D 11],CD3D11_TEXTURE3D_DESC constructor, CD3D11_TEXTURE3D_DESC.CD3D11_TEXTURE3D_DESC, CD3D11_TEXTURE3D_DESC.CD3D11_TEXTURE3D_DESC(DXGI_FORMAT,UINT,UINT,UINT,UINT,UINT,D3D11_USAGE,UINT,UINT), CD3D11_TEXTURE3D_DESC::CD3D11_TEXTURE3D_DESC, CD3D11_TEXTURE3D_DESC::CD3D11_TEXTURE3D_DESC(DXGI_FORMAT,UINT,UINT,UINT,UINT,UINT,D3D11_USAGE,UINT,UINT), d3d11/CD3D11_TEXTURE3D_DESC::CD3D11_TEXTURE3D_DESC, direct3d11.cd3d11_texture3d_desc_cd3d11_texture3d_desc_d3d11_texture3d_desc_values_
req.header: d3d11.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 7 [desktop apps \| UWP apps]
req.target-min-winversvr: Windows Server 2008 R2 [desktop apps \| UWP apps]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: D3D11.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - CD3D11_TEXTURE3D_DESC::CD3D11_TEXTURE3D_DESC
 - d3d11/CD3D11_TEXTURE3D_DESC::CD3D11_TEXTURE3D_DESC
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - D3D11.lib
 - D3D11.dll
api_name:
 - CD3D11_TEXTURE3D_DESC.CD3D11_TEXTURE3D_DESC
---

# CD3D11_TEXTURE3D_DESC::CD3D11_TEXTURE3D_DESC(DXGI_FORMAT,UINT,UINT,UINT,UINT,UINT,D3D11_USAGE,UINT,UINT)


## -description

Instantiates a new instance of a <a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/jj151706(v=vs.85)">CD3D11_TEXTURE3D_DESC</a> structure that is initialized with <a href="https://docs.microsoft.com/windows/desktop/api/d3d11/ns-d3d11-d3d11_texture3d_desc">D3D11_TEXTURE3D_DESC</a> values.

## -parameters

### -param format

Type: <b><a href="https://docs.microsoft.com/windows/desktop/api/dxgiformat/ne-dxgiformat-dxgi_format">DXGI_FORMAT</a></b>

A <a href="https://docs.microsoft.com/windows/desktop/api/dxgiformat/ne-dxgiformat-dxgi_format">DXGI_FORMAT</a>-typed value that specifies the texture format.

### -param width

Type: <b><a href="https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types">UINT</a></b>

Texture width (in texels). The  range is from 1 to D3D11_REQ_TEXTURE3D_U_V_OR_W_DIMENSION (2048). However, the range is actually constrained by the <a href="https://docs.microsoft.com/windows/desktop/direct3d11/overviews-direct3d-11-devices-downlevel-intro">feature level</a> at which you create the rendering device.

### -param height

Type: <b><a href="https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types">UINT</a></b>

Texture height (in texels). The  range is from 1 to D3D11_REQ_TEXTURE3D_U_V_OR_W_DIMENSION (2048). However, the range is actually constrained by the <a href="https://docs.microsoft.com/windows/desktop/direct3d11/overviews-direct3d-11-devices-downlevel-intro">feature level</a> at which you create the rendering device.

### -param depth

Type: <b><a href="https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types">UINT</a></b>

Texture depth (in texels). The  range is from 1 to D3D11_REQ_TEXTURE3D_U_V_OR_W_DIMENSION (2048). However, the range is actually constrained by the <a href="https://docs.microsoft.com/windows/desktop/direct3d11/overviews-direct3d-11-devices-downlevel-intro">feature level</a> at which you create the rendering device.

### -param mipLevels

Type: <b><a href="https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types">UINT</a></b>

The maximum number of mipmap levels in the texture. See the remarks in <a href="https://docs.microsoft.com/windows/desktop/api/d3d11/ns-d3d11-d3d11_tex1d_srv">D3D11_TEX1D_SRV</a>. Use 1 for a multisampled texture; or 0 to generate a full set of subtextures.

### -param bindFlags

Type: <b><a href="https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types">UINT</a></b>

A combination of <a href="https://docs.microsoft.com/windows/desktop/api/d3d11/ne-d3d11-d3d11_bind_flag">D3D11_BIND_FLAG</a>-typed values that are combined by using a bitwise OR operation. The resulting value specifies how to bind the texture to pipeline stages.

### -param usage

Type: <b><a href="https://docs.microsoft.com/windows/desktop/api/d3d11/ne-d3d11-d3d11_usage">D3D11_USAGE</a></b>

A <a href="https://docs.microsoft.com/windows/desktop/api/d3d11/ne-d3d11-d3d11_usage">D3D11_USAGE</a>-typed value that identifies how the texture is to be read from and written to.

### -param cpuaccessFlags

Type: <b><a href="https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types">UINT</a></b>

A combination of <a href="https://docs.microsoft.com/windows/desktop/api/d3d11/ne-d3d11-d3d11_cpu_access_flag">D3D11_CPU_ACCESS_FLAG</a>-typed values that are combined by using a bitwise OR operation. The resulting value specifies the types of CPU access allowed.

### -param miscFlags

Type: <b><a href="https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types">UINT</a></b>

A combination of <a href="https://docs.microsoft.com/windows/desktop/api/d3d11/ne-d3d11-d3d11_resource_misc_flag">D3D11_RESOURCE_MISC_FLAG</a>-typed values that are combined by using a bitwise OR operation. The resulting value identifies other, less common resource options.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/jj151706(v=vs.85)">CD3D11_TEXTURE3D_DESC</a>

