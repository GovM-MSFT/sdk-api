---
UID: NF:winuser.GetPointerFrameInfo
title: GetPointerFrameInfo function (winuser.h)
description: Gets the entire frame of information for the specified pointers associated with the current message.
helpviewer_keywords: ["GetPointerFrameInfo","GetPointerFrameInfo function [Input Messages and Notifications]","inputmsg.getpointerframeinfo","winuser/GetPointerFrameInfo"]
old-location: inputmsg\getpointerframeinfo.htm
tech.root: InputMsg
ms.assetid: 6b7f450d-6ab1-4991-b2f9-a1db3f065711
ms.date: 12/05/2018
ms.keywords: GetPointerFrameInfo, GetPointerFrameInfo function [Input Messages and Notifications], inputmsg.getpointerframeinfo, winuser/GetPointerFrameInfo
req.header: winuser.h
req.include-header: Windows.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8 [desktop apps only]
req.target-min-winversvr: Windows Server 2012 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: User32.lib
req.dll: User32.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - GetPointerFrameInfo
 - winuser/GetPointerFrameInfo
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - User32.dll
 - API-MS-Win-NTUser-IE-WMPointer-l1-1-0.dll
 - ie_shims.dll
 - API-MS-Win-RTCore-NTUser-WMPointer-l1-1-0.dll
 - MinUser.dll
 - API-MS-Win-RTCore-NTUser-WMPointer-l1-1-1.dll
 - API-Ms-Win-RTCore-NTUser-WMPointer-L1-1-2.dll
 - API-MS-Win-RTCore-NTUser-WMPointer-L1-1-3.dll
api_name:
 - GetPointerFrameInfo
---

# GetPointerFrameInfo function


## -description

Gets the entire frame of information for the specified pointers associated with the current message.

## -parameters

### -param pointerId [in]

An identifier of the pointer for which to retrieve frame information.

### -param pointerCount [in, out]

A pointer to a variable that specifies the count of structures in the buffer to which pointerInfo points. If <b>GetPointerFrameInfo</b> succeeds, <i>pointerCount</i> is updated with the total count of pointers in the frame.

### -param pointerInfo [out]

Address of an array of <a href="https://docs.microsoft.com/windows/desktop/api/winuser/ns-winuser-pointer_info">POINTER_INFO</a> structures to receive the pointer information. This parameter can be <b>NULL</b> if <i>*pointerCount</i> is zero.

## -returns

If the function succeeds, the return value is non-zero.

If the function fails, the return value is zero. To get extended error information, call <a href="https://docs.microsoft.com/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror">GetLastError</a>.

## -remarks

Parallel-mode devices may report pointer input in frames, that is, they may report the state and position of all pointers from that device in a single input report to the system. Ideally, applications should view the entire frame as a single input unless the application-specific requirements dictate otherwise. 

<b>GetPointerFrameInfo</b> retrieves the entire pointer input frame associated with a pointer message. Use <a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getpointerinfo">GetPointerInfo</a> to retrieve information for a single pointer associated with a pointer message.

The  frame contains only pointers that are currently owned by the same window as the specified pointer.

The information returned by <b>GetPointerFrameInfo</b> is associated with the most recent pointer message retrieved by the calling thread. When the next message is retrieved by the calling thread, the information associated with the previous message may no longer be available.



If the application does not process pointer input messages as fast as they are generated, some messages may be coalesced into a <a href="https://docs.microsoft.com/previous-versions/windows/desktop/inputmsg/wm-pointerupdate">WM_POINTERUPDATE</a> message. Use <a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getpointerframeinfohistory">GetPointerFrameInfoHistory</a> to retrieve the message history from the most recent <b>WM_POINTERUPDATE</b> message. 

Having retrieved the entire frame of information, the application can then call the <a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-skippointerframemessages">SkipPointerFrameMessages</a> function to skip remaining pointer messages associated with this frame that are pending retrieval. This saves the application the overhead of retrieving and processing the remaining messages one by one. However, the <b>SkipPointerFrameMessages</b> function should be used with care and only when the caller can be sure that no other entity on the caller’s thread is expecting to see the remaining pointer messages one by one as they are retrieved.

Note that the information retrieved is associated with the pointer frame most recently retrieved by the calling thread. Once the calling thread retrieves its next message, the information associated with the previous pointer frame may no longer be available.

If the pointer frame contains no additional pointers besides the specified pointer, this function succeeds and returns only the information for the specified pointer.

If the information associated with the pointer frame is no longer available, this function fails with the last error set to <b>ERROR_NO_DATA</b>.

If the calling thread does not own the window (where the input was originally delivered or where the message was forwarded) to which the pointer message has been delivered, this function fails with the last error set to <b>ERROR_ACCESS_DENIED</b>. 

For apps that have  both client and non-client areas, the input frame can include both client and non-client data. To differentiate between client and non-client data, you must perform hit testing on the target window.

We recommend the following if you want to filter data from the input frame:

<ul>
<li>For each update that does not include a pointer contact (a <a href="https://docs.microsoft.com/previous-versions/windows/desktop/inputmsg/pointer-flags-contants">POINTER_FLAG_UPDATE</a> without <b>POINTER_FLAG_INCONTACT</b>), hit test to determine if the input is client or non-client.</li>
<li>For each new contact (<a href="https://docs.microsoft.com/previous-versions/windows/desktop/inputmsg/pointer-flags-contants">POINTER_FLAG_DOWN</a>), hit test to determine if the input is client or non-client and track this info.</li>
<li>For each update that includes a pointer contact (a <a href="https://docs.microsoft.com/previous-versions/windows/desktop/inputmsg/pointer-flags-contants">POINTER_FLAG_UPDATE</a> with <b>POINTER_FLAG_INCONTACT</b>), use the tracking info to determine whether the input is client or non-client.</li>
<li>For each <a href="https://docs.microsoft.com/previous-versions/windows/desktop/inputmsg/pointer-flags-contants">POINTER_FLAG_UP</a>, use the tracking info to determine whether the input is client or non-client and then clear this pointer from the tracking data.</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/desktop/inputmsg/functions">Functions</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getpointerframeinfohistory">GetPointerFrameInfoHistory</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getpointerinfo">GetPointerInfo</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-getpointerinfohistory">GetPointerInfoHistory</a>

