---
UID: NC:commdlg.LPFRHOOKPROC
title: LPFRHOOKPROC (commdlg.h)
description: Receives messages or notifications intended for the default dialog box procedure of the Find or Replace dialog box.
helpviewer_keywords: ["FRHookProc","LPFRHOOKPROC","LPFRHOOKPROC callback","LPFRHOOKPROC callback function [Dialog Boxes]","_win32_FRHookProc","_win32_frhookproc_cpp","commdlg/LPFRHOOKPROC","dlgbox.frhookproc","winui._win32_frhookproc"]
old-location: dlgbox\frhookproc.htm
tech.root: dlgbox
ms.assetid: VS|winui|~\winui\windowsuserinterface\userinput\commondialogboxlibrary\commondialogboxreference\commondialogboxfunctions\frhookproc.htm
ms.date: 12/05/2018
ms.keywords: FRHookProc, LPFRHOOKPROC, LPFRHOOKPROC callback, LPFRHOOKPROC callback function [Dialog Boxes], _win32_FRHookProc, _win32_frhookproc_cpp, commdlg/LPFRHOOKPROC, dlgbox.frhookproc, winui._win32_frhookproc
req.header: commdlg.h
req.include-header: Windows.h
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 Professional [desktop apps only]
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - LPFRHOOKPROC
 - commdlg/LPFRHOOKPROC
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Commdlg.h
api_name:
 - LPFRHOOKPROC
---

## -description

Receives messages or notifications intended for the default dialog box procedure of the <b>Find</b> or <b>Replace</b> dialog box. The <i>FRHookProc</i> hook procedure is an application-defined or library-defined callback function that is used with the <a href="https://docs.microsoft.com/windows/desktop/api/commdlg/nf-commdlg-findtexta">FindText</a> or <a href="https://docs.microsoft.com/windows/desktop/api/commdlg/nf-commdlg-replacetexta">ReplaceText</a> function.

The <b>LPFRHOOKPROC</b> type defines a pointer to this callback function. <i>FRHookProc</i> is a placeholder for the application-defined function name.

## -parameters

### -param Arg1

A handle to the <b>Find</b> or <b>Replace</b> dialog box for which the message is intended.

### -param Arg2

The identifier of the message being received.

### -param Arg3

Additional information about the message. The exact meaning depends on the value of the <i>Arg2</i> parameter.

### -param Arg4

Additional information about the message. The exact meaning depends on the value of the <i>Arg2</i> parameter. 

If the <i>Arg2</i> parameter indicates the <a href="https://docs.microsoft.com/windows/desktop/dlgbox/wm-initdialog">WM_INITDIALOG</a> message, <i>Arg4</i> is a pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/commdlg/ns-commdlg-findreplacea">FINDREPLACE</a> structure containing the values specified when the dialog box was created.

## -returns

If the hook procedure returns zero, the default dialog box procedure processes the message.

If the hook procedure returns a nonzero value, the default dialog box procedure ignores the message.

## -remarks

When you use the <a href="https://docs.microsoft.com/windows/desktop/api/commdlg/nf-commdlg-findtexta">FindText</a> or <a href="https://docs.microsoft.com/windows/desktop/api/commdlg/nf-commdlg-replacetexta">ReplaceText</a> functions to create a <b>Find</b> or <b>Replace</b> dialog box, you can provide an <i>FRHookProc</i> hook procedure to process messages or notifications intended for the dialog box procedure. To enable the hook procedure, use the <a href="https://docs.microsoft.com/windows/desktop/api/commdlg/ns-commdlg-findreplacea">FINDREPLACE</a> structure that you passed to the dialog creation function. Specify the address of the hook procedure in the <b>lpfnHook</b> member and specify the <b>FR_ENABLEHOOK</b> flag in the <b>Flags</b> member.

The default dialog box procedure processes the <a href="https://docs.microsoft.com/windows/desktop/dlgbox/wm-initdialog">WM_INITDIALOG</a> message before passing it to the hook procedure. For all other messages, the hook procedure receives the message first. Then, the return value of the hook procedure determines whether the default dialog procedure processes the message or ignores it.

If the hook procedure processes the <a href="https://docs.microsoft.com/windows/desktop/dlgbox/wm-ctlcolordlg">WM_CTLCOLORDLG</a> message, it must return a valid brush handle for painting the background of the dialog box. In general, if the hook procedure processes any <b>WM_CTLCOLOR*</b> message, it must return a valid brush handle for painting the background of the specified control.

Do not call the <a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-enddialog">EndDialog</a> function from the hook procedure. Instead, the hook procedure can call the <a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-postmessagea">PostMessage</a> function to post a <a href="https://docs.microsoft.com/windows/desktop/menurc/wm-command">WM_COMMAND</a> message with the <b>IDABORT</b> value to the dialog box procedure. Posting <b>IDABORT</b> closes the dialog box and causes the dialog box function to return <b>FALSE</b>. If you need to know why the hook procedure closed the dialog box, you must provide your own communication mechanism between the hook procedure and your application.

You can subclass the standard controls of a common dialog box. However, the dialog box procedure may also subclass the controls. Because of this, you should subclass controls when your hook procedure processes the <a href="https://docs.microsoft.com/windows/desktop/dlgbox/wm-initdialog">WM_INITDIALOG</a> message. This ensures that your subclass procedure receives the control-specific messages before the subclass procedure set by the dialog box procedure.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/dlgbox/common-dialog-box-library">Common Dialog Box Library</a>



<b>Conceptual</b>



<a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-enddialog">EndDialog</a>



<a href="https://docs.microsoft.com/windows/desktop/api/commdlg/ns-commdlg-findreplacea">FINDREPLACE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/commdlg/nf-commdlg-findtexta">FindText</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-postmessagea">PostMessage</a>



<b>Reference</b>



<a href="https://docs.microsoft.com/windows/desktop/api/commdlg/nf-commdlg-replacetexta">ReplaceText</a>



<a href="https://docs.microsoft.com/windows/desktop/dlgbox/wm-ctlcolordlg">WM_CTLCOLORDLG</a>



<a href="https://docs.microsoft.com/windows/desktop/dlgbox/wm-initdialog">WM_INITDIALOG</a>

