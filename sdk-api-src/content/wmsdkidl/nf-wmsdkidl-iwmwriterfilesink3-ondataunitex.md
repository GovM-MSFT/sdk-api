---
UID: NF:wmsdkidl.IWMWriterFileSink3.OnDataUnitEx
title: IWMWriterFileSink3::OnDataUnitEx (wmsdkidl.h)
description: The OnDataUnitEx method is called when the writer has finished sending a data unit.
helpviewer_keywords: ["IWMWriterFileSink3 interface [windows Media Format]","OnDataUnitEx method","IWMWriterFileSink3.OnDataUnitEx","IWMWriterFileSink3::OnDataUnitEx","IWMWriterFileSink3OnDataUnitEx","OnDataUnitEx","OnDataUnitEx method [windows Media Format]","OnDataUnitEx method [windows Media Format]","IWMWriterFileSink3 interface","wmformat.iwmwriterfilesink3_ondataunitex","wmsdkidl/IWMWriterFileSink3::OnDataUnitEx"]
old-location: wmformat\iwmwriterfilesink3_ondataunitex.htm
tech.root: wmformat
ms.assetid: 1dbcb27b-7588-4475-99fe-3e547d1659d3
ms.date: 12/05/2018
ms.keywords: IWMWriterFileSink3 interface [windows Media Format],OnDataUnitEx method, IWMWriterFileSink3.OnDataUnitEx, IWMWriterFileSink3::OnDataUnitEx, IWMWriterFileSink3OnDataUnitEx, OnDataUnitEx, OnDataUnitEx method [windows Media Format], OnDataUnitEx method [windows Media Format],IWMWriterFileSink3 interface, wmformat.iwmwriterfilesink3_ondataunitex, wmsdkidl/IWMWriterFileSink3::OnDataUnitEx
req.header: wmsdkidl.h
req.include-header: Wmsdk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 Professional [desktop apps only],Windows Media Format 9 Series SDK, or later versions of the SDK
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
req.lib: Wmvcore.lib; WMStubDRM.lib (if you use DRM)
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - IWMWriterFileSink3::OnDataUnitEx
 - wmsdkidl/IWMWriterFileSink3::OnDataUnitEx
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wmvcore.lib
 - Wmvcore.dll
 - WMStubDRM.lib
 - WMStubDRM.dll
api_name:
 - IWMWriterFileSink3.OnDataUnitEx
---

# IWMWriterFileSink3::OnDataUnitEx


## -description

The <b>OnDataUnitEx</b> method is called when the writer has finished sending a data unit.



<b>OnDataUnitEx</b> is an enhanced version of <a href="https://docs.microsoft.com/windows/desktop/api/wmsdkidl/nf-wmsdkidl-iwmwritersink-ondataunit">IWMWriterSink::OnDataUnit</a>. The difference between these two methods is that <b>OnDataUnitEx</b> delivers very granular data unit information. You can examine individual payload headers, payload data fragments, and the packet header.

## -parameters

### -param pFileSinkDataUnit [in]

Pointer to a <a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/wmsdkidl/ns-wmsdkidl-wmt_filesink_data_unit">WMT_FILESINK_DATA_UNIT</a> structure containing the data unit information.

## -returns

This method always returns S_OK.

## -remarks

Applications do not call this method. If you are implementing the <b>IWMWriterFileSink3</b> interface on a custom sink, you have the option of implementing this method. If you do so, your implementation of <a href="https://docs.microsoft.com/windows/desktop/api/wmsdkidl/nf-wmsdkidl-iwmwriterfilesink3-getmode">GetMode</a> should return WMT_FM_FILESINK_DATA_UNITS.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/wmsdkidl/nn-wmsdkidl-iwmwriterfilesink3">IWMWriterFileSink3 Interface</a>

