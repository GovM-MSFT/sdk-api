---
UID: NF:iphlpapi.GetTcpTable2
title: GetTcpTable2 function (iphlpapi.h)
description: Retrieves the IPv4 TCP connection table.
helpviewer_keywords: ["GetTcpTable2","GetTcpTable2 function [IP Helper]","iphlp.gettcptable2","iphlpapi/GetTcpTable2"]
old-location: iphlp\gettcptable2.htm
tech.root: IpHlp
ms.assetid: 942e8cb6-545f-45ab-919a-246e3b2d4c6a
ms.date: 12/05/2018
ms.keywords: GetTcpTable2, GetTcpTable2 function [IP Helper], iphlp.gettcptable2, iphlpapi/GetTcpTable2
req.header: iphlpapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista [desktop apps only]
req.target-min-winversvr: Windows Server 2008 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Iphlpapi.lib
req.dll: Iphlpapi.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - GetTcpTable2
 - iphlpapi/GetTcpTable2
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Iphlpapi.dll
api_name:
 - GetTcpTable2
---

# GetTcpTable2 function


## -description

The 
<b>GetTcpTable2</b> function retrieves the IPv4 TCP connection table.

## -parameters

### -param TcpTable [out]

A pointer to a buffer that receives the TCP connection table as a 
<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcptable2">MIB_TCPTABLE2</a> structure.

### -param SizePointer [in, out]

On input, specifies the size of the buffer pointed to by the <i>TcpTable</i> parameter. 




On output, if the buffer is not large enough to hold the returned connection table, the function sets this parameter equal to the required buffer size.

### -param Order [in]

A value that specifies whether the TCP connection table should be sorted. If this parameter is <b>TRUE</b>, the table is sorted in the order of: 




<ol>
<li>Local IP address</li>
<li>Local port</li>
<li>Remote IP address</li>
<li>Remote port</li>
</ol>

## -returns

If the function succeeds, the return value is NO_ERROR.

If the function fails, the return value is one of the following error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_INSUFFICIENT_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
The buffer pointed to by the <i>TcpTable</i> parameter is not large enough. The required size is returned in the <b>PULONG</b> variable pointed to by the <i>SizePointer</i> parameter.

This error is also returned if the <i>pTcpTable</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>SizePointer</i> parameter is <b>NULL</b>, or 
<a href="https://docs.microsoft.com/windows/desktop/api/iphlpapi/nf-iphlpapi-gettcptable2">GetTcpTable2</a> is unable to write to the memory pointed to by the <i>SizePointer</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not supported on the operating system in use on the local system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other</b></dt>
</dl>
</td>
<td width="60%">
Use 
<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-formatmessage">FormatMessage</a> to obtain the message string for the returned error.

</td>
</tr>
</table>

## -remarks

The <b>GetTcpTable2</b> function is defined on Windows Vista and later. 

The <b>GetTcpTable2</b> function is an enhanced version of the <a href="https://docs.microsoft.com/windows/desktop/api/iphlpapi/nf-iphlpapi-gettcptable">GetTcpTable</a> function that also retrieves information on the TCP offload state of the TCP connection.


#### Examples

The following example retrieves the TCP connection table for IPv4 and prints the state of each connection.


