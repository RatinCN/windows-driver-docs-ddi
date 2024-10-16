---
UID: NC:d3d12umddi.PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054
title: PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054
description: Queries for clock calibration information.
tech.root: display
ms.date: 04/04/2019
keywords: ["PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
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
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0021, 19H1
f1_keywords:
 - PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054
 - d3d12umddi/PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054 callback function


## -description

Queries for clock calibration information.

## -parameters

### -param unnamedParam1

The device to query clock information for.

### -param unnamedParam2

A handle to the command queue.

### -param pClockData

Pointer to a [D3D12DDI_GPUCLOCKDATA_0054](ns-d3d12umddi-d3d12ddi_gpuclockdata_0054.md) structure that contains the output frequency, GPU clock, and CPU clock on the specified engine.

## -prototype

```
//Declaration

PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054 Pfnd3d12ddiQueryClockCalibration0054; 

// Definition

void Pfnd3d12ddiQueryClockCalibration0054 
(
	D3D12DDI_HDEVICE Arg1
	D3D12DDI_HCOMMANDQUEUE Arg2
	D3D12DDI_GPUCLOCKDATA_0054 *pClockData
)
{...}

```

## -remarks

## -see-also

