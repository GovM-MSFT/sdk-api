---
UID: NF:winbase.WriteEncryptedFileRaw
title: WriteEncryptedFileRaw function (winbase.h)
description: Restores (import) encrypted files.
helpviewer_keywords: ["WriteEncryptedFileRaw","WriteEncryptedFileRaw function [Files]","base.writeencryptedfileraw","fs.writeencryptedfileraw","winbase/WriteEncryptedFileRaw"]
old-location: fs\writeencryptedfileraw.htm
tech.root: fs
ms.assetid: f44e291e-dbc6-4a44-92ba-92a81e043764
ms.date: 12/05/2018
ms.keywords: WriteEncryptedFileRaw, WriteEncryptedFileRaw function [Files], base.writeencryptedfileraw, fs.writeencryptedfileraw, winbase/WriteEncryptedFileRaw
req.header: winbase.h
req.include-header: Windows.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional [desktop apps only]
req.target-min-winversvr: Windows Server 2003 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Advapi32.lib
req.dll: Advapi32.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - WriteEncryptedFileRaw
 - winbase/WriteEncryptedFileRaw
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Advapi32.dll
 - Ext-MS-Win-AdvAPI32-EncryptedFile-l1-1-0.dll
 - Ext-MS-Win-AdvAPI32-EncryptedFile-L1-1-1.dll
api_name:
 - WriteEncryptedFileRaw
---

# WriteEncryptedFileRaw function


## -description

Restores (import) encrypted files. This is one of a group of Encrypted File System (EFS) 
    functions that is intended  to implement backup and restore functionality, while maintaining files in their 
    encrypted state.

## -parameters

### -param pfImportCallback [in]

A pointer to the import callback function. The system calls the callback function multiple times, each time 
      passing a buffer that will be filled by the callback function with a portion of backed-up file's data. When the 
      callback function signals that the entire file has been processed, it tells the system that the restore 
      operation is finished. For more information, see 
      <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nc-winbase-pfe_import_func">ImportCallback</a>.

### -param pvCallbackContext [in, optional]

A pointer to an application-defined and allocated context block. The system passes this pointer to the 
      callback function as a parameter so that the callback function can have access to application-specific data. 
      This can be a structure and can contain any data the application needs, such as the handle to the file that will 
      contain the backup copy of the encrypted file.

### -param pvContext [in]

A pointer to a system-defined context block. The context block is returned by the 
      <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-openencryptedfilerawa">OpenEncryptedFileRaw</a> function. Do not modify 
      it.

## -returns

If the function succeeds, the return value is <b>ERROR_SUCCESS</b>.

If the function fails, it returns a nonzero error code defined in WinError.h. You can use 
       <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-formatmessage">FormatMessage</a> with the 
       <b>FORMAT_MESSAGE_FROM_SYSTEM</b> flag to get a generic text description of the error.

## -remarks

The file being restored is not decrypted;  it is restored in its encrypted state.

To back up an encrypted file, call 
     <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-openencryptedfilerawa">OpenEncryptedFileRaw</a> to open the file. Then call 
     <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-readencryptedfileraw">ReadEncryptedFileRaw</a>, passing it the address of an 
     application-defined export callback function. The system calls this callback function multiple times until the 
     entire file's contents have been read and backed up.  When the backup is complete, call 
     <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-closeencryptedfileraw">CloseEncryptedFileRaw</a> to free resources and close 
     the file. See <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nc-winbase-pfe_export_func">ExportCallback</a> for details about how to 
     declare the export callback function.

To restore an encrypted file, call 
     <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-openencryptedfilerawa">OpenEncryptedFileRaw</a>, specifying 
     <b>CREATE_FOR_IMPORT</b> in the <i>ulFlags</i> parameter. Then call 
     <b>WriteEncryptedFileRaw</b>, passing it the address of 
     an application-defined import callback function. The system calls this callback function multiple times until the 
     entire file's contents have been read and restored. When the restore is complete, call 
     <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-closeencryptedfileraw">CloseEncryptedFileRaw</a> to free resources and close 
     the file. See <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nc-winbase-pfe_import_func">ImportCallback</a> for details about how to 
     declare the export callback function.

If the file is a sparse file that was backed up from a volume with a smaller sparse allocation unit size than 
    the volume it is being restored to, the sparse blocks in the middle of the file may not properly align with the 
    larger blocks and the function call would fail and set an <b>ERROR_INVALID_PARAMETER</b> last 
    error code. The sparse allocation unit size is either 16 clusters or 64 KB, whichever is smaller.

This function is intended for restoring only encrypted files; see 
    <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-backupwrite">BackupWrite</a> for restoring unencrypted files.

In Windows 8, Windows Server 2012, and later, this function is supported by the following technologies.

<table>
<tr>
<th>Technology</th>
<th>Supported</th>
</tr>
<tr>
<td>
Server Message Block (SMB) 3.0 protocol

</td>
<td>
Yes

</td>
</tr>
<tr>
<td>
SMB 3.0 Transparent Failover (TFO)

</td>
<td>
No

</td>
</tr>
<tr>
<td>
SMB 3.0 with Scale-out File Shares (SO)

</td>
<td>
No

</td>
</tr>
<tr>
<td>
Cluster Shared Volume File System (CsvFS)

</td>
<td>
No

</td>
</tr>
<tr>
<td>
Resilient File System (ReFS)

</td>
<td>
No

</td>
</tr>
</table>
 

SMB 3.0 does not support EFS on shares with continuous availability capability.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-backupwrite">BackupWrite</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-closeencryptedfileraw">CloseEncryptedFileRaw</a>



<a href="https://docs.microsoft.com/windows/desktop/FileIO/file-encryption">File Encryption</a>



<a href="https://docs.microsoft.com/windows/desktop/FileIO/file-management-functions">File Management Functions</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nc-winbase-pfe_import_func">ImportCallback</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-openencryptedfilerawa">OpenEncryptedFileRaw</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-readencryptedfileraw">ReadEncryptedFileRaw</a>