```cpp
#include <winsock2.h>
#include <ws2tcpip.h>
#include <iphlpapi.h>
#include <stdio.h>

// Need to link with Iphlpapi.lib and Ws2_32.lib
#pragma comment(lib, "iphlpapi.lib")
#pragma comment(lib, "ws2_32.lib")

#define MALLOC(x) HeapAlloc(GetProcessHeap(), 0, (x))
#define FREE(x) HeapFree(GetProcessHeap(), 0, (x))
/* Note: could also use malloc() and free() */

int main()
{

    // Declare and initialize variables
    PMIB_TCPTABLE2 pTcpTable;
    ULONG ulSize = 0;
    DWORD dwRetVal = 0;

    char szLocalAddr[128];
    char szRemoteAddr[128];

    struct in_addr IpAddr;

    int i;

    pTcpTable = (MIB_TCPTABLE2 *) MALLOC(sizeof (MIB_TCPTABLE2));
    if (pTcpTable == NULL) {
        printf("Error allocating memory\n");
        return 1;
    }

    ulSize = sizeof (MIB_TCPTABLE);
// Make an initial call to GetTcpTable2 to
// get the necessary size into the ulSize variable
    if ((dwRetVal = GetTcpTable2(pTcpTable, &ulSize, TRUE)) ==
        ERROR_INSUFFICIENT_BUFFER) {
        FREE(pTcpTable);
        pTcpTable = (MIB_TCPTABLE2 *) MALLOC(ulSize);
        if (pTcpTable == NULL) {
            printf("Error allocating memory\n");
            return 1;
        }
    }
// Make a second call to GetTcpTable2 to get
// the actual data we require
    if ((dwRetVal = GetTcpTable2(pTcpTable, &ulSize, TRUE)) == NO_ERROR) {
        printf("\tNumber of entries: %d\n", (int) pTcpTable->dwNumEntries);
        for (i = 0; i < (int) pTcpTable->dwNumEntries; i++) {
            printf("\n\tTCP[%d] State: %ld - ", i,
                   pTcpTable->table[i].dwState);
            switch (pTcpTable->table[i].dwState) {
            case MIB_TCP_STATE_CLOSED:
                printf("CLOSED\n");
                break;
            case MIB_TCP_STATE_LISTEN:
                printf("LISTEN\n");
                break;
            case MIB_TCP_STATE_SYN_SENT:
                printf("SYN-SENT\n");
                break;
            case MIB_TCP_STATE_SYN_RCVD:
                printf("SYN-RECEIVED\n");
                break;
            case MIB_TCP_STATE_ESTAB:
                printf("ESTABLISHED\n");
                break;
            case MIB_TCP_STATE_FIN_WAIT1:
                printf("FIN-WAIT-1\n");
                break;
            case MIB_TCP_STATE_FIN_WAIT2:
                printf("FIN-WAIT-2 \n");
                break;
            case MIB_TCP_STATE_CLOSE_WAIT:
                printf("CLOSE-WAIT\n");
                break;
            case MIB_TCP_STATE_CLOSING:
                printf("CLOSING\n");
                break;
            case MIB_TCP_STATE_LAST_ACK:
                printf("LAST-ACK\n");
                break;
            case MIB_TCP_STATE_TIME_WAIT:
                printf("TIME-WAIT\n");
                break;
            case MIB_TCP_STATE_DELETE_TCB:
                printf("DELETE-TCB\n");
                break;
            default:
                printf("UNKNOWN dwState value\n");
                break;
            }
            IpAddr.S_un.S_addr = (u_long) pTcpTable->table[i].dwLocalAddr;
            strcpy_s(szLocalAddr, sizeof (szLocalAddr), inet_ntoa(IpAddr));
            printf("\tTCP[%d] Local Addr: %s\n", i, szLocalAddr);
            printf("\tTCP[%d] Local Port: %d \n", i,
                   ntohs((u_short)pTcpTable->table[i].dwLocalPort));

            IpAddr.S_un.S_addr = (u_long) pTcpTable->table[i].dwRemoteAddr;
            strcpy_s(szRemoteAddr, sizeof (szRemoteAddr), inet_ntoa(IpAddr));
            printf("\tTCP[%d] Remote Addr: %s\n", i, szRemoteAddr);
            printf("\tTCP[%d] Remote Port: %d\n", i,
                   ntohs((u_short)pTcpTable->table[i].dwRemotePort));
                   
            printf("\tTCP[%d] Owning PID: %d\n", i, pTcpTable->table[i].dwOwningPid);
            printf("\tTCP[%d] Offload State: %ld - ", i,
                   pTcpTable->table[i].dwOffloadState);
            switch (pTcpTable->table[i].dwOffloadState) {
            case TcpConnectionOffloadStateInHost:
                printf("Owned by the network stack and not offloaded \n");
                break;
            case TcpConnectionOffloadStateOffloading:
                printf("In the process of being offloaded\n");
                break;
            case TcpConnectionOffloadStateOffloaded:
                printf("Offloaded to the network interface control\n");
                break;
            case TcpConnectionOffloadStateUploading:
                printf("In the process of being uploaded back to the network stack \n");
                break;
            default:
                printf("UNKNOWN Offload state value\n");
                break;
            }
                   
        }
    } else {
        printf("\tGetTcpTable2 failed with %d\n", dwRetVal);
        FREE(pTcpTable);
        return 1;
    }
    
    if (pTcpTable != NULL) {
        FREE(pTcpTable);
        pTcpTable = NULL;
    }

    return 0;    
}

```

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/iphlpapi/nf-iphlpapi-getextendedtcptable">GetExtendedTcpTable</a>



<a href="https://docs.microsoft.com/windows/desktop/api/iphlpapi/nf-iphlpapi-getownermodulefromtcpentry">GetOwnerModuleFromTcpEntry</a>



<a href="https://docs.microsoft.com/windows/desktop/api/iphlpapi/nf-iphlpapi-gettcp6table">GetTcp6Table</a>



<a href="https://docs.microsoft.com/windows/desktop/api/iphlpapi/nf-iphlpapi-gettcpstatistics">GetTcpStatistics</a>



<a href="https://docs.microsoft.com/windows/desktop/api/iphlpapi/nf-iphlpapi-gettcpstatisticsex">GetTcpStatisticsEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/iphlpapi/nf-iphlpapi-gettcptable">GetTcpTable</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcp6row2">MIB_TCP6ROW2</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcp6table">MIB_TCP6TABLE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcp6table2">MIB_TCP6TABLE2</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcp6table_owner_module">MIB_TCP6TABLE_OWNER_MODULE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcp6table_owner_pid">MIB_TCP6TABLE_OWNER_PID</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcprow_lh">MIB_TCPROW</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcprow2">MIB_TCPROW2</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcprow_owner_module">MIB_TCPROW_OWNER_MODULE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcprow_owner_pid">MIB_TCPROW_OWNER_PID</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcptable">MIB_TCPTABLE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcptable2">MIB_TCPTABLE2</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcptable_owner_module">MIB_TCPTABLE_OWNER_MODULE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/tcpmib/ns-tcpmib-mib_tcptable_owner_pid">MIB_TCPTABLE_OWNER_PID</a>



<a href="https://docs.microsoft.com/windows/desktop/api/iphlpapi/nf-iphlpapi-settcpentry">SetTcpEntry</a>

