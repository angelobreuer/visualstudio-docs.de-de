---
title: IDebugSymbolProvider::GetAddressesFromPosition | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition method
ms.assetid: 1b0f02cb-8ace-4614-88f3-0e10239012b3
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 27349cfdc438da133c4cea05077649ebb4df376c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62547155"
---
# <a name="idebugsymbolprovidergetaddressesfromposition"></a>IDebugSymbolProvider::GetAddressesFromPosition
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Diese Methode ordnet eine Dokumentposition in ein Array von Debug-Adressen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT GetAddressesFromPosition(   
   IDebugDocumentPosition2* pDocPos,  
   BOOL                     fStatmentOnly,  
   IEnumDebugAddresses**    ppEnumBegAddresses,  
   IEnumDebugAddresses**    ppEnumEndAddresses  
);  
```  
  
```csharp  
int GetAddressesFromPosition(   
   IDebugDocumentPosition2  pDocPos,  
   bool                     fStatmentOnly,  
   out IEnumDebugAddresses  ppEnumBegAddresses,  
   out IEnumDebugAddresses  ppEnumEndAddresses  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pDocPos`  
 [in] Die Dokumentposition.  
  
 `fStatmentOnly`  
 [in] True gibt an, beschränkt die Debug-Adressen zu einer einzigen Anweisung.  
  
 `ppEnumBegAddresses`  
 [out] Gibt einen Enumerator für die Debug-Startadressen dieser Anweisung oder der Zeile zugeordnet.  
  
 `ppEnumEndAddresses`  
 [out] Gibt eine [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) Enumerator für die abschließende Debug-Adressen, die dieser Anweisung oder der Zeile zugeordnet.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Eine Dokumentposition liegt in der Regel im Bereich von Quellzeilen. Diese Methode bietet die Start- und endadressen Debuggen, die mit diesen Zeilen verknüpft ist. Einige Sprachen ermöglichen die Anweisungen, die sich erstrecken, mehrere Zeilen oder Zeilen, die mehr als eine Anweisung enthält. Diese Methode bietet ein Flag, um die Debug-Adressen, die einer einzelnen Anweisung zu beschränken.  
  
 Es ist möglich, dass eine einzelne Anweisung, um mehrere Debug-Adressen, wie im Fall von Vorlagen zu erhalten.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)
