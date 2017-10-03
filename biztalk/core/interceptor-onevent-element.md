---
title: Elemento OnEvent del interceptor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d684ac8e-61bc-410b-97a2-6fd3549e0d97
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6fb70b2536dbf5db5b0abc03bc194de154b4317
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interceptor-onevent-element"></a>Elemento OnEvent del interceptor
El **OnEvent** elemento describe un evento real que está asignado a la actividad de BAM envolvente.  
  
## <a name="format"></a>Formato  
 El elemento `OnEvent` contiene elementos secundarios que especifican un filtro de eventos, el Id. de correlación y, opcionalmente, los datos que se van a actualizar, los datos de referencia y un token de continuación.  
  
### <a name="attributes"></a>Atributos  
  
|Nombre del atributo|Description|  
|--------------------|-----------------|  
|Nombre|Nombre de este evento definido por el usuario.|  
|Source|Nombre del evento de origen tal como aparece en un **EventSource** elemento.|  
|IsBegin|Valor booleano que indica si el evento es el comienzo de una nueva actividad de BAM (`true`) o no (`false`).|  
|IsEnd|Valor booleano que indica si el evento es el final de una nueva actividad de BAM (`true`) o no (`false`).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Estado de ejecución|Description|  
|----------------------|-----------------|  
|Filtro|Proporciona una forma de limitar el evento de acuerdo con unos criterios específicos.|  
|CorrelationID|Especifica el Id. de correlación (el Id. de instancia de actividad).|  
|ContinuationToken|Especifica el token de continuación, un Id. de correlación que utilizarán eventos futuros que contribuirán a la misma instancia de actividad.|  
|Update|Especifica los datos que se van a extraer del evento y que se van a importar a la actividad de BAM.|  
|Referencia|Agrega una relación a una actividad de BAM.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una típica **OnEvent** bloque para WF:  
  
```  
<ic:OnEvent Name="BeginAct" IsBegin="true" Source="ResWF">  
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
  <ic:CorrelationID>  
    <ic:Expression>  
      <wf:Operation Name="GetContextProperty">  
        <wf:Argument>InstanceId</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:CorrelationID>  
  <ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
    <ic:Expression>  
      <wf:Operation Name="GetContextProperty">  
        <wf:Argument>EventTime</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  <ic:Update DataItemName="FoodItem" Type="NVARCHAR">  
    <ic:Expression>  
      <wf:Operation Name="GetWorkflowProperty">  
        <wf:Argument>foodItem</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:Update>  
</ic:OnEvent>  
```  
  
 Este ejemplo muestra el típico **OnEvent** bloque para el servicio WCF:  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="AuthorizationRequestService" Source="ESCreditCardService">  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceRequest</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals"/>  
      <wcf:Operation Name="GetOperationName" />  
      <ic:Operation Name="Constant">  
        <ic:Argument>AuthorizeWithDataContract</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals" />  
      <ic:Operation Name ="And" />  
    </ic:Expression>  
  </ic:Filter>  
  <ic:CorrelationID>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>ServiceRequest</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:CorrelationID>  
  <ic:Update DataItemName="Name" Type="NVARCHAR">  
    <ic:Expression>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:creditCard/creditcard:FirstName</wcf:Argument>  
      </wcf:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:creditCard/creditcard:LastName</wcf:Argument>  
      </wcf:Operation>  
      <ic:Operation Name ="Concatenate"/>  
    </ic:Expression>  
  </ic:Update>  
</ic:OnEvent>  
```  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Filter](../core/filter.md)  
  
-   [CorrelationID](../core/correlationid.md)  
  
-   [ContinuationToken](../core/continuationtoken.md)  
  
-   [Referencia](../core/reference.md)  
  
-   [Update](../core/update2.md)  
  
## <a name="see-also"></a>Vea también  
 [Estructura de un archivo de configuración de Interceptor](../core/structure-of-an-interceptor-configuration-file.md)