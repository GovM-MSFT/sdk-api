---
UID: NF:imapi2.IDiscFormat2Erase.put_ClientName
title: IDiscFormat2Erase::put_ClientName (imapi2.h)
description: Sets the friendly name of the client.
helpviewer_keywords: ["IDiscFormat2Erase interface [IMAPI]","put_ClientName method","IDiscFormat2Erase.put_ClientName","IDiscFormat2Erase::put_ClientName","imapi.idiscformat2erase_put_clientname","imapi2/IDiscFormat2Erase::put_ClientName","put_ClientName","put_ClientName method [IMAPI]","put_ClientName method [IMAPI]","IDiscFormat2Erase interface"]
old-location: imapi\idiscformat2erase_put_clientname.htm
tech.root: imapi
ms.assetid: 641395b1-724b-42d1-b230-a4d6f3844077
ms.date: 12/05/2018
ms.keywords: IDiscFormat2Erase interface [IMAPI],put_ClientName method, IDiscFormat2Erase.put_ClientName, IDiscFormat2Erase::put_ClientName, imapi.idiscformat2erase_put_clientname, imapi2/IDiscFormat2Erase::put_ClientName, put_ClientName, put_ClientName method [IMAPI], put_ClientName method [IMAPI],IDiscFormat2Erase interface
req.header: imapi2.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista, Windows XP with SP2 [desktop apps only]
req.target-min-winversvr: Windows Server 2003 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Imapi2.idl
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
 - IDiscFormat2Erase::put_ClientName
 - imapi2/IDiscFormat2Erase::put_ClientName
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - imapi2.h
api_name:
 - IDiscFormat2Erase.put_ClientName
---

# IDiscFormat2Erase::put_ClientName


## -description

Sets the friendly name of the client.

## -parameters

### -param value [in]

Name of the client application.

## -returns

S_OK is returned on success, but other success codes may be returned as a result of implementation. The following error codes are commonly returned on operation failure, but do not represent the only possible error values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
Failed to allocate the required memory.

Value: 0x8007000E

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
One or more arguments are not valid.

Value: 0x80070057

</td>
</tr>
</table>

## -remarks

The name is used when the write operation requests exclusive access to the device. The <a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-idiscrecorder2-get_exclusiveaccessowner">IDiscRecorder2::get_ExclusiveAccessOwner</a> property contains the name of the client that has the lock.

Because any application with read/write access to the CDROM device during the erase operation can use the IOCTL_CDROM_EXCLUSIVE_ACCESS (query) control code (see the Microsoft Windows Driver Development Kit (DDK)) to access the name, it is important that the name identify the program that is using this interface to erase to the media. The name is restricted to the same character set as required by the IOCTL_CDROM_EXCLUSIVE_ACCESS control code.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nn-imapi2-idiscformat2erase">IDiscFormat2Erase</a>



<a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-idiscformat2erase-get_clientname">IDiscFormat2Erase::get_ClientName</a>

