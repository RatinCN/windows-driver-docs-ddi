---
UID: NF:ntddk.IoPropagateActivityIdToThread
title: IoPropagateActivityIdToThread function (ntddk.h)
description: The IoPropagateActivityIdToThread routine associates the activity ID from an IRP with the current thread.
old-location: kernel\iopropagateactivityidtothread.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoPropagateActivityIdToThread function"]
ms.keywords: IoPropagateActivityIdToThread, IoPropagateActivityIdToThread routine [Kernel-Mode Driver Architecture], kernel.iopropagateactivityidtothread, ntddk/IoPropagateActivityIdToThread
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - IoPropagateActivityIdToThread
 - ntddk/IoPropagateActivityIdToThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoPropagateActivityIdToThread
---

# IoPropagateActivityIdToThread function


## -description

The <b>IoPropagateActivityIdToThread</b> routine associates the activity ID from an IRP with the current thread.

## -parameters

### -param Irp [in]


The IRP whose ID will be propagated to the thread.

### -param PropagatedId [out]


A pointer to memory allocated by the caller to store the ID in the thread.

### -param OriginalId

<p>Upon successfully returning from the call, holds the ID that was previously set on the thread. The driver must call <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioclearactivityidthread"><b>IoClearActivityIdThread</b></a> with this pointer when tracing is completed within the same thread context.</p>

## -returns

<b>IoPropagateActivityIdToThread</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The IRP does not have an ID associated with it.

</td>
</tr>
</table>

## -remarks

This routine should be used by drivers that are tracing aware and are issuing I/O on a worker thread. Note that such drivers must call <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioclearactivityidthread">IoClearActivityIdThread</a> with the <i>OriginalId</i> before they return control from the thread, if the call was successful.

Drivers that use I/O work items do not need to call this routine because the I/O subsystem takes care of propagating activity IDs to threads in that case.
