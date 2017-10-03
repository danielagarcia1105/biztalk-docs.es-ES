---
title: GetContextProperty1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8867c29-63de-4a13-9ef9-8c6ab8ea3443
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65b7ffffe4b21e3317b920ac50cdc27b12d708d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getcontextproperty"></a>GetContextProperty
Inserta la propiedad de contexto solicitada en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wcf:Operation Name ="GetContextProperty">  
  <wcf:Argument>EventTime</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a>Parámetros  
 Uno de los siguientes nombres de propiedad de contexto:  
  
|Nombre de propiedad de contexto|Description|  
|---------------------------|-----------------|  
|EventTime|Fecha y hora actuales.|  
|SessionId|Id. de sesión de flujo de trabajo.|  
  
> [!NOTE]
>  Los nombres de propiedades de contexto distinguen mayúsculas de minúsculas.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene la propiedad de contexto solicitada.  
  
## <a name="remarks"></a>Comentarios  
 La hora se almacena en formato UTC en la base de datos.  
  
## <a name="example"></a>Ejemplo  
 En la siguiente expresión de actualización de ejemplo, la fecha de aprobación se obtiene al recuperar la hora del evento actual.  
  
```  
<ic:Update DataItemName ="Approval Date" Type ="DATETIME">  
  <ic:Expression>  
    <wcf:Operation Name ="GetContextProperty">  
      <wcf:Argument>EventTime</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
 Es un uso común de `GetContextProperty`.  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de Windows Communication Foundation](../core/operations-in-windows-communication-foundation.md)