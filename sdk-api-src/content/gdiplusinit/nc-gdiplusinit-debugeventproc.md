---
UID: NC:gdiplusinit.DebugEventProc
title: DebugEventProc
ms.date: 05/07/2020
ms.topic: language-reference
targetos: Windows
description: \**DebugEventProc** is the signature of a callback function that you implement in your application, and pass to the constructor of [**GdiplusStartupInput**](/windows/win32/api/gdiplusinit/nf-gdiplusinit-gdiplusstartupinput-gdiplusstartupinput).
tech.root: gdiplus
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: gdiplusinit.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - gdiplusinit.h
api_name:
 - DebugEventProc
f1_keywords:
 - DebugEventProc
 - gdiplusinit/DebugEventProc
dev_langs:
 - c++
---

## -description

**DebugEventProc** is the signature of a callback function that you implement in your application, and pass to the constructor of [**GdiplusStartupInput**](/windows/win32/api/gdiplusinit/nf-gdiplusinit-gdiplusstartupinput-gdiplusstartupinput).

## -parameters

### -param level

A [**DebugEventLevel**](/windows/win32/api/gdiplusinit/ne-gdiplusinit-debugeventlevel) object representing the level of the debug event.

### -param message

A pointer to a narrow string containing the debug event message.

## -remarks

## -see-also

