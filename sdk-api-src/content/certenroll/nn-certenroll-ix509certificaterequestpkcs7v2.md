---
UID: NN:certenroll.IX509CertificateRequestPkcs7V2
title: IX509CertificateRequestPkcs7V2 (certenroll.h)
description: The IX509CertificateRequestPkcs7V2 interface represents a PKCS
helpviewer_keywords: ["IX509CertificateRequestPkcs7V2","IX509CertificateRequestPkcs7V2 interface [Security]","IX509CertificateRequestPkcs7V2 interface [Security]","described","certenroll/IX509CertificateRequestPkcs7V2","security.ix509certificaterequestpkcs7v2"]
old-location: security\ix509certificaterequestpkcs7v2.htm
tech.root: security
ms.assetid: e58e1122-2ef0-4902-a9e9-23934cc544ec
ms.date: 12/05/2018
ms.keywords: IX509CertificateRequestPkcs7V2, IX509CertificateRequestPkcs7V2 interface [Security], IX509CertificateRequestPkcs7V2 interface [Security],described, certenroll/IX509CertificateRequestPkcs7V2, security.ix509certificaterequestpkcs7v2
req.header: certenroll.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 7 [desktop apps only]
req.target-min-winversvr: Windows Server 2008 R2 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: CertEnroll.dll
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - IX509CertificateRequestPkcs7V2
 - certenroll/IX509CertificateRequestPkcs7V2
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - CertEnroll.dll
api_name:
 - IX509CertificateRequestPkcs7V2
---

# IX509CertificateRequestPkcs7V2 interface


## -description

The <b>IX509CertificateRequestPkcs7V2</b> interface represents a PKCS #10 certificate request. It includes all of the methods defined by the <a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nn-certenroll-ix509certificaterequestpkcs7">IX509CertificateRequestPkcs7</a> interface and adds a method that enables initialization from a certificate request template, methods to retrieve the template and certificate enrollment policy server used during initialization, and a method to verify the certificate signature.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IX509CertificateRequestPkcs7V2</b> interface inherits from <a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nn-certenroll-ix509certificaterequestpkcs7">IX509CertificateRequestPkcs7</a>. <b>IX509CertificateRequestPkcs7V2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IX509CertificateRequestPkcs7V2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nf-certenroll-ix509certificaterequestpkcs7v2-checkcertificatesignature">CheckCertificateSignature</a>
</td>
<td align="left" width="63%">
Verifies the certificate signature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nf-certenroll-ix509certificaterequestpkcs7v2-initializefromtemplate">InitializeFromTemplate</a>
</td>
<td align="left" width="63%">
Initializes the certificate request by using a template.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IX509CertificateRequestPkcs7V2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nf-certenroll-ix509certificaterequestpkcs7v2-get_policyserver">PolicyServer</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Retrieves the certificate enrollment policy (CEP) server that contains the template used during initialization.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nf-certenroll-ix509certificaterequestpkcs7v2-get_template">Template</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Retrieves the certificate request template used during initialization.

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nn-certenroll-ix509certificaterequest">IX509CertificateRequest</a>



<a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nn-certenroll-ix509certificaterequestpkcs7">IX509CertificateRequestPkcs7</a>

