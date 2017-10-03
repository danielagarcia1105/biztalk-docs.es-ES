---
title: "Getworkflowevent (operación) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2534e0b8-26df-4554-b0df-742014deb64d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dc753bd45452af6ab586a11f216bc65f9539fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getworkflowevent"></a>GetWorkflowEvent (operación)
Inserta el nombre del evento del flujo de trabajo en curso en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wf:Operation Name="GetWorkflowEvent" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el evento del flujo de trabajo en curso.  
  
## <a name="remarks"></a>Comentarios  
 Una instancia de flujo de trabajo puede pasar por varios estados durante el transcurso de su ejecución. Por ejemplo, una instancia de flujo de trabajo puede estar inactiva o suspendida. Cada vez que la instancia de flujo de trabajo cambia de estado, emite un evento de estado de flujo de trabajo a la infraestructura de seguimiento en tiempo de ejecución. El interceptor de BAM de Windows Workflow Foundation es compatible con la mayoría de los eventos definidos por la enumeración de `System.Workflow.Runtime.Tracking.TrackingWorkflowEvent`, como se muestra en la siguiente tabla.  
  
|Evento de actividad|Description|  
|--------------------|-----------------|  
|Cambiado|Se ha producido un cambio de flujo de trabajo en la instancia de flujo de trabajo.|  
|Completado|La instancia de flujo de trabajo ha finalizado.|  
|Creado|La instancia de flujo de trabajo se ha creado.|  
|Excepción|Se ha producido un error no controlado.|  
|Idle|La instancia del flujo de trabajo está inactiva.|  
|Cargado|La instancia de flujo de trabajo se ha cargado en memoria.|  
|Guardado|La instancia de flujo de trabajo se ha guardado.|  
|Reanudado|Se ha reanudado la ejecución de una instancia que se había detenido anteriormente.|  
|Iniciado|La instancia de flujo de trabajo se ha iniciado.|  
|Suspendida|La instancia de flujo de trabajo se ha suspendido.|  
|Finalizado|La instancia de flujo de trabajo se ha finalizado.|  
|Descargado|La instancia de flujo de trabajo se ha descargado desde memoria.|  
  
> [!NOTE]
>  No puede usar `GetWorkflowEvent` ni `GetActivityEvent` en el mismo elemento OnEvent.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo contiene un filtro configurado para buscar una actividad específica ("FoodAndDrinksPolicy") en un flujo de trabajo. En el ejemplo, se configura un filtro para buscar la actividad denominada "FoodAndDrinksPolicy" en un flujo de trabajo cerrado. Esto se realiza mediante la comparación del valor devuelto por `GetWorkflowEvent` al valor constante "Creado".  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowEvent" />   
      <ic:Operation Name="Constant">  
        <ic:Argument>Created</ic:Argument>   
      </ic:Operation>  
    <ic:Operation Name="Equals" />   
  </ic:Expression>  
</ic:Filter>  
```  
  
 Esta operación es útil para el seguimiento del período de vida de un flujo de trabajo y para la detección de excepciones o de otros problemas con el flujo de trabajo.  
  
## <a name="see-also"></a>Vea también  
 [Enumeración System.Workflow.Runtime.Tracking.TrackingWorkflowEvent](http://go.microsoft.com/fwlink/?LinkId=119568)