---
title: Patrones de filtro de eventos comunes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc80168b-25bd-4228-b84c-d38bf4e2fe4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef90a4533b8b12929488d3a323dae47976eace0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234524"
---
# <a name="common-event-filter-patterns"></a>Patrones de filtro de evento comunes
A medida que trabaje con el interceptor de BAM para Windows Workflow Foundation (WF), es probable que observe que hay un conjunto de patrones de filtro comunes que utilizará con frecuencia en los archivos de configuración del interceptor. Aunque algunos de estos patrones de filtro serán exclusivos para sus aplicaciones y entornos, hay muchos patrones que se pueden usar en distintos entornos y en varias aplicaciones.  
  
 En este tema se recogen muchos de los patrones de filtro comunes que usan los archivos de configuración del interceptor escritos para aplicaciones WF. Los patrones se agrupan según el evento de seguimiento de Windows Workflow Foundation:  
  
-   Eventos de estado de actividad  
  
-   Eventos de estado de flujo de trabajo  
  
-   Eventos de usuario  
  
 Todos los patrones se pueden copiar en el archivo de configuración de interceptor y se pueden modificar para adaptarlos a la aplicación.  
  
## <a name="activity-status-event-filter-patterns"></a>Patrones de filtro de evento de estado de actividad  
 Las actividades constituyen los bloques de creación de flujos de trabajo fundamentales. Un flujo de trabajo consiste en un conjunto de actividades organizadas de forma jerárquica en una estructura de árbol. Una actividad representa una acción en un flujo de trabajo. Puede ser una acción sencilla como un retraso o una compuesta con varias actividades secundarias.  
  
 Los filtros que se indican en esta sección filtran actividades y utilizan una o varias de las siguientes operaciones personalizadas del interceptor de BAM para WF:  
  
-   GetActivityName  
  
-   GetActivityEvent (operación)  
  
-   GetActivityType  
  
-   GetActivityProperty  
  
-   GetWorkflowProperty  
  
-   GetContextProperty  
  
> [!NOTE]
>  Si no se usa la operación GetActivityEvent en el filtro, éste buscará sólo eventos de actividad cerrados.  
  
### <a name="filter-by-activity-name-closed-activity"></a>Filtrar por nombre de actividad (actividad cerrada)  
 Con frecuencia tendrá que filtrar los eventos de actividades cerradas por nombre de actividad. Esto resulta útil cuando es necesario capturar datos de una actividad específica como recibir un archivo o escribir datos en una base de datos.  
  
 El siguiente fragmento filtra una actividad cerrada denominada "MyActivity".  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-closed-activity-event"></a>Filtrar por tipo de actividad (evento de actividad cerrada)  
 Habrá ocasiones en las que deseará filtrar una actividad por tipo en lugar de por nombre. Por ejemplo, es posible que desee guardar el nombre de la actividad y una marca de fecha y hora de todas las actividades en un flujo de trabajo. Para ello, use la `GetActivityType` operación. `GetActivityType`Compara el tipo facilitado con el tipo base y todos los tipos derivados para determinar a su coincidencia. La comparación con `System.Workflow.ComponentModel.Activity` coincidirá, ya que todas las actividades del flujo de trabajo deben derivarse de ella.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-event-any-activity-type"></a>Filtrar por evento de actividad (cualquier tipo de actividad)  
 Este filtro usa la operación GetActivityEvent para encontrar actividades cerradas. Resulta útil para capturar información acerca de todos los eventos cerrados (frente a un evento específico por nombre o tipo).  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-type-closed-activity-event"></a>Filtrar por nombre y tipo de actividad (evento de actividad cerrada)  
 Puede elegir que las actividades se filtren por nombre y tipo de actividad si desea especificar el tipo exacto de la actividad (incluida la arquitectura del procesador) que le interesa encontrar. En el siguiente ejemplo se busca "MyActivity" que deriva de `System.Workflow.ComponentModel.Activity`; puede cambiar esto a un tipo derivado para hacerlo más restrictivo.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
<ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-event-any-activity-type"></a>Filtrar por nombre y evento de actividad (cualquier tipo de actividad)  
 Esta expresión filtra según el nombre y el evento de actividad. Esto resulta útil si se desea capturar información para una actividad y evento específicos o cuando se capturan datos desde varios eventos de actividad para una actividad determinada. Por ejemplo, es posible que desee dos elementos OnEvent diferentes, uno para MyActivity cuando se está ejecutando y uno para cuando está cerrado, tal y como se muestra a continuación.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-event"></a>Filtrar por tipo y evento de actividad  
 Este filtro resulta útil para capturar información acerca de todas las actividades que derivan de un tipo específico durante un único evento de actividad. Por ejemplo, es posible que esté interesado en realizar el seguimiento de un Id. de pedido y una marca de fecha y hora de un pedido a medida que pasa por un flujo de trabajo. Para ello, use la `GetActivityEvent` y `GetActivityType` operaciones. `GetActivityType`Compara el tipo facilitado con el tipo base y todos los tipos derivados para determinar a su coincidencia. La comparación con `System.Workflow.ComponentModel.Activity` coincidirá, ya que todas las actividades del flujo de trabajo deben derivarse de ella.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-type-and-event"></a>Filtrar por nombre, tipo y evento de actividad  
 El filtrado de una actividad por nombre, tipo y evento puede resultar útil cuando desea que califique mejor la actividad cuyo seguimiento le interesa. Por ejemplo, el siguiente filtro busca la actividad cerrada "MyActivity" que tiene un tipo igual a o que deriva de `System.Workflow.ComponentModel.Activity`.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="workflow-status-event-filter-patterns"></a>Patrones de filtro de evento de estado de flujo de trabajo  
 Los filtros que se indican en esta sección filtran eventos de flujo de trabajo y utilizan una o varias de las siguientes operaciones personalizadas del interceptor de BAM para WF:  
  
