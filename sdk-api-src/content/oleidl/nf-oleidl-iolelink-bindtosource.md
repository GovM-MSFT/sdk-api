---
UID: NF:oleidl.IOleLink.BindToSource
title: IOleLink::BindToSource (oleidl.h)
description: Activates the connection to the link source by binding the moniker stored within the linked object.
helpviewer_keywords: ["BindToSource","BindToSource method [COM]","BindToSource method [COM]","IOleLink interface","IOleLink interface [COM]","BindToSource method","IOleLink.BindToSource","IOleLink::BindToSource","_ole_iolelink_bindtosource","com.iolelink_bindtosource","oleidl/IOleLink::BindToSource"]
old-location: com\iolelink_bindtosource.htm
tech.root: com
ms.assetid: 1fadd27d-cb2c-47fc-891a-16f82bdac0f6
ms.date: 12/05/2018
ms.keywords: BindToSource, BindToSource method [COM], BindToSource method [COM],IOleLink interface, IOleLink interface [COM],BindToSource method, IOleLink.BindToSource, IOleLink::BindToSource, _ole_iolelink_bindtosource, com.iolelink_bindtosource, oleidl/IOleLink::BindToSource
req.header: oleidl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 Professional [desktop apps only]
req.target-min-winversvr: Windows 2000 Server [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: OleIdl.Idl
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
 - IOleLink::BindToSource
 - oleidl/IOleLink::BindToSource
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - OleIdl.h
api_name:
 - IOleLink.BindToSource
---

# IOleLink::BindToSource


## -description

Activates the connection to the link source by binding the moniker stored within the linked object.

## -parameters

### -param bindflags [in]

Specifies how to proceed if the link source has a different CLSID from the last time it was bound. If this parameter is zero and the CLSIDs are different, the method fails and returns OLE_E_CLASSDIFF. If the OLELINKBIND_EVENIFCLASSDIFF value from the <a href="https://docs.microsoft.com/windows/desktop/api/oleidl/ne-oleidl-olelinkbind">OLELINKBIND</a> enumeration is specified and the CLSIDs are different, the method binds successfully and updates the CLSID stored in the linked object.

### -param pbc [in]

A pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-ibindctx">IBindCtx</a> interface on the bind context to be used in this binding operation. This parameter can be <b>NULL</b>. The bind context caches objects bound during the binding process, contains parameters that apply to all operations using the bind context, and provides the means by which the binding implementation should retrieve information about its environment. For more information, see <b>IBindCtx</b>.

## -returns

This method returns S_OK on success. Other possible return values include the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>OLE_E_CLASSDIFF</b></dt>
</dl>
</td>
<td width="60%">
The link source was not bound because its CLSID has changed. This error is returned only if the OLELINKBIND_EVENIFCLASSDIFF flag is not specified in the <i>bindflags</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>MK_E_NOOBJECT</b></dt>
</dl>
</td>
<td width="60%">
The link source could not be found or (if the link source's moniker is a composite) some intermediate object identified in the composite could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNSPEC</b></dt>
</dl>
</td>
<td width="60%">
The link's moniker is <b>NULL</b>.

</td>
</tr>
</table>
 

Binding the moniker might require calling the <a href="https://docs.microsoft.com/windows/desktop/api/objbase/nf-objbase-createbindctx">CreateBindCtx</a> function; therefore, this method may return errors generated by <b>CreateBindCtx</b>.

## -remarks

<h3><a id="Notes_to_Callers"></a><a id="notes_to_callers"></a><a id="NOTES_TO_CALLERS"></a>Notes to Callers</h3>
Typically, your container application does not need to call the <b>IOleLink::BindToSource</b> method directly. When it's necessary to activate the connection to the link source, your container typically calls <a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb">IOleObject::DoVerb</a>, <a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-ioleobject-update">IOleObject::Update</a>, or <a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolelink-update">IOleLink::Update</a>. The linked object's implementation of these methods calls <b>IOleLink::BindToSource</b>. Your container can also call the <a href="https://docs.microsoft.com/windows/desktop/api/ole2/nf-ole2-olerun">OleRun</a> function, which calls <b>IOleLink::BindToSource</b> when called on a linked object.

In each of the examples listed previously, in which <b>IOleLink::BindToSource</b> is called indirectly, the bindflags parameter is set to zero. Consequently, these calls can fail with the OLE_E_CLASSDIFF error if the class of the link source is different from what it was the last time the linked object was bound. This could happen, for example, if the original link source was an embedded Lotus spreadsheet that an end user had subsequently converted (using the Change Type dialog box) to an Excel spreadsheet.

If you want your container to bind even though the link source now has a different CLSID, you can call <b>IOleLink::BindToSource</b> directly and specify OLELINKBIND_EVENIFCLASSDIFF for the bindflags parameter. This call binds to the link source and updates the link object's CLSID. Alternatively, your container can delete the existing link and use the <a href="https://docs.microsoft.com/windows/desktop/api/ole2/nf-ole2-olecreatelink">OleCreateLink</a> function to create a new linked object.

<h3><a id="Notes_to_Implementers"></a><a id="notes_to_implementers"></a><a id="NOTES_TO_IMPLEMENTERS"></a>Notes to Implementers</h3>
The linked object caches the interface pointer to the link source acquired during binding.

The linked object's <b>IOleLink::BindToSource</b> implementation first tries to bind using a moniker consisting of the compound document's moniker composed with the link source's relative moniker. If successful, it updates the link's absolute moniker. Otherwise, it tries to bind using the absolute moniker, updating the relative moniker if successful.

If <b>IOleLink::BindToSource</b> binds to the link source, it calls the compound document's <a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolecontainer-lockcontainer">IOleContainer::LockContainer</a> implementation to keep the containing compound document alive while the link source is running. <b>IOleLink::BindToSource</b> also calls the <a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-ioleobject-advise">IOleObject::Advise</a> and <a href="https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-idataobject-dadvise">IDataObject::DAdvise</a> implementations of the link source to set up advisory connections. The <a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolelink-unbindsource">IOleLink::UnbindSource</a> implementation unlocks the container and deletes the advisory connections.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-idataobject-dadvise">IDataObject::DAdvise</a>



<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolecontainer-lockcontainer">IOleContainer::LockContainer</a>



<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nn-oleidl-iolelink">IOleLink</a>



<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolelink-unbindsource">IOleLink::UnbindSource</a>



<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-iolelink-update">IOleLink::Update</a>



<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-ioleobject-advise">IOleObject::Advise</a>



<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb">IOleObject::DoVerb</a>



<a href="https://docs.microsoft.com/windows/desktop/api/oleidl/nf-oleidl-ioleobject-update">IOleObject::Update</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ole2/nf-ole2-olerun">OleRun</a>

