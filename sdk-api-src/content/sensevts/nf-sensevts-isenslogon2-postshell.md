---
UID: NF:sensevts.ISensLogon2.PostShell
title: ISensLogon2::PostShell (sensevts.h)
description: Use the PostShell method when a user has logged on and Windows Explorer is running. This method is different from the Logon method because Logon is called after logon when the Shell may not yet be running.
helpviewer_keywords: ["ISensLogon2 interface [SENS]","PostShell method","ISensLogon2.PostShell","ISensLogon2::PostShell","PostShell","PostShell method [SENS]","PostShell method [SENS]","ISensLogon2 interface","_zaw_isenslogon2_sessionpostshell","sens.isenslogon2_sessionpostshell","sensevts/ISensLogon2::PostShell","syncmgr.isenslogon2_sessionpostshell"]
old-location: sens\isenslogon2_sessionpostshell.htm
tech.root: Sens
ms.assetid: fa187b3c-fc78-410f-9339-9b4c94c43f95
ms.date: 12/05/2018
ms.keywords: ISensLogon2 interface [SENS],PostShell method, ISensLogon2.PostShell, ISensLogon2::PostShell, PostShell, PostShell method [SENS], PostShell method [SENS],ISensLogon2 interface, _zaw_isenslogon2_sessionpostshell, sens.isenslogon2_sessionpostshell, sensevts/ISensLogon2::PostShell, syncmgr.isenslogon2_sessionpostshell
req.header: sensevts.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP [desktop apps only]
req.target-min-winversvr: Windows Server 2003 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: Sensevts.tlb
req.lib: 
req.dll: Sens.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - ISensLogon2::PostShell
 - sensevts/ISensLogon2::PostShell
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Sens.dll
api_name:
 - ISensLogon2.PostShell
 - ISensLogon2.PostShell
---

# ISensLogon2::PostShell


## -description

Use the 
<b>PostShell</b> method when a user has logged on and Windows Explorer is running. This method is different from the 
<a href="https://docs.microsoft.com/windows/desktop/api/sensevts/nf-sensevts-isenslogon2-logon">Logon</a> method because 
<b>Logon</b> is called after logon when the Shell may not yet be running.

## -parameters

### -param bstrUserName [in]

Name of the current user.

### -param dwSessionId [in]

The session identifier of the session.

## -returns

This method can return one of these values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
Method returned successfully.

</td>
</tr>
</table>

## -remarks

SENS calls this method to notify your application that a user has logged on and the Windows Explorer (Shell) is running.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/Sens/about-system-event-notification-service">About System Event Notification Service</a>



<a href="https://docs.microsoft.com/windows/desktop/api/sensevts/nn-sensevts-isenslogon2">ISensLogon2</a>



<a href="https://docs.microsoft.com/windows/desktop/api/sensevts/nf-sensevts-isenslogon-logoff">ISensLogon::Logoff</a>



<a href="https://docs.microsoft.com/windows/desktop/TermServ/terminal-services-portal">Terminal Services</a>

