---
UID: NC:d3dkmthk.PFND3DKMT_CREATEPROTECTEDSESSION
title: PFND3DKMT_CREATEPROTECTEDSESSION (d3dkmthk.h)
description: Implemented by the client driver to create a protected session.
ms.date: 03/04/2022
keywords: ["PFND3DKMT_CREATEPROTECTEDSESSION callback function"]
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
f1_keywords:
 - PFND3DKMT_CREATEPROTECTEDSESSION
 - d3dkmthk/PFND3DKMT_CREATEPROTECTEDSESSION
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CREATEPROTECTEDSESSION
product:
 - Windows
---

# PFND3DKMT_CREATEPROTECTEDSESSION callback function

## -description

Implemented by the client driver to create a protected session.

## -syntax

```cpp
PFND3DKMT_CREATEPROTECTEDSESSION PfnD3dkmtCreateProtectedSession;

NTSTATUS PfnD3dkmtCreateProtectedSession(
    D3DKMT_CREATEPROTECTEDSESSION *unnamedParam1
)
{...}
```

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_CREATEPROTECTEDSESSION](ns-d3dkmthk-_d3dkmt_createprotectedsession.md) structure that contains the information needed to create a protected session.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_CREATEPROTECTEDSESSION](ns-d3dkmthk-_d3dkmt_createprotectedsession.md) and then calling **PfnD3dkmtCreateProtectedSession**.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.
