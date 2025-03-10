---
UID: NN:oleidl.IOleCache
title: IOleCache (oleidl.h)
description: Provides control of the presentation data that gets cached inside of an object. Cached presentation data is available to the container of the object even when the server application is not running or is unavailable.
helpviewer_keywords: ["IOleCache","IOleCache interface [COM]","IOleCache interface [COM]","described","_ole_iolecache","com.iolecache","oleidl/IOleCache"]
old-location: com\iolecache.htm
tech.root: com
ms.assetid: b5ef85d0-b54e-4831-87f1-ac6763179181
ms.date: 12/05/2018
ms.keywords: IOleCache, IOleCache interface [COM], IOleCache interface [COM],described, _ole_iolecache, com.iolecache, oleidl/IOleCache
req.header: oleidl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 Professional [desktop apps only]
req.target-min-winversvr: Windows 2000 Server [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: OleIdl.Idl
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
 - IOleCache
 - oleidl/IOleCache
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - OleIdl.h
api_name:
 - IOleCache
---

# IOleCache interface


## -description

Provides control of the presentation data that gets cached inside of an object. Cached presentation data is available to the container of the object even when the server application is not running or is unavailable.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IOleCache</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IOleCache</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IOleCache</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolecache-cache">Cache</a>
</td>
<td align="left" width="63%">
Specifies the format and other data to be cached inside an embedded object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolecache-enumcache">EnumCache</a>
</td>
<td align="left" width="63%">
Creates an enumerator that can be used to enumerate the current cache connections.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolecache-initcache">InitCache</a>
</td>
<td align="left" width="63%">
Fills the cache as needed using the  data provided by the specified data object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolecache-setdata">SetData</a>
</td>
<td align="left" width="63%">
Initializes the cache with data in a specified format and on a specified medium.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolecache-uncache">Uncache</a>
</td>
<td align="left" width="63%">
Removes a cache connection created previously using <a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolecache-cache">IOleCache::Cache</a>.

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/objbase/nf-objbase-createdatacache">CreateDataCache</a>



<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nn-oleidl-iolecache2">IOleCache2</a>



<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nn-oleidl-iolecachecontrol">IOleCacheControl</a>

