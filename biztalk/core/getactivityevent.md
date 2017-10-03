---
title: GetActivityEvent | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fe824c9-4cea-44da-b830-5520d67988e0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb039c0e9946091214a52fbb605753a212c233c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getactivityevent"></a>GetActivityEvent (operación)
Inserta el nombre del evento de la actividad en curso en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wf:Operation Name="GetActivityEvent"/>  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el evento de actividad en curso.  
  
## <a name="remarks"></a>Comentarios  
 Una actividad de flujo de trabajo puede pasar por varios estados durante el período de vida del flujo de trabajo. El interceptor de BAM de Windows Workflow Foundation es compatible con la mayoría de los valores de estado de ejecución definidos por la enumeración de `System.Workflow.ComponentModel.ActivityExecutionStatus`, como se muestra en la siguiente tabla.  
  
|Estado de ejecución|Description|  
|----------------------|-----------------|  
|Cancelando|Representa el estado en el que la actividad está siendo cancelada.|  
|Cerrado|Representa el estado en el que una actividad se ha cerrado.|  
|Compensando|Representa el estado en el que una actividad se está compensando.|  
|Ejecutando|Representa el estado en el que una actividad se está ejecutando.|  
|Con errores|Representa el estado en el que una actividad es errónea.|  
  
> [!NOTE]
>  No puede usar `GetActivityEvent` ni `GetWorkflowEvent` en el mismo elemento OnEvent.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo contiene una expresión de filtro de eventos configurada para buscar una actividad específica, FoodAndDringPolicy, en un flujo de trabajo cerrado. Para ello, se usa una combinación de operaciones, incluidas `GetActivityEvent`, `GetActivityName` y operaciones lógicas.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 Este patrón de filtro es habitual con los archivos de configuración del interceptor de Windows Workflow Foundation.  
  
> [!NOTE]
>  Los argumentos no requieren comillas dobles a menos que intente hacer coincidir, de forma explícita, una cadena que contiene comillas dobles.  
  
## <a name="see-also"></a>Vea también  
 [Enumeración System.Workflow.ComponentModel.ActivityExecutionStatus](http://go.microsoft.com/fwlink/?LinkId=119570)