---
UID: NF:imapi2.IDiscRecorder2Ex.GetFeaturePage
title: IDiscRecorder2Ex::GetFeaturePage (imapi2.h)
description: Retrieves the specified feature page from the device.
helpviewer_keywords: ["GetFeaturePage","GetFeaturePage method [IMAPI]","GetFeaturePage method [IMAPI]","IDiscRecorder2Ex interface","IDiscRecorder2Ex interface [IMAPI]","GetFeaturePage method","IDiscRecorder2Ex.GetFeaturePage","IDiscRecorder2Ex::GetFeaturePage","imapi.idiscrecorder2ex_getfeaturepage","imapi2/IDiscRecorder2Ex::GetFeaturePage"]
old-location: imapi\idiscrecorder2ex_getfeaturepage.htm
tech.root: imapi
ms.assetid: a3cf0d33-25ea-4764-8fdb-5ef47c7b1e50
ms.date: 12/05/2018
ms.keywords: GetFeaturePage, GetFeaturePage method [IMAPI], GetFeaturePage method [IMAPI],IDiscRecorder2Ex interface, IDiscRecorder2Ex interface [IMAPI],GetFeaturePage method, IDiscRecorder2Ex.GetFeaturePage, IDiscRecorder2Ex::GetFeaturePage, imapi.idiscrecorder2ex_getfeaturepage, imapi2/IDiscRecorder2Ex::GetFeaturePage
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
 - IDiscRecorder2Ex::GetFeaturePage
 - imapi2/IDiscRecorder2Ex::GetFeaturePage
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
 - IDiscRecorder2Ex.GetFeaturePage
---

# IDiscRecorder2Ex::GetFeaturePage


## -description

Retrieves the specified feature page from the device.

## -parameters

### -param requestedFeature [in]

Feature page to retrieve. For possible values, see the <a href="https://docs.microsoft.com/windows/desktop/api/imapi2/ne-imapi2-imapi_feature_page_type">IMAPI_FEATURE_PAGE_TYPE</a> enumeration type.

### -param currentFeatureOnly [in]

Set to True to retrieve the feature page only when it is the current feature page. Otherwise, False to retrieve the feature page regardless of it being the current feature page.

### -param featureData [out]

Data buffer that contains the feature page. For details of the contents of the data buffer, see the GET CONFIGURATION command in the latest revision of the MMC specification at ftp://ftp.t10.org/t10/drafts/mmc5.

This method removes header information and other non-feature data before filling and sending this buffer.

When done, call the <b>CoTaskMemFree</b> function to free the memory.

### -param byteSize [out]

Size, in bytes, of the <i>featureData</i> data buffer.

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
<dt><b>E_IMAPI_RECORDER_GET_CONFIGURATION_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The drive does not support the GET CONFIGURATION command.

Value: 0xC0AA020C

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_IMAPI_RECORDER_NO_SUCH_FEATURE</b></dt>
</dl>
</td>
<td width="60%">
The feature page requested is not supported by the device.

Value: 0xC0AA020A

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
<dt><b>E_IMAPI_RECORDER_FEATURE_IS_NOT_CURRENT</b></dt>
</dl>
</td>
<td width="60%">
The feature page requested is supported, but is not marked as current.

Value: 0xC0AA020B

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
</table>

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nn-imapi2-idiscrecorder2ex">IDiscRecorder2Ex</a>



<a href="https://docs.microsoft.com/windows/desktop/api/imapi2/nf-imapi2-idiscrecorder2ex-getsupportedfeaturepages">IDiscRecorder2Ex::GetSupportedFeaturePages</a>



<a href="https://docs.microsoft.com/windows/desktop/api/imapi2/ne-imapi2-imapi_feature_page_type">IMAPI_FEATURE_PAGE_TYPE</a>

