---
UID: NF:msiquery.MsiGetFeatureStateW
title: MsiGetFeatureStateW function (msiquery.h)
description: The MsiGetFeatureState function gets the requested state of a feature.
helpviewer_keywords: ["INSTALLSTATE_ABSENT","INSTALLSTATE_ADVERTISED","INSTALLSTATE_BADCONFIG","INSTALLSTATE_BROKEN","INSTALLSTATE_DEFAULT","INSTALLSTATE_INCOMPLETE","INSTALLSTATE_INVALIDARG","INSTALLSTATE_LOCAL","INSTALLSTATE_MOREDATA","INSTALLSTATE_SOURCE","INSTALLSTATE_SOURCEABSENT","INSTALLSTATE_UNKNOWN","MsiGetFeatureState","MsiGetFeatureState function","MsiGetFeatureStateA","MsiGetFeatureStateW","_msi_msigetfeaturestate","msiquery/MsiGetFeatureState","msiquery/MsiGetFeatureStateA","msiquery/MsiGetFeatureStateW","setup.msigetfeaturestate"]
old-location: setup\msigetfeaturestate.htm
tech.root: setup
ms.assetid: eb8942b9-996e-45d8-b515-5c84737eb5ed
ms.date: 12/05/2018
ms.keywords: INSTALLSTATE_ABSENT, INSTALLSTATE_ADVERTISED, INSTALLSTATE_BADCONFIG, INSTALLSTATE_BROKEN, INSTALLSTATE_DEFAULT, INSTALLSTATE_INCOMPLETE, INSTALLSTATE_INVALIDARG, INSTALLSTATE_LOCAL, INSTALLSTATE_MOREDATA, INSTALLSTATE_SOURCE, INSTALLSTATE_SOURCEABSENT, INSTALLSTATE_UNKNOWN, MsiGetFeatureState, MsiGetFeatureState function, MsiGetFeatureStateA, MsiGetFeatureStateW, _msi_msigetfeaturestate, msiquery/MsiGetFeatureState, msiquery/MsiGetFeatureStateA, msiquery/MsiGetFeatureStateW, setup.msigetfeaturestate
req.header: msiquery.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Installer 5.0 on Windows Server 2012, Windows 8, Windows Server 2008 R2 or Windows 7. Windows Installer 4.0 or Windows Installer 4.5 on   Windows Server 2008 or Windows Vista. Windows Installer on Windows Server 2003 or Windows XP
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: MsiGetFeatureStateW (Unicode) and MsiGetFeatureStateA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Msi.lib
req.dll: Msi.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - MsiGetFeatureStateW
 - msiquery/MsiGetFeatureStateW
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Msi.dll
api_name:
 - MsiGetFeatureState
 - MsiGetFeatureStateA
 - MsiGetFeatureStateW
---

# MsiGetFeatureStateW function


## -description

The 
<b>MsiGetFeatureState</b> function gets the requested state of a feature.

## -parameters

### -param hInstall [in]

Handle to the installation provided to a DLL custom action or obtained through <a href="https://docs.microsoft.com/windows/desktop/api/msi/nf-msi-msiopenpackagea">MsiOpenPackage</a>, <a href="https://docs.microsoft.com/windows/desktop/api/msi/nf-msi-msiopenpackageexa">MsiOpenPackageEx</a>, or <a href="https://docs.microsoft.com/windows/desktop/api/msi/nf-msi-msiopenproducta">MsiOpenProduct</a>.

### -param szFeature [in]

Specifies the feature name within the product.

### -param piInstalled [out]

Specifies the returned current installed state. This parameter must not be null. This parameter can be one of the following values. 



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_BADCONFIG"></a><a id="installstate_badconfig"></a><dl>
<dt><b>INSTALLSTATE_BADCONFIG</b></dt>
</dl>
</td>
<td width="60%">
The configuration data is corrupt.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_INCOMPLETE"></a><a id="installstate_incomplete"></a><dl>
<dt><b>INSTALLSTATE_INCOMPLETE</b></dt>
</dl>
</td>
<td width="60%">
The installation is suspended or in progress.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_SOURCEABSENT"></a><a id="installstate_sourceabsent"></a><dl>
<dt><b>INSTALLSTATE_SOURCEABSENT</b></dt>
</dl>
</td>
<td width="60%">
The feature must run from the source, and the source is unavailable.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_MOREDATA"></a><a id="installstate_moredata"></a><dl>
<dt><b>INSTALLSTATE_MOREDATA</b></dt>
</dl>
</td>
<td width="60%">
The return buffer is full.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_INVALIDARG"></a><a id="installstate_invalidarg"></a><dl>
<dt><b>INSTALLSTATE_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was passed to the function.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_UNKNOWN"></a><a id="installstate_unknown"></a><dl>
<dt><b>INSTALLSTATE_UNKNOWN</b></dt>
</dl>
</td>
<td width="60%">
An unrecognized product or feature was specified.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_BROKEN"></a><a id="installstate_broken"></a><dl>
<dt><b>INSTALLSTATE_BROKEN</b></dt>
</dl>
</td>
<td width="60%">
The feature is broken.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_ADVERTISED"></a><a id="installstate_advertised"></a><dl>
<dt><b>INSTALLSTATE_ADVERTISED</b></dt>
</dl>
</td>
<td width="60%">
The advertised feature.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_ABSENT"></a><a id="installstate_absent"></a><dl>
<dt><b>INSTALLSTATE_ABSENT</b></dt>
</dl>
</td>
<td width="60%">
The feature was uninstalled.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_LOCAL"></a><a id="installstate_local"></a><dl>
<dt><b>INSTALLSTATE_LOCAL</b></dt>
</dl>
</td>
<td width="60%">
The feature was installed on the local drive.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_SOURCE"></a><a id="installstate_source"></a><dl>
<dt><b>INSTALLSTATE_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The feature must run from the source, CD-ROM, or network.

</td>
</tr>
<tr>
<td width="40%"><a id="INSTALLSTATE_DEFAULT"></a><a id="installstate_default"></a><dl>
<dt><b>INSTALLSTATE_DEFAULT</b></dt>
</dl>
</td>
<td width="60%">
The feature is  installed in the default location: local or source.

</td>
</tr>
</table>

### -param piAction [out]

Receives the action taken during the installation session. This parameter must not be null. For return values, see <i>piInstalled</i>.

## -returns

The 
<b>MsiGetFeatureState</b> function returns the following values:

## -remarks

See 
<a href="https://docs.microsoft.com/windows/desktop/Msi/calling-database-functions-from-programs">Calling Database Functions From Programs</a>.

If the function fails, you can obtain extended error information by using <a href="https://docs.microsoft.com/windows/desktop/api/msiquery/nf-msiquery-msigetlasterrorrecord">MsiGetLastErrorRecord</a>.





> [!NOTE]
> The msiquery.h header defines MsiGetFeatureState as an alias which automatically selects the ANSI or Unicode version of this function based on the definition of the UNICODE preprocessor constant. Mixing usage of the encoding-neutral alias with code that not encoding-neutral can lead to mismatches that result in compilation or runtime errors. For more information, see [Conventions for Function Prototypes](/windows/win32/intl/conventions-for-function-prototypes).

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/Msi/database-functions">Installer Selection Functions</a>



<a href="https://docs.microsoft.com/windows/desktop/Msi/passing-null-as-the-argument-of-windows-installer-functions">Passing Null as the Argument of Windows Installer Functions</a>

