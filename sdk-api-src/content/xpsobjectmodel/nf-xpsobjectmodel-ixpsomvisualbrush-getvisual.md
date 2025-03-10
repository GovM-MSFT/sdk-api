---
UID: NF:xpsobjectmodel.IXpsOMVisualBrush.GetVisual
title: IXpsOMVisualBrush::GetVisual (xpsobjectmodel.h)
description: Gets a pointer to the interface of the resolved visual to be used as the source for the brush.
helpviewer_keywords: ["GetVisual","GetVisual method [XPS Documents and Packaging]","GetVisual method [XPS Documents and Packaging]","IXpsOMVisualBrush interface","IXpsOMVisualBrush interface [XPS Documents and Packaging]","GetVisual method","IXpsOMVisualBrush.GetVisual","IXpsOMVisualBrush::GetVisual","xps.ixpsomvisualbrush_getvisual","xpsobjectmodel/IXpsOMVisualBrush::GetVisual"]
old-location: xps\ixpsomvisualbrush_getvisual.htm
tech.root: xps
ms.assetid: b8fb6698-8ce7-42a1-bad6-bde3d5dbbbf8
ms.date: 12/05/2018
ms.keywords: GetVisual, GetVisual method [XPS Documents and Packaging], GetVisual method [XPS Documents and Packaging],IXpsOMVisualBrush interface, IXpsOMVisualBrush interface [XPS Documents and Packaging],GetVisual method, IXpsOMVisualBrush.GetVisual, IXpsOMVisualBrush::GetVisual, xps.ixpsomvisualbrush_getvisual, xpsobjectmodel/IXpsOMVisualBrush::GetVisual
req.header: xpsobjectmodel.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 7, Windows Vista with SP2 and Platform Update for Windows Vista [desktop apps \| UWP apps]
req.target-min-winversvr: Windows Server 2008 R2, Windows Server 2008 with SP2 and Platform Update for Windows Server 2008 [desktop apps \| UWP apps]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: XpsObjectModel.idl
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
 - IXpsOMVisualBrush::GetVisual
 - xpsobjectmodel/IXpsOMVisualBrush::GetVisual
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - xpsobjectmodel.h
api_name:
 - IXpsOMVisualBrush.GetVisual
---

# IXpsOMVisualBrush::GetVisual


## -description

Gets a pointer to the interface of the resolved visual to be used as the source for the brush.

## -parameters

### -param visual [out, retval]

A pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsomvisual">IXpsOMVisual</a> interface of the resolved visual object used as the source for the brush. If a visual has not been set, a <b>NULL</b> pointer is returned.

The value that is returned in this parameter depends on which method has most recently  been called to set the visual object.

<table>
<tr>
<th>Most recent method called</th>
<th>Object that is returned  in <i>visual</i></th>
</tr>
<tr>
<td>

<a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nf-xpsobjectmodel-ixpsomvisualbrush-setvisuallocal">SetVisualLocal</a>


</td>
<td>
The visual that is set by <a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nf-xpsobjectmodel-ixpsomvisualbrush-setvisuallocal">SetVisualLocal</a>.

</td>
</tr>
<tr>
<td>

<a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nf-xpsobjectmodel-ixpsomvisualbrush-setvisuallookup">SetVisualLookup</a>


</td>
<td>
The visual that is retrieved, with a lookup key that matches the key that is set by <a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nf-xpsobjectmodel-ixpsomvisualbrush-setvisuallookup">SetVisualLookup</a>, from the resource directory.

</td>
</tr>
<tr>
<td>
Neither <a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nf-xpsobjectmodel-ixpsomvisualbrush-setvisuallocal">SetVisualLocal</a> nor <a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nf-xpsobjectmodel-ixpsomvisualbrush-setvisuallookup">SetVisualLookup</a> has been called yet.

</td>
<td>
<b>NULL</b> pointer.

</td>
</tr>
</table>

## -returns

The method returns an <b>HRESULT</b>. Possible values include, but are not limited to, those in the table that follows. For information about  XPS document API return values that are not listed in this table, see <a href="https://docs.microsoft.com/previous-versions/windows/desktop/dd372955(v=vs.85)">XPS Document Errors</a>.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
<i>visual</i> is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>XPS_E_LOOKUP_INVALID_TYPE</b></dt>
</dl>
</td>
<td width="60%">
The lookup key name set by  <a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nf-xpsobjectmodel-ixpsompath-setstrokebrushlookup">SetStrokeBrushLookup</a> references an object that is not a brush.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>XPS_E_LOOKUP_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No object could be found with a key name that matched the lookup value.

</td>
</tr>
</table>

## -remarks

This method returns an  <a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsomvisual">IXpsOMVisual</a> interface pointer. However, the  
	 interface that is returned can be any interface that inherits from   <b>IXpsOMVisual</b>, such as  <a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsomcanvas">IXpsOMCanvas</a>, <a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsompath">IXpsOMPath</a>, 
	  and <a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsomglyphs">IXpsOMGlyphs</a>.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsomcanvas">IXpsOMCanvas</a>



<a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsomglyphs">IXpsOMGlyphs</a>



<a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsompath">IXpsOMPath</a>



<a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsomvisual">IXpsOMVisual</a>



<a href="https://docs.microsoft.com/windows/desktop/api/xpsobjectmodel/nn-xpsobjectmodel-ixpsomvisualbrush">IXpsOMVisualBrush</a>



<a href="https://www.microsoft.com/download/details.aspx?id=11816">XML Paper Specification</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/dd372955(v=vs.85)">XPS Document Errors</a>

