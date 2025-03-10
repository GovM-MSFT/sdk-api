---
UID: NF:tom.ITextDocument2.Update
title: ITextDocument2::Update (tom.h)
description: Updates the selection and caret.
helpviewer_keywords: ["ITextDocument2 interface [Windows Controls]","Update method","ITextDocument2.Update","ITextDocument2::Update","Update","Update method [Windows Controls]","Update method [Windows Controls]","ITextDocument2 interface","controls.itextdocument2_update","tom/ITextDocument2::Update"]
old-location: controls\itextdocument2_update.htm
tech.root: Controls
ms.assetid: 0ac5c944-227d-4ba3-afcf-ccb969902383
ms.date: 12/05/2018
ms.keywords: ITextDocument2 interface [Windows Controls],Update method, ITextDocument2.Update, ITextDocument2::Update, Update, Update method [Windows Controls], Update method [Windows Controls],ITextDocument2 interface, controls.itextdocument2_update, tom/ITextDocument2::Update
req.header: tom.h
req.include-header: 
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
req.lib: 
req.dll: Msftedit.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - ITextDocument2::Update
 - tom/ITextDocument2::Update
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Msftedit.dll
api_name:
 - ITextDocument2.Update
---

# ITextDocument2::Update


## -description

Updates the selection and caret.

## -parameters

### -param Value [in]

Type: <b>long</b>

Scroll flag. Use <b>tomTrue</b> to scroll the caret into view.

## -returns

Type: <b><a href="https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types">HRESULT</a></b>

If the method succeeds, it returns <b>NOERROR</b>. Otherwise, it returns an <b>HRESULT</b> error code.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/tom/nn-tom-itextdocument2">ITextDocument2</a>

