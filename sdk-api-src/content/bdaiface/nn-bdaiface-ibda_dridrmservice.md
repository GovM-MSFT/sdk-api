---
UID: NN:bdaiface.IBDA_DRIDRMService
title: IBDA_DRIDRMService (bdaiface.h)
description: The IBDA_DRIDRMService interface implements a Digital Rights Management (DRM) service for Media Transform Devices (MTDs) under the Protected Broadcast Driver Architecture (PBDA).
helpviewer_keywords: ["IBDA_DRIDRMService","IBDA_DRIDRMService interface [DirectShow]","IBDA_DRIDRMService interface [DirectShow]","described","bdaiface/IBDA_DRIDRMService","mstv.ibda_dridrmservice"]
old-location: mstv\ibda_dridrmservice.htm
tech.root: mstv
ms.assetid: 9b04c960-a766-4322-bf18-e59176ee2ad1
ms.date: 12/05/2018
ms.keywords: IBDA_DRIDRMService, IBDA_DRIDRMService interface [DirectShow], IBDA_DRIDRMService interface [DirectShow],described, bdaiface/IBDA_DRIDRMService, mstv.ibda_dridrmservice
req.header: bdaiface.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 7 [desktop apps only]
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Bdaiface.idl
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
 - IBDA_DRIDRMService
 - bdaiface/IBDA_DRIDRMService
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - bdaiface.h
api_name:
 - IBDA_DRIDRMService
---

# IBDA_DRIDRMService interface


## -description

The <b>IBDA_DRIDRMService</b> interface implements a Digital Rights Management (DRM) service for Media Transform Devices (MTDs) under the Protected Broadcast Driver Architecture (PBDA). This service allows conditional-access (CA) content to move between an MTD and a Media Sink Device (MSD) under DRM protection in a PBDA graph.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBDA_DRIDRMService</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IBDA_DRIDRMService</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IBDA_DRIDRMService</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/bdaiface/nf-bdaiface-ibda_dridrmservice-getdrmstatus">GetDRMStatus</a>
</td>
<td align="left" width="63%">
Gets status information about the supported DRM services  that are set for an MTD. 
          

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/bdaiface/nf-bdaiface-ibda_dridrmservice-getpairingstatus">GetPairingStatus</a>
</td>
<td align="left" width="63%">
Gets status information about secure pairing between an MTD and an MSD in the graph.
          

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/bdaiface/nf-bdaiface-ibda_dridrmservice-setdrm">SetDRM</a>
</td>
<td align="left" width="63%">
Sets the DRM service used by an MTD.
          

</td>
</tr>
</table>

## -remarks

To declare the interface identifier (IID) for this interface, use the <b>__uuidof</b> operator: <code>__uuidof(IBDA_DRIDRMService)</code>.

