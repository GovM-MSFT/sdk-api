---
UID: NF:imapi2.IDiscFormat2RawCD.PrepareMedia
title: IDiscFormat2RawCD::PrepareMedia (imapi2.h)
description: Locks the current media for exclusive access.
helpviewer_keywords: ["IDiscFormat2RawCD interface [IMAPI]","PrepareMedia method","IDiscFormat2RawCD.PrepareMedia","IDiscFormat2RawCD::PrepareMedia","PrepareMedia","PrepareMedia method [IMAPI]","PrepareMedia method [IMAPI]","IDiscFormat2RawCD interface","imapi.idiscformat2rawcd_preparemedia","imapi2/IDiscFormat2RawCD::PrepareMedia"]
old-location: imapi\idiscformat2rawcd_preparemedia.htm
tech.root: imapi
ms.assetid: 8c393786-0c2d-4244-8ec3-0ac9e47e76c6
ms.date: 12/05/2018
ms.keywords: IDiscFormat2RawCD interface [IMAPI],PrepareMedia method, IDiscFormat2RawCD.PrepareMedia, IDiscFormat2RawCD::PrepareMedia, PrepareMedia, PrepareMedia method [IMAPI], PrepareMedia method [IMAPI],IDiscFormat2RawCD interface, imapi.idiscformat2rawcd_preparemedia, imapi2/IDiscFormat2RawCD::PrepareMedia
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
 - IDiscFormat2RawCD::PrepareMedia
 - imapi2/IDiscFormat2RawCD::PrepareMedia
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
 - IDiscFormat2RawCD.PrepareMedia
---

# IDiscFormat2RawCD::PrepareMedia


## -description

Locks the current media for exclusive access.

## -parameters

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
<dt><b>E_IMAPI_DF2RAW_NO_RECORDER_SPECIFIED</b></dt>
</dl>
</td>
<td width="60%">
You cannot prepare the media until you choose a recorder to use.

Value: 0xC0AA060A

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_DF2RAW_MEDIA_IS_PREPARED</b></dt>
</dl>
</td>
<td width="60%">
The requested operation is not valid when media has been "prepared" but not released.

Value: 0xC0AA0603

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
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
Pointer is not valid.

Value: 0x80004003

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
Unspecified failure.

Value: 0x80004005

</td>
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
<dt><b>E_IMAPI_RECORDER_COMMAND_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The device failed to accept the command within the timeout period. This may be caused by the device having entered an inconsistent state, or the timeout value for the command may need to be increased.

Value: 0xC0AA020D

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_INVALID_RESPONSE_FROM_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
The device reported unexpected or invalid data for a command.

Value: 0xC0AA02FF

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_MEDIA_UPSIDE_DOWN</b></dt>
</dl>
</td>
<td width="60%">
The media is inserted upside down.

Value: 0xC0AA0204

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_MEDIA_BECOMING_READY</b></dt>
</dl>
</td>
<td width="60%">
The drive reported that it is in the process of becoming ready. Please try the request again later.

Value: 0xC0AA0205

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_MEDIA_NO_MEDIA</b></dt>
</dl>
</td>
<td width="60%">
There is no media in the device.

Value: 0xC0AA0202

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_MEDIA_FORMAT_IN_PROGRESS</b></dt>
</dl>
</td>
<td width="60%">
The media is currently being formatted. Please wait for the format to complete before attempting to use the media.

Value: 0xC0AA0206

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_MEDIA_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The drive reported that it is performing a long-running operation, such as finishing a write. The drive may be unusable for a long period of time.

Value: 0xC0AA0207

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_LOSS_OF_STREAMING</b></dt>
</dl>
</td>
<td width="60%">
The write failed because the drive did not receive data quickly enough to continue writing. Moving the source data to the local computer, reducing the write speed, or enabling a "buffer underrun free" setting may resolve this issue.

Value: 0xC0AA0300

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_MEDIA_INCOMPATIBLE</b></dt>
</dl>
</td>
<td width="60%">
The media is not compatible or of unknown physical format.

Value: 0xC0AA0203

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_DVD_STRUCTURE_NOT_PRESENT</b></dt>
</dl>
</td>
<td width="60%">
The DVD structure is not present. This may be caused by incompatible drive/medium used.

Value: 0xC0AA020E

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_NO_SUCH_MODE_PAGE</b></dt>
</dl>
</td>
<td width="60%">
The device reported that the requested mode page (and type) is not present.

Value: 0xC0AA0201

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_INVALID_MODE_PARAMETERS</b></dt>
</dl>
</td>
<td width="60%">
The drive reported that the combination of parameters provided in the mode page for a MODE SELECT command were not supported.

Value: 0xC0AA0208

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_MEDIA_WRITE_PROTECTED</b></dt>
</dl>
</td>
<td width="60%">
The drive reported that the media is write protected.

Value: 0xC0AA0209

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_MEDIA_SPEED_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The media's speed is incompatible with the device. This may be caused by using higher or lower speed media than the range of speeds supported by the device.

Value: 0xC0AA020F

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_INVALID_HANDLE)</b></dt>
</dl>
</td>
<td width="60%">
The specified handle is invalid.

Value: 6

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_DEV_NOT_EXIST)</b></dt>
</dl>
</td>
<td width="60%">
The specified network resource or device is no longer available.

Value: 55

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_LOCKED</b></dt>
</dl>
</td>
<td width="60%">
The device associated with this recorder during the last operation has been exclusively locked, causing this operation to failed.

Value: 0xC0AA0210

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_DF2RAW_MEDIA_IS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Only blank CD-R/RW media is supported.

Value: 0xC0AA0606

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_DF2RAW_MEDIA_IS_NOT_BLANK</b></dt>
</dl>
</td>
<td width="60%">
Only blank CD-R/RW media is supported.

Value: 0xC0AA0607

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_DF2RAW_CLIENT_NAME_IS_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The client name is not valid.

Value: 0xC0AA0604

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_IMAPI_ROTATIONADJUSTED</b></dt>
</dl>
</td>
<td width="60%">
The requested rotation type was not supported by the drive and the rotation type was adjusted.

Value: 0x00AA0005

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_IMAPI_SPEEDADJUSTED</b></dt>
</dl>
</td>
<td width="60%">
The requested write speed was not supported by the drive and the speed was adjusted.

Value: 0x00AA0004

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_IMAPI_BOTHADJUSTED</b></dt>
</dl>
</td>
<td width="60%">
The requested write speed and rotation type were not supported by the drive and they were both adjusted.

Value: 0x00AA0006

</td>
</tr>
</table>

## -remarks

Before calling this method, you must call the <a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-idiscformat2rawcd-put_clientname">IDiscFormat2RawCD::put_ClientName</a> method. 

Also, you must call the <b>IDiscFormat2RawCD::PrepareMedia</b> method before calling either the <a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-idiscformat2rawcd-writemedia">IDiscFormat2RawCD::WriteMedia</a> or <a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-idiscformat2rawcd-writemedia2">IDiscFormat2RawCD::WriteMedia2</a> method. 

After the write is complete or you cancel the write operation, you must call the <a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-idiscformat2rawcd-releasemedia">IDiscFormat2RawCD::ReleaseMedia</a> method to release the lock.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nn-imapi2-idiscformat2rawcd">IDiscFormat2RawCD</a>



<a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-idiscformat2rawcd-releasemedia">IDiscFormat2RawCD::ReleaseMedia</a>

