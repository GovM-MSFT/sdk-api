---
UID: NF:msctf.ITfInputProcessorProfiles.EnableLanguageProfileByDefault
title: ITfInputProcessorProfiles::EnableLanguageProfileByDefault (msctf.h)
description: ITfInputProcessorProfiles::EnableLanguageProfileByDefault method
helpviewer_keywords: ["EnableLanguageProfileByDefault","EnableLanguageProfileByDefault method [Text Services Framework]","EnableLanguageProfileByDefault method [Text Services Framework]","ITfInputProcessorProfiles interface","ITfInputProcessorProfiles interface [Text Services Framework]","EnableLanguageProfileByDefault method","ITfInputProcessorProfiles.EnableLanguageProfileByDefault","ITfInputProcessorProfiles::EnableLanguageProfileByDefault","_tsf_itfinputprocessorprofiles_enablelanguageprofilebydefault_ref","msctf/ITfInputProcessorProfiles::EnableLanguageProfileByDefault","tsf.itfinputprocessorprofiles_enablelanguageprofilebydefault"]
old-location: tsf\itfinputprocessorprofiles_enablelanguageprofilebydefault.htm
tech.root: TSF
ms.assetid: 5ab40219-278d-4721-88a1-b0bd2e3d8d2f
ms.date: 12/05/2018
ms.keywords: EnableLanguageProfileByDefault, EnableLanguageProfileByDefault method [Text Services Framework], EnableLanguageProfileByDefault method [Text Services Framework],ITfInputProcessorProfiles interface, ITfInputProcessorProfiles interface [Text Services Framework],EnableLanguageProfileByDefault method, ITfInputProcessorProfiles.EnableLanguageProfileByDefault, ITfInputProcessorProfiles::EnableLanguageProfileByDefault, _tsf_itfinputprocessorprofiles_enablelanguageprofilebydefault_ref, msctf/ITfInputProcessorProfiles::EnableLanguageProfileByDefault, tsf.itfinputprocessorprofiles_enablelanguageprofilebydefault
req.header: msctf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 Professional [desktop apps only]
req.target-min-winversvr: Windows 2000 Server [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Msctf.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: Msctf.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: TSF 1.0 on Windows 2000 Professional
ms.custom: 19H1
f1_keywords:
 - ITfInputProcessorProfiles::EnableLanguageProfileByDefault
 - msctf/ITfInputProcessorProfiles::EnableLanguageProfileByDefault
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Msctf.dll
api_name:
 - ITfInputProcessorProfiles.EnableLanguageProfileByDefault
---

# ITfInputProcessorProfiles::EnableLanguageProfileByDefault


## -description

Enables or disables a language profile by default for all users.

## -parameters

### -param rclsid [in]

Contains the CLSID of the text service of the profile to be enabled or disabled.

### -param langid [in]

Contains a <b>LANGID</b> value that specifies the language of the profile to be enabled or disabled.

### -param guidProfile [in]

Contains a GUID value that identifies the profile to be enabled or disabled.

### -param fEnable [in]

Contains a <b>BOOL</b> value that specifies if the profile is enabled or disabled. If this contains a nonzero value, the profile is enabled. If this contains zero, the profile is disabled.

## -returns

This method can return one of these values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
An unspecified error occurred.

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/msctf/nn-msctf-itfinputprocessorprofiles">ITfInputProcessorProfiles</a>



<a href="https://docs.microsoft.com/windows/desktop/api/msctf/nf-msctf-itfinputprocessorprofiles-enablelanguageprofile">ITfInputProcessorProfiles::EnableLanguageProfile
      </a>

