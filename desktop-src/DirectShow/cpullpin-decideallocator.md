---
description: The DecideAllocator method negotiates an allocator with the output pin.
ms.assetid: 5c04f440-b177-4caa-989f-3aa783c4b348
title: CPullPin.DecideAllocator method (Pullpin.h)
ms.topic: reference
ms.date: 4/26/2023
topic_type: 
- APIRef
- kbSyntax
api_name: 
- CPullPin.DecideAllocator
api_type: 
- COM
api_location: 
- Strmbase.lib
- Strmbase.dll
- Strmbasd.lib
- Strmbasd.dll
ms.custom: UpdateFrequency5
---

# CPullPin.DecideAllocator method

\[The feature associated with this page, [DirectShow](/windows/win32/directshow/directshow), is a legacy feature. It has been superseded by [MediaPlayer](/uwp/api/Windows.Media.Playback.MediaPlayer) and [IMFMediaEngine](/windows/win32/api/mfmediaengine/nn-mfmediaengine-imfmediaengine). **MediaPlayer** and **IMFMediaEngine** have been optimized for Windows 10 and Windows 11. Microsoft strongly recommends that new code use **MediaPlayer** and **IMFMediaEngine** instead of **DirectShow**, when possible. Microsoft suggests that existing code that uses the legacy APIs be rewritten to use the new APIs if possible.\]

The `DecideAllocator` method negotiates an allocator with the output pin.

## Syntax


```C++
virtual HRESULT DecideAllocator(
   IMemAllocator        *pAlloc,
   ALLOCATOR_PROPERTIES *pProps
);
```



## Parameters

<dl> <dt>

*pAlloc* 
</dt> <dd>

Pointer to the [**IMemAllocator**](/windows/desktop/api/Strmif/nn-strmif-imemallocator) interface of the input pin's preferred allocator, or **NULL**.

</dd> <dt>

*pProps* 
</dt> <dd>

Pointer to an optional [**ALLOCATOR\_PROPERTIES**](/windows/win32/api/strmif/ns-strmif-allocator_properties) structure that contains the input pin's buffer requirements.

</dd> </dl>

## Return value

Returns S\_OK if successful, or an error code otherwise.

## Remarks

This method calls the [**IAsyncReader::RequestAllocator**](/windows/desktop/api/Strmif/nf-strmif-iasyncreader-requestallocator) method to negotiate an allocator. It passes the *pAlloc* parameter directly to the **RequestAllocator** method. It passes the *pProps* parameter to **RequestAllocator** if *pProps* is non-**NULL**; otherwise, it creates an **ALLOCATOR\_PROPERTIES** structure with a default request of three 64K buffers.

## Requirements



| Requirement | Value |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Pullpin.h</dt> </dl>                                                                                                       |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CPullPin Class**](cpullpin.md)
</dt> <dt>

[**CPullPin::Connect**](cpullpin-connect.md)
</dt> </dl>

 

 