-   GetWorkflowEvent (operación)  
  
-   GetContextProperty  
  
### <a name="filter-by-workflow-event"></a>Filtrar por evento de flujo de trabajo  
 Esta expresión filtra por evento de flujo de trabajo.  
  
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
  
## <a name="user-event-filter-patterns"></a>Patrones de filtro de evento de usuario  
 Si la aplicación realiza el seguimiento de información personalizada con el método TrackData, puede filtrar según las características de los datos mediante una o varias operaciones de datos de usuario personalizados del interceptor de BAM para WF que se indican a continuación:  
  
-   GetUserDataType (operación)  
  
-   GetUserKey (operación)  
  
-   GetUserData (operación)  
  
 El filtro puede combinar estas operaciones con las siguientes para crear una expresión más compleja:  
  
-   GetActivityName  
  
-   GetActivityType  
  
-   GetActivityProperty  
  
-   GetWorkflowProperty  
  
-   GetContextProperty  
  
 Si el filtro no incluye al menos una operación de datos de usuario, el filtro no será un filtro de evento de usuario y el OnEvent envolvente producirá un error (si una operación de usuario aparece en una expresión de actualización correspondiente) o se identificará como un punto de seguimiento de actividad y no de usuario.  
  
### <a name="filter-by-activity-name-and-user-data-type"></a>Filtrar por nombre de actividad y tipo de datos de usuario  
 Con frecuencia, puede identificar un evento por nombre de actividad y tipo de datos de usuario. La siguiente expresión filtra una actividad denominada "MyActivity" y un tipo de datos de usuario que deriva de `System.Object`.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-data-type"></a>Filtrar por tipo de actividad y tipo de datos de usuario  
 Puede filtrar según el tipo de actividad y el tipo de datos de usuario. De este modo se consigue flexibilidad a la hora de filtrar eventos según el tipo del que derivan porque `GetActivityType` y `GetUserDataType` se comparan con el tipo especificado y todos los tipos derivados.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-data-type"></a>Filtrar por nombre de actividad, tipo de actividad y tipo de datos de usuario  
 Este filtro restringe aún más el patrón de filtro de tipo de actividad y de tipo de datos de usuario al incluir el nombre de la actividad.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-user-key"></a>Filtrar por nombre de actividad y clave del usuario  
 Si la aplicación tiene una actividad que llama a `TrackData` con una clave determinada en el tiempo de ejecución, es posible que desee filtrar por nombre de actividad y clave de usuario. Esto le habilitará para desencadenar un `OnEvent` basado en un valor de clave específico. Por ejemplo, la aplicación podría definir varias claves y seleccionar una, de forma dinámica, en la actividad.  
  
 La siguiente expresión filtra "MyActivity" que contiene una clave de usuario denominada "ItemKey".  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-key"></a>Filtrar por tipo de actividad y clave de usuario  
 Si la aplicación contiene varias actividades que llaman a `TrackData` con una clave determinada en el tiempo de ejecución, es posible que desee filtrar por nombre de actividad y clave de usuario. Esto le habilitará para desencadenar un `OnEvent` basado en un valor de clave específico. Por ejemplo, la aplicación podría definir varias claves y seleccionar una, de forma dinámica, en la actividad.  
  
 La siguiente expresión filtra cualquier actividad que derive de `System.Workflow.ComponentModel.Activity` y que contenga una clave de usuario denominada "ItemKey".  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-key"></a>Filtrar por nombre de actividad, tipo de actividad y clave de usuario  
 Este patrón de filtro refine aún más el patrón de filtro de tipo de actividad y de clave de usuario al incluir el nombre de la actividad en el filtro.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-user-data-type-and-user-key"></a>Filtrar por nombre de actividad, tipo de datos de usuario y clave de usuario  
 Este filtro resulta útil cuando se desea restringir el filtro a una actividad con un nombre y una clave de usuario específica y que derive de un tipo de datos concreto. Por ejemplo, la actividad puede llamar a TrackData mediante la clave "Item" y un valor de datos de cadena o entero según el tipo de elemento.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-user-data-type-and-user-key"></a>Filtrar por tipo de actividad, tipo de datos de usuario y clave de usuario  
 Este filtro resulta útil cuando se desea restringir el filtro a un tipo de actividad con una clave de usuario específica y que derive de un tipo de datos concreto. Puede ser más o menos restrictivo que el filtro que usa el nombre de actividad, el tipo de datos de usuario y la clave de usuario basados en el tipo usado. Si especifica el tipo más derivado, podría ser más restrictivo; en cambio, si especifica el tipo de base raíz, podría ser menos restrictivo.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-user-data-type-and-user-key"></a>Filtrar por nombre de actividad, tipo de actividad, tipo de datos de usuario y clave de usuario  
 Este filtro restringe aún más el patrón de tipo de actividad, tipo de datos de usuario y clave de usuario al agregar el nombre de la actividad.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>   
```