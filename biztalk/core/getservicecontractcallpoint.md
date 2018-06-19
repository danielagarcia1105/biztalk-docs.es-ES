---
title: Getservicecontractcallpoint (operación) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be03d100-0cba-4b80-8056-b582a2cd74ce
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e291bcf733129991f6d3b5000ca8e9bc1353057
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246412"
---
# <a name="getservicecontractcallpoint"></a>GetServiceContractCallPoint (operación)
Inserta el nombre del punto de llamada de contrato de servicio actual en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wcf:Operation Name="GetServiceContractCallPoint" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el punto de llamada de contrato actual.  
  
## <a name="remarks"></a>Comentarios  
 Se puede interceptar un servicio de Windows Communication Framework en distintos puntos de la duración del contrato de servicio. Estas ubicaciones se definen mediante la enumeración `System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint`:  
  
|Punto de llamada de contrato|Description|  
|-------------------------|-----------------|  
|ClientReply|Punto de llamada de respuesta del cliente.|  
|ClientRequest|Punto de llamada de solicitud del cliente.|  
|ClientFault|Punto de error del cliente.|  
|ServiceReply|Punto de llamada de respuesta del servicio.|  
|ServiceRequest|Punto de llamada de solicitud del servicio.|  
|ServiceFault|Punto de error del servicio.|  
|CallbackRequest|Punto de llamada de solicitud de devolución de llamada.|  
|CallbackReply|Punto de llamada de respuesta de devolución de llamada.|  
|CallbackFault|Punto de error de devolución de llamada.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo contiene una expresión de filtro de eventos configurada para buscar una operación específica ("Receive") en el estado de respuesta del cliente. Para ello, se usa una combinación de operaciones, incluidas `GetOperationName`, `GetServiceContractCallPoint` y operaciones lógicas.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Receive</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wcf:Operation Name="GetServiceContractCallPoint" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ClientReply</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de Windows Communication Foundation](../core/operations-in-windows-communication-foundation.md)