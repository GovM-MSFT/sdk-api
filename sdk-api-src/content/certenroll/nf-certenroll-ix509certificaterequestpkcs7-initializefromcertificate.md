---
UID: NF:certenroll.IX509CertificateRequestPkcs7.InitializeFromCertificate
title: IX509CertificateRequestPkcs7::InitializeFromCertificate (certenroll.h)
description: Initializes the certificate request by using an existing certificate.
helpviewer_keywords: ["IX509CertificateRequestPkcs7 interface [Security]","InitializeFromCertificate method","IX509CertificateRequestPkcs7.InitializeFromCertificate","IX509CertificateRequestPkcs7::InitializeFromCertificate","InheritDefault","InheritExtensionsFlag","InheritNewDefaultKey","InheritNewSimilarKey","InheritPrivateKey","InheritPublicKey","InheritRenewalCertificateFlag","InheritSubjectAltNameFlag","InheritSubjectFlag","InheritTemplateFlag","InheritValidityPeriodFlag","InitializeFromCertificate","InitializeFromCertificate method [Security]","InitializeFromCertificate method [Security]","IX509CertificateRequestPkcs7 interface","certenroll/IX509CertificateRequestPkcs7::InitializeFromCertificate","security.ix509certificaterequestpkcs7_initializefromcertificate_method"]
old-location: security\ix509certificaterequestpkcs7_initializefromcertificate_method.htm
tech.root: security
ms.assetid: 7500b714-4608-4da6-85ad-20cea30853cc
ms.date: 12/05/2018
ms.keywords: IX509CertificateRequestPkcs7 interface [Security],InitializeFromCertificate method, IX509CertificateRequestPkcs7.InitializeFromCertificate, IX509CertificateRequestPkcs7::InitializeFromCertificate, InheritDefault, InheritExtensionsFlag, InheritNewDefaultKey, InheritNewSimilarKey, InheritPrivateKey, InheritPublicKey, InheritRenewalCertificateFlag, InheritSubjectAltNameFlag, InheritSubjectFlag, InheritTemplateFlag, InheritValidityPeriodFlag, InitializeFromCertificate, InitializeFromCertificate method [Security], InitializeFromCertificate method [Security],IX509CertificateRequestPkcs7 interface, certenroll/IX509CertificateRequestPkcs7::InitializeFromCertificate, security.ix509certificaterequestpkcs7_initializefromcertificate_method
req.header: certenroll.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista [desktop apps only]
req.target-min-winversvr: Windows Server 2008 [desktop apps only]
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
req.dll: CertEnroll.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - IX509CertificateRequestPkcs7::InitializeFromCertificate
 - certenroll/IX509CertificateRequestPkcs7::InitializeFromCertificate
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
 - IX509CertificateRequestPkcs7.InitializeFromCertificate
---

# IX509CertificateRequestPkcs7::InitializeFromCertificate


## -description

The <b>InitializeFromCertificate</b> method initializes the certificate request by using an existing certificate. The certificate is contained in a byte array encoded by using <a href="https://docs.microsoft.com/windows/desktop/SecGloss/d-gly">Distinguished Encoding Rules</a> (DER) as defined by the <a href="https://docs.microsoft.com/windows/desktop/SecGloss/a-gly">Abstract Syntax Notation One</a> (ASN.1) standard. The DER-encoded byte array is represented by a string that  is either a pure binary sequence or is Unicode encoded.

## -parameters

### -param Context [in]

An <a href="https://docs.microsoft.com/windows/desktop/api/certenroll/ne-certenroll-x509certificateenrollmentcontext">X509CertificateEnrollmentContext</a> enumeration value that specifies whether the requested certificate is intended for an end user, a computer, or an administrator acting on behalf of the computer.

### -param RenewalRequest [in]

A <b>VARIANT_BOOL</b> that indicates whether the end entity is requesting that the certificate identified by the  <i>strCertificate</i> parameter be renewed.

### -param strCertificate [in]

A <b>BSTR</b> variable that contains the DER-encoded  certificate.

Beginning with Windows 7 and Windows Server 2008 R2, you can specify a certificate thumb print or serial number rather than an encoded certificate. Doing so causes the function to search the appropriate local stores for the matching certificate. Keep in mind the following points:

<ul>
<li>The <b>BSTR</b> must be an even number of hexadecimal digits.</li>
<li>Whitespace between hexadecimal pairs is ignored.</li>
<li>The <i>Encoding</i> parameter must be set to <b>XCN_CRYPT_STRING_HEXRAW</b>.</li>
<li>The <i>Context</i> parameter determines whether the local or computer stores or both are searched.</li>
<li>If a private key is needed, only the personal and request stores are searched.</li>
<li>If a private key is not needed, the root and intermediate CA stores are also searched.</li>
</ul>

### -param Encoding [in]

An <a href="https://docs.microsoft.com/windows/desktop/api/certenroll/ne-certenroll-encodingtype">EncodingType</a> enumeration value that specifies the type of encoding applied to  the DER-encoded  certificate. The default value is <b>XCN_CRYPT_STRING_BASE64</b>.

### -param InheritOptions [in]

An <a href="https://docs.microsoft.com/windows/desktop/api/certenroll/ne-certenroll-x509requestinheritoptions">X509RequestInheritOptions</a> enumeration value that specifies how to create the certificate request object from the existing certificate. You can specify how to inherit a key by choosing one of the following values.  The default value is <b>InheritDefault</b>.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="InheritDefault"></a><a id="inheritdefault"></a><a id="INHERITDEFAULT"></a><dl>
<dt><b><b>InheritDefault</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Provider and key inheritance is not specified.

</td>
</tr>
<tr>
<td width="40%"><a id="InheritNewDefaultKey"></a><a id="inheritnewdefaultkey"></a><a id="INHERITNEWDEFAULTKEY"></a><dl>
<dt><b><b>InheritNewDefaultKey</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Creates a new key but inherits the default cryptographic provider.

</td>
</tr>
<tr>
<td width="40%"><a id="InheritNewSimilarKey"></a><a id="inheritnewsimilarkey"></a><a id="INHERITNEWSIMILARKEY"></a><dl>
<dt><b><b>InheritNewSimilarKey</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Creates a new key but inherits the cryptographic provider used to create the existing certificate.

</td>
</tr>
<tr>
<td width="40%"><a id="InheritPrivateKey"></a><a id="inheritprivatekey"></a><a id="INHERITPRIVATEKEY"></a><dl>
<dt><b><b>InheritPrivateKey</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Inherits the private and public keys.

</td>
</tr>
<tr>
<td width="40%"><a id="InheritPublicKey"></a><a id="inheritpublickey"></a><a id="INHERITPUBLICKEY"></a><dl>
<dt><b><b>InheritPublicKey</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Inherits only the public key.

</td>
</tr>
</table>
 

You can also use a bitwise-<b>AND</b> operation to combine the key inheritance value with any combination of the  following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="InheritRenewalCertificateFlag"></a><a id="inheritrenewalcertificateflag"></a><a id="INHERITRENEWALCERTIFICATEFLAG"></a><dl>
<dt><b><b>InheritRenewalCertificateFlag</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Inherits the renewal certificate. Specifying this flag sets an <a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nn-certenroll-icertpropertyrenewal">ICertPropertyRenewal</a> value.

</td>
</tr>
<tr>
<td width="40%"><a id="InheritTemplateFlag"></a><a id="inherittemplateflag"></a><a id="INHERITTEMPLATEFLAG"></a><dl>
<dt><b><b>InheritTemplateFlag</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Inherits the certificate template.

</td>
</tr>
<tr>
<td width="40%"><a id="InheritSubjectFlag"></a><a id="inheritsubjectflag"></a><a id="INHERITSUBJECTFLAG"></a><dl>
<dt><b><b>InheritSubjectFlag</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Inherits the subject distinguished name.

</td>
</tr>
<tr>
<td width="40%"><a id="InheritExtensionsFlag"></a><a id="inheritextensionsflag"></a><a id="INHERITEXTENSIONSFLAG"></a><dl>
<dt><b><b>InheritExtensionsFlag</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Inherits the relevant extensions from the certificate.

</td>
</tr>
<tr>
<td width="40%"><a id="InheritSubjectAltNameFlag"></a><a id="inheritsubjectaltnameflag"></a><a id="INHERITSUBJECTALTNAMEFLAG"></a><dl>
<dt><b><b>InheritSubjectAltNameFlag</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Inherits the <b>SubjectAlternativeName</b> extension.

</td>
</tr>
<tr>
<td width="40%"><a id="InheritValidityPeriodFlag"></a><a id="inheritvalidityperiodflag"></a><a id="INHERITVALIDITYPERIODFLAG"></a><dl>
<dt><b><b>InheritValidityPeriodFlag</b></b></dt>
<dt></dt>
</dl>
</td>
<td width="60%">
Inherits the validity period.

</td>
</tr>
</table>
 

You can also specify <b>InheritNone</b> to prevent any of the flags in the preceding table (flags not related to key inheritance) from being implemented by default. If you specify <b>InheritNone</b> but also specify a flag not related to key inheritance, the method returns <b>E_INVALIDARG</b>.

If you set the <i>InheritOptions</i> parameter to zero (0) or specify <b>InheritDefault</b> and do not specify a key inheritance value, <b>InheritNewSimilarKey</b> is used by default.

If you set the <i>InheritOptions</i> parameter to zero (0) or specify <b>InheritDefault</b> and do not specify any of the values not related to key inheritance, the following flags are set by default:<ul>
<li><b>InheritSubjectFlag</b></li>
<li><b>InheritExtensionsFlag</b></li>
<li><b>InheritValidityPeriodFlag</b></li>
<li><b>InheritTemplateFlag</b> (if the certificate contains a template extension)</li>
<li><b>InheritRenewalCertificateFlag</b> (if the client is renewing a  certificate)</li>
</ul>

## -returns

If the function succeeds, the function returns <b>S_OK</b>.

If the function fails, it returns an <b>HRESULT</b> value that indicates the error. Possible values include, but are not limited to, those in the following table. For a list of common error codes, see <a href="https://docs.microsoft.com/windows/desktop/SecCrypto/common-hresult-values">Common HRESULT Values</a>.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_ALREADY_INITIALIZED</b></dt>
</dl>
</td>
<td width="60%">
The certificate request object has already been initialized.

</td>
</tr>
</table>

## -remarks

The <b>InitializeFromCertificate</b> method validates the options specified in the <i>InheritOptions</i> parameter and initializes a new PKCS #7  request object by performing the following actions:<ul>
<li>Creates a PKCS #10 request object from the certificate, enrollment context, and inherit options specified on input. The PKCS #10 object inherits:<ul>
<li>The template if one exists in the original certificate and you set the <b>InheritTemplateFlag</b> value.</li>
<li>The subject distinguished name if you specify <b>InheritSubjectFlag</b>.</li>
<li>The subject alternative name if you specify <b>InheritSubjectAltNameFlag</b>.</li>
<li>The extensions if you specify <b>InheritExtensionsFlag</b>.</li>
</ul>
</li>
<li>Copies the original certificate, if it is to be renewed,  to the <a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nf-certenroll-ix509certificaterequest-get_renewalcertificate">RenewalCertificate</a> property on the new PKCS #10 request.</li>
<li>Creates an <a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nn-certenroll-isignercertificate">ISignerCertificate</a> from the original certificate, if it is to be renewed, and sets it on the <a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nf-certenroll-ix509certificaterequestpkcs7-get_signercertificate">SignerCertificate</a> property.</li>
<li>Sets the PKCS #10 request  as the inner request object.</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/certenroll/nn-certenroll-ix509certificaterequestpkcs7">IX509CertificateRequestPkcs7</a>

