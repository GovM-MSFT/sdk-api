---
UID: NF:mi.MI_SubscriptionDeliveryOptions_GetExpirationTime
title: MI_SubscriptionDeliveryOptions_GetExpirationTime function (mi.h)
description: Gets the delivery expiration value (which can be expressed as a timestamp or an interval).
helpviewer_keywords: ["MI_SubscriptionDeliveryOptions_GetExpirationTime","MI_SubscriptionDeliveryOptions_GetExpirationTime function [Windows Management Infrastructure (MI)]","mi/MI_SubscriptionDeliveryOptions_GetExpirationTime","wmi_v2.mi_subscriptiondeliveryoptions_getexpirationtime"]
old-location: wmi_v2\mi_subscriptiondeliveryoptions_getexpirationtime.htm
tech.root: wmi_v2
ms.assetid: b76abb3b-e7f4-4b4b-866a-51a7d8b0066d
ms.date: 12/05/2018
ms.keywords: MI_SubscriptionDeliveryOptions_GetExpirationTime, MI_SubscriptionDeliveryOptions_GetExpirationTime function [Windows Management Infrastructure (MI)], mi/MI_SubscriptionDeliveryOptions_GetExpirationTime, wmi_v2.mi_subscriptiondeliveryoptions_getexpirationtime
req.header: mi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.redist: Windows Management Framework 3.0 on Windows Server 2008 R2 with SP1, Windows 7 with SP1, and Windows Server 2008 with SP2
ms.custom: 19H1
f1_keywords:
 - MI_SubscriptionDeliveryOptions_GetExpirationTime
 - mi/MI_SubscriptionDeliveryOptions_GetExpirationTime
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mi.h
api_name:
 - MI_SubscriptionDeliveryOptions_GetExpirationTime
---

# MI_SubscriptionDeliveryOptions_GetExpirationTime function


## -description

Gets the delivery expiration value (which can be expressed as a timestamp or an interval).

## -parameters

### -param self [in, out]

A <a href="https://docs.microsoft.com/windows/desktop/api/mi/ns-mi-mi_subscriptiondeliveryoptions">MI_SubscriptionDeliveryOptions</a> structure.

### -param value [out]

Returned delivery expiration value. This value is a <a href="https://docs.microsoft.com/windows/desktop/api/mi/ns-mi-mi_datetime">MI_Datetime</a> structure that can contain either a timestamp or an interval.

## -returns

A value of the <a href="https://docs.microsoft.com/windows/desktop/api/mi/ne-mi-mi_result">MI_Result</a> enumeration that specifies the function return code. This can be one of the following codes.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/mi/ns-mi-mi_datetime">MI_Datetime</a>



<a href="https://docs.microsoft.com/windows/desktop/api/mi/ns-mi-mi_subscriptiondeliveryoptions">MI_SubscriptionDeliveryOptions</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/mi/nf-mi-mi_subscriptiondeliveryoptions_setexpirationtime">MI_SubscriptionDeliveryOptions_SetExpirationTime</a>

