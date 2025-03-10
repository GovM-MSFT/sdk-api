---
UID: NN:d2d1_3.ID2D1ImageSource
title: ID2D1ImageSource (d2d1_3.h)
description: Represents a producer of pixels that can fill an arbitrary 2D plane.
helpviewer_keywords: ["ID2D1ImageSource","ID2D1ImageSource interface [Direct2D]","ID2D1ImageSource interface [Direct2D]","described","d2d1_3/ID2D1ImageSource","direct2d.id2d1imagesource"]
old-location: direct2d\id2d1imagesource.htm
tech.root: Direct2D
ms.assetid: a9ee20db-98cf-bc5f-96d8-232073810cc5
ms.date: 12/05/2018
ms.keywords: ID2D1ImageSource, ID2D1ImageSource interface [Direct2D], ID2D1ImageSource interface [Direct2D],described, d2d1_3/ID2D1ImageSource, direct2d.id2d1imagesource
req.header: d2d1_3.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10 [desktop apps \| UWP apps]
req.target-min-winversvr: Windows Server 2016 [desktop apps \| UWP apps]
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
req.dll: D2d1.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - ID2D1ImageSource
 - d2d1_3/ID2D1ImageSource
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - D2d1.dll
api_name:
 - ID2D1ImageSource
---

# ID2D1ImageSource interface


## -description

Represents a producer of pixels that can fill an arbitrary 2D plane.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">ID2D1ImageSource</b> interface inherits from <a href="https://docs.microsoft.com/windows/desktop/api/d2d1/nn-d2d1-id2d1image">ID2D1Image</a>. <b>ID2D1ImageSource</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>ID2D1ImageSource</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/d2d1_3/nf-d2d1_3-id2d1imagesource-offerresources">OfferResources</a>
</td>
<td align="left" width="63%">
Allows the operating system to free the video memory of resources by discarding their content.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/d2d1_3/nf-d2d1_3-id2d1imagesource-tryreclaimresources">TryReclaimResources</a>
</td>
<td align="left" width="63%">
Restores access to resources that were previously offered by calling <a href="https://docs.microsoft.com/windows/desktop/api/d2d1_3/nf-d2d1_3-id2d1imagesource-offerresources">OfferResources</a>.
        

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/d2d1_3/nf-d2d1_3-createimagesourcefromwic">I2D1DeviceContext2::CreateImageSourceFromWic</a>



<a href="https://docs.microsoft.com/windows/desktop/api/d2d1_3/nf-d2d1_3-id2d1devicecontext2-createimagesourcefromdxgi">ID2D1DeviceContext2::CreateImageSourceFromDxgi</a>



<a href="https://docs.microsoft.com/windows/desktop/api/d2d1/nn-d2d1-id2d1image">ID2D1Image</a>



<a href="https://docs.microsoft.com/windows/desktop/api/d2d1_3/nn-d2d1_3-id2d1imagesourcefromwic">ID2D1ImageSourceFromWic</a>

