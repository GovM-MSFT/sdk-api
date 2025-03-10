---
UID: NN:strmif.IBPCSatelliteTuner
title: IBPCSatelliteTuner (strmif.h)
description: Note  This interface is not implemented and has been deprecated. The IBPCSatelliteTuner interface supports satellite television tuning.
helpviewer_keywords: ["IBPCSatelliteTuner","IBPCSatelliteTuner interface [DirectShow]","IBPCSatelliteTuner interface [DirectShow]","described","IBPCSatelliteTunerInterface","dshow.ibpcsatellitetuner","strmif/IBPCSatelliteTuner"]
old-location: dshow\ibpcsatellitetuner.htm
tech.root: dshow
ms.assetid: 61b14331-851b-4579-8995-06c6c4e8c8b7
ms.date: 12/05/2018
ms.keywords: IBPCSatelliteTuner, IBPCSatelliteTuner interface [DirectShow], IBPCSatelliteTuner interface [DirectShow],described, IBPCSatelliteTunerInterface, dshow.ibpcsatellitetuner, strmif/IBPCSatelliteTuner
req.header: strmif.h
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
 - IBPCSatelliteTuner
 - strmif/IBPCSatelliteTuner
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - strmif.h
api_name:
 - IBPCSatelliteTuner
---

# IBPCSatelliteTuner interface


## -description

<div class="alert"><b>Note</b>  This interface is not implemented and has been deprecated.</div>
<div> </div>
The <code>IBPCSatelliteTuner</code> interface supports satellite television tuning.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBPCSatelliteTuner</b> interface inherits from <a href="https://docs.microsoft.com/windows/desktop/api/strmif/nn-strmif-iamtuner">IAMTuner</a>. <b>IBPCSatelliteTuner</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IBPCSatelliteTuner</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/strmif/nf-strmif-ibpcsatellitetuner-get_defaultsubchanneltypes">get_DefaultSubChannelTypes</a>
</td>
<td align="left" width="63%">
Gets the default sub-channel types.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/strmif/nf-strmif-ibpcsatellitetuner-istapingpermitted">IsTapingPermitted</a>
</td>
<td align="left" width="63%">
Queries whether taping is permitted.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/strmif/nf-strmif-ibpcsatellitetuner-put_defaultsubchanneltypes">put_DefaultSubChannelTypes</a>
</td>
<td align="left" width="63%">
Sets the default sub-channel types.

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/DirectShow/deprecated-interfaces">Deprecated Interfaces</a>



<a href="https://docs.microsoft.com/windows/desktop/api/strmif/nn-strmif-iamtuner">IAMTuner</a>

