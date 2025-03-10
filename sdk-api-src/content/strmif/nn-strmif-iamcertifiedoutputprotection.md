---
UID: NN:strmif.IAMCertifiedOutputProtection
title: IAMCertifiedOutputProtection (strmif.h)
description: The IAMCertifiedOutputProtection interface sends Certified Output Protection Protocol (COPP) messages to the graphics driver.
helpviewer_keywords: ["IAMCertifiedOutputProtection","IAMCertifiedOutputProtection interface [DirectShow]","IAMCertifiedOutputProtection interface [DirectShow]","described","IAMCertifiedOutputProtectionInterface","dshow.iamcertifiedoutputprotection","strmif/IAMCertifiedOutputProtection"]
old-location: dshow\iamcertifiedoutputprotection.htm
tech.root: dshow
ms.assetid: e5da271d-9528-4bcb-8b76-56fbec2e5855
ms.date: 12/05/2018
ms.keywords: IAMCertifiedOutputProtection, IAMCertifiedOutputProtection interface [DirectShow], IAMCertifiedOutputProtection interface [DirectShow],described, IAMCertifiedOutputProtectionInterface, dshow.iamcertifiedoutputprotection, strmif/IAMCertifiedOutputProtection
req.header: strmif.h
req.include-header: Dshow.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP with SP2 [desktop apps only]
req.target-min-winversvr: Windows Server 2003 R2 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Strmiids.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - IAMCertifiedOutputProtection
 - strmif/IAMCertifiedOutputProtection
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Strmiids.lib
 - Strmiids.dll
api_name:
 - IAMCertifiedOutputProtection
---

# IAMCertifiedOutputProtection interface


## -description

The <code>IAMCertifiedOutputProtection</code> interface sends Certified Output Protection Protocol (COPP) messages to the graphics driver. This interface is exposed by the Video Mixing Renderer 7 (VMR-7) and Video Mixing Renderer 9 (VMR-9) filters.

For information about using COPP, see <a href="https://docs.microsoft.com/windows/desktop/DirectShow/using-certified-output-protection-protocol--copp">Using Certified Output Protection Protocol (COPP)</a>.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IAMCertifiedOutputProtection</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IAMCertifiedOutputProtection</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IAMCertifiedOutputProtection</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/strmif/nf-strmif-iamcertifiedoutputprotection-keyexchange">KeyExchange</a>
</td>
<td align="left" width="63%">
Returns the graphics driver's certificate.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/strmif/nf-strmif-iamcertifiedoutputprotection-protectioncommand">ProtectionCommand</a>
</td>
<td align="left" width="63%">
Sends a COPP command to the graphics driver.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/strmif/nf-strmif-iamcertifiedoutputprotection-protectionstatus">ProtectionStatus</a>
</td>
<td align="left" width="63%">
Sends a COPP status request to the graphics driver

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/strmif/nf-strmif-iamcertifiedoutputprotection-sessionsequencestart">SessionSequenceStart</a>
</td>
<td align="left" width="63%">
Initiates the COPP session with the graphics driver.

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/DirectShow/interfaces">Interfaces</a>

