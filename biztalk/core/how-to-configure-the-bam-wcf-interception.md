---
title: Cómo configurar la intercepción de WCF de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d85aa130-3219-4df1-8974-a44a51a15002
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90577a73abc0291635bf4b7d9bad34a11d1f806
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249212"
---
# <a name="how-to-configure-the-bam-wcf-interception"></a>Cómo configurar la intercepción de WCF de BAM
Para configurar BAM para la intercepción de WCF, es necesario modificar el archivo de configuración del interceptor para obtener acceso al manifiesto del ensamblado adecuado para los orígenes de eventos.  
  
 Al configurar los eventos debe especificar con el formato correcto [XPath](../core/xpath.md) expresiones para las acciones.  
  
 Puede crear con el formato correcto [XPath](../core/xpath.md) expresiones que se usan en la configuración del interceptor habilitando el seguimiento de WCF y ejecutar la aplicación para generar un registro de WCF de ejemplo que contiene el mensaje. Puede usar el **Microsoft Service Trace Viewer** (SvcTraceViewer.exe) para ver el registro y extraer el mensaje. El visor se incluye con el SDK de WCF. Lo que se desea [XPath](../core/xpath.md) expresión podrá formar basándose en el mensaje y aplicar a la configuración del interceptor.  
  
 Al configurar la intercepción de WCF de BAM, es fundamental que la extensión del comportamiento usada en el archivo machine.config coincida con la extensión usada en la configuración de comportamiento personalizado de la ubicación de recepción. Si se cambia el nombre de la extensión de una ubicación de recepción configurada en el archivo machine.config se producirán errores en la carga del comportamiento. Además, también se producirán errores en la interfaz de usuario de configuración de la ubicación de recepción.  
  
 Si se trata de un escenario agrupado, dado que el comportamiento personalizado se configura sólo una vez, debe asegurarse de que todos los archivos machine.config en los equipos del clúster especifican la misma extensión del nombre de archivo.  
  
### <a name="to-set-the-manifest"></a>Para establecer el manifiesto  
  
1.  Establezca el manifiesto en EventSource en la configuración de intercepción como "Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid, Microsoft.BizTalk.Adapter.Wcf.Runtime, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35”.  
  
    > [!NOTE]
    >  La interfaz cambia de acuerdo con el tipo de puerto de recepción/servicio utilizado. Cambie la línea de manifiesto para reflejar el tipo de puerto que va a utilizar según la tabla siguiente.  
  
    |Tipo de puerto|Utilice|  
    |---------------|---------|  
    |Puertos bidireccionales|ITwoWayAsync|  
    |Puertos unidireccionales con enlaces que son de forma inherente bidireccionales (por ejemplo, HTTP).|ITwoWayAsyncVoid|  
    |Puertos unidireccionales con enlaces que son de forma inherente bidireccionales con transacciones.|ITwoWayAsyncVoidTxn|  
    |Enlaces que son unidireccionales (por ejemplo, MSMQ).|IOneWayAsync|  
    |Enlaces que son unidireccionales con transacciones.|IOneWayAsyncTxn|  
  
    > [!IMPORTANT]
    >  En el filtro, en lugar de utilizar el [GetOperationName](../core/getoperationname.md) operación, utilice la operación XPath como se resalta en el ejemplo siguiente. Para los contratos genéricos todos los mensajes llegan a alguna operación genérica, en cuyo punto se enrutan a operaciones específicas según el propio mensaje (atributo de acción).  
  
2.  El nombre de operación será siempre el mismo en este punto. Si se trata de adaptadores de WCF (que utilizan contratos genéricos) el método que se utiliza es BizTalkSubmit. Puede utilizar un XPath para el nodo Acción en vez de GetOperationName para recuperar el nombre de la operación. Después, puede filtrar según el nombre de operación.  
  
## <a name="sample-interceptor-configurations"></a>Configuraciones de interceptor de ejemplo  
 En este ejemplo se muestra el uso de ServiceRequest y de ServiceReply para el adaptador de WCF. En la sección resaltada una [XPath](../core/xpath.md) expresión en la acción se usa para filtrar en la operación en lugar de usar [GetOperationName](../core/getoperationname.md). También puede filtrar en la respuesta aunque sólo en el caso de ITwoWayAsync. Las demás interfaces no devuelven nada o valores nulos.  
  
### <a name="servicerequest"></a>ServiceRequest  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="WCFServiceRequest" Source="WCFService">  
      <ic:Filter>  
        <ic:Expression>  
          <wcf:Operation Name="GetServiceContractCallPoint"/>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>ServiceRequest</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
          <wcf:Operation Name ="XPath">  
            <wcf:Argument>//s:Header/a:Action</wcf:Argument>  
          </wcf:Operation>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>Operation1</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
          <ic:Operation Name ="And" />  
        </ic:Expression>  
      </ic:Filter>  
  
      <ic:CorrelationID>  
        <ic:Expression>  
          <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
        </ic:Expression>  
      </ic:CorrelationID>  
  
      <ic:Update DataItemName ="Activity Date" Type ="DATETIME">  
        <ic:Expression>  
          <wcf:Operation Name ="GetContextProperty">  
            <wcf:Argument>EventTime</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
      <ic:Update DataItemName ="Source" Type ="NVARCHAR">  
        <ic:Expression>  
          <ic:Operation Name="Constant">  
            <ic:Argument>WcfAdapter_ServiceRequest</ic:Argument>  
          </ic:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
    </ic:OnEvent>  
```  
  
### <a name="servicereply"></a>ServiceReply  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="WCFServiceReply" Source="WCFService">  
      <ic:Filter>  
        <ic:Expression>  
          <wcf:Operation Name="GetServiceContractCallPoint"/>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>ServiceReply</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
        </ic:Expression>  
      </ic:Filter>  
  
      <ic:CorrelationID>  
        <ic:Expression>  
          <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
        </ic:Expression>  
      </ic:CorrelationID>  
  
      <ic:Update DataItemName ="Activity Date" Type ="DATETIME">  
        <ic:Expression>  
          <wcf:Operation Name ="GetContextProperty">  
            <wcf:Argument>EventTime</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
      <ic:Update DataItemName ="Name" Type ="NVARCHAR">  
        <ic:Expression>  
          <ic:Operation Name="Constant">  
            <ic:Argument>WcfAdapter_ServiceReply</ic:Argument>  
          </ic:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
    </ic:OnEvent>  
```  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador WCF para interceptar datos BAM](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)