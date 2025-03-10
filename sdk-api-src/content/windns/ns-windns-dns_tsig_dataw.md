---
UID: NS:windns.__unnamed_struct_37
title: DNS_TSIG_DATAW (windns.h)
description: The DNS_TSIG_DATA structure represents a secret key transaction authentication (TSIG) resource record (RR) as specified in RFC 2845 and RFC 3645.
helpviewer_keywords: ["*PDNS_TSIG_DATA","*PDNS_TSIG_DATAW","DNS_RCODE_BADKEY","DNS_RCODE_BADSIG","DNS_RCODE_BADTIME","DNS_TSIG_DATA","DNS_TSIG_DATA structure [DNS]","DNS_TSIG_DATAW","PDNS_TSIG_DATA","PDNS_TSIG_DATA structure pointer [DNS]","_dns_dns_tsig_data","dns.dns_tsig_data","gss-tsig","gss.microsoft.com","windns/DNS_TSIG_DATA","windns/PDNS_TSIG_DATA"]
old-location: dns\dns_tsig_data.htm
tech.root: DNS
ms.assetid: 32077169-d319-45c0-982f-8d470cd70111
ms.date: 12/05/2018
ms.keywords: '*PDNS_TSIG_DATA, *PDNS_TSIG_DATAW, DNS_RCODE_BADKEY, DNS_RCODE_BADSIG, DNS_RCODE_BADTIME, DNS_TSIG_DATA, DNS_TSIG_DATA structure [DNS], DNS_TSIG_DATAW, PDNS_TSIG_DATA, PDNS_TSIG_DATA structure pointer [DNS], _dns_dns_tsig_data, dns.dns_tsig_data, gss-tsig, gss.microsoft.com, windns/DNS_TSIG_DATA, windns/PDNS_TSIG_DATA'
req.header: windns.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 Professional [desktop apps only]
req.target-min-winversvr: Windows 2000 Server [desktop apps only]
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
req.typenames: DNS_TSIG_DATAW, *PDNS_TSIG_DATAW
req.redist: 
ms.custom: 19H1
f1_keywords:
 - PDNS_TSIG_DATAW
 - windns/PDNS_TSIG_DATAW
 - DNS_TSIG_DATAW
 - windns/DNS_TSIG_DATAW
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windns.h
api_name:
 - DNS_TSIG_DATA
---

# DNS_TSIG_DATAW structure


## -description

The 
<b>DNS_TSIG_DATA</b> structure represents a secret key transaction authentication (TSIG) resource record (RR) as specified in <a href="https://www.ietf.org/rfc/rfc2845.txt">RFC 2845</a> and <a href="https://www.ietf.org/rfc/rfc3645.txt">RFC 3645</a>.

## -struct-fields

### -field pNameAlgorithm

A pointer to a string that represents the name of the key used to generate <b>pSignature</b> as defined in section 2.3 of <a href="https://www.ietf.org/rfc/rfc2845.txt">RFC 2845</a>.

### -field pAlgorithmPacket

A pointer to a string that represents the name of the   algorithm used to generate <b>pSignature</b> as defined in section 2.3 of <a href="https://www.ietf.org/rfc/rfc2845.txt">RFC 2845</a>.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="gss.microsoft.com"></a><a id="GSS.MICROSOFT.COM"></a><dl>
<dt><b>"gss.microsoft.com"</b></dt>
</dl>
</td>
<td width="60%">
Windows 2000 Server only: Generic Security Service Algorithm for
        Secret Key Transaction Authentication for DNS (GSS-API) as defined in <a href="https://www.ietf.org/rfc/rfc3645.txt">RFC 3645</a>.

</td>
</tr>
<tr>
<td width="40%"><a id="gss-tsig"></a><a id="GSS-TSIG"></a><dl>
<dt><b>"gss-tsig"</b></dt>
</dl>
</td>
<td width="60%">
Generic Security Service Algorithm for
        Secret Key Transaction Authentication for DNS (GSS-API) as defined in <a href="https://www.ietf.org/rfc/rfc3645.txt">RFC 3645</a>.

</td>
</tr>
</table>

### -field pSignature

A pointer to the Message
   Authentication Code (MAC) generated by the algorithm in <b>pAlgorithmPacket</b>. The length, in bytes, and composition of <b>pSignature</b> are determined by <b>pAlgorithmPacket</b>.

### -field pOtherData

If <b>wError</b> contains the RCODE, <b>BADTIME</b>, <b>pOtherData</b> is a  BYTE array that contains the server's current time, otherwise it is <b>NULL</b>. Time is expressed in seconds since the beginning of January 1, 1970, Greenwich Mean Time (GMT), excluding leap seconds.

### -field i64CreateTime

The time <b>pSignature</b> was generated, expressed in seconds since the beginning of January 1, 1970, Greenwich Mean Time (GMT), excluding leap seconds.

### -field wFudgeTime

The time, in seconds, <b>i64CreateTime</b> may be in error.

### -field wOriginalXid

The <a href="https://docs.microsoft.com/windows/desktop/api/windns/ns-windns-dns_header">Xid</a>  identifier of the original message.

### -field wError

An error, expressed in expanded RCODE format that covers TSIG and TKEY RR processing.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DNS_RCODE_BADSIG"></a><a id="dns_rcode_badsig"></a><dl>
<dt><b>DNS_RCODE_BADSIG</b></dt>
</dl>
</td>
<td width="60%">
The <b>pSignature</b> field is bad.

</td>
</tr>
<tr>
<td width="40%"><a id="DNS_RCODE_BADKEY"></a><a id="dns_rcode_badkey"></a><dl>
<dt><b>DNS_RCODE_BADKEY</b></dt>
</dl>
</td>
<td width="60%">
The <b>pKey</b> field of the <a href="/windows/win32/api/windns/ns-windns-dns_tkey_dataw">DNS_TKEY_DATA</a> RR is bad.

</td>
</tr>
<tr>
<td width="40%"><a id="DNS_RCODE_BADTIME"></a><a id="dns_rcode_badtime"></a><dl>
<dt><b>DNS_RCODE_BADTIME</b></dt>
</dl>
</td>
<td width="60%">
A timestamp is bad.

</td>
</tr>
</table>

### -field wSigLength

The length, in bytes, of the <b>pSignature</b> member.

### -field wOtherLength

The length, in bytes, of the <b>pOtherData</b> member.

### -field cAlgNameLength

The length, in bytes, of the <b>pAlgorithmPacket</b> member.

### -field bPacketPointers

Reserved for future use. Do not use.

## -remarks

The 
<b>DNS_TSIG_DATA</b> structure is used in conjunction with the 
<a href="/windows/win32/api/windns/ns-windns-dns_recorda">DNS_RECORD</a> structure to programmatically manage DNS entries.





> [!NOTE]
> The windns.h header defines DNS_TSIG_DATA as an alias which automatically selects the ANSI or Unicode version of this function based on the definition of the UNICODE preprocessor constant. Mixing usage of the encoding-neutral alias with code that not encoding-neutral can lead to mismatches that result in compilation or runtime errors. For more information, see [Conventions for Function Prototypes](/windows/win32/intl/conventions-for-function-prototypes).

## -see-also

<a href="/windows/win32/api/windns/ns-windns-dns_recorda">DNS_RECORD</a>



<a href="/windows/win32/api/windns/ns-windns-dns_tkey_dataw">DNS_TKEY_DATA</a>

