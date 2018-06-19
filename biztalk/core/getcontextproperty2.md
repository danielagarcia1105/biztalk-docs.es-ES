---
title: GetContextProperty2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2554a210-cfb4-4b63-9afa-ffe2a853ba7b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f834bf1271f6706c332123d8b1835e0bd730f069
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246148"
---
# <a name="getcontextproperty"></a>GetContextProperty
Inserta la propiedad de contexto solicitada en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wf:Operation Name="GetContextProperty">  
  <wf:Argument>ContextPropertyName</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>Parámetros  
 Uno de los siguientes nombres de propiedad de contexto:  
  
|Nombre de propiedad de contexto|Description|  
|---------------------------|-----------------|  
|EventTime|Fecha y hora actuales.|  
|InstanceID|Id. de instancia de flujo de trabajo.|  
  
> [!NOTE]
>  Los nombres de propiedades de contexto distinguen mayúsculas de minúsculas.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene la propiedad de contexto solicitada.  
  
## <a name="remarks"></a>Comentarios  
 La hora se almacena en formato UTC en la base de datos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, una expresión para extraer el **InstanceId** se usa en un bloque correlationID para establecer el identificador de correlación.  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>InstanceId</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 Es un uso común de `GetContextProperty`.