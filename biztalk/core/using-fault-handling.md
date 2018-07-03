---
title: Uso de control de errores | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc793386-d2ec-4e02-9283-3237f65c9e01
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90cb589894b9bb2166cf701866575092da53540e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015125"
---
# <a name="using-fault-handling"></a>Utilizar el control de errores
Durante la [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] un mensaje de excepción de control de errores no se devuelven al cliente a menos que un **FaultException** (o un subtipo) se produce o un **FaultContract** se implementa. Por este motivo, sólo se puede realizar el seguimiento de datos desde el propio mensaje de error en estos escenarios. Una excepción en las implementaciones de devolución de llamada vuelve automáticamente como un mensaje de error para ambos **ServerFault** y **ClientFault** puntos de seguimiento. Sin embargo, siempre devuelve un error genérico con un mensaje genérico. Para obtener más información acerca de los contratos de errores WCF, vea [ http://go.microsoft.com/fwlink/?LinkId=83132 ](http://go.microsoft.com/fwlink/?LinkId=83132).  
  
 También puede realizar el seguimiento de constantes y de propiedades de contexto a través de puntos de seguimiento de error.  
  
 Si se devuelven detalles de la excepción en errores mediante la **IncludeExceptionDetailInFaults** atributo, extraer el mensaje de excepción real a través de la expresión XPath.  
  
 Proporciona control de errores definidos en los puntos de seguimiento de errores [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md):  
  
- ServiceFault  
  
- ClientFault  
  
- CallbackFault  
  
  Cuando se utilizan estos puntos de seguimiento de errores, los datos de error se guardan siempre, incluso cuando se trabaja en un escenario basado en transacciones. La integridad transaccional se mantiene en todos los datos de seguimiento sin error y los datos de seguimiento sin error se revierten como respuesta al error.  
  
> [!NOTE]
>  Pista de estos puntos se aplican a la ruta de acceso de respuesta y solo se aplican a los ServiceReply, ClientReply y callbackreply que contrato llamada puntos de servicio proporcionados por [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md).  
  
## <a name="fault-configuration-sample"></a>Ejemplo de configuración de error  
 El ejemplo siguiente muestra el mensaje de excepción de seguimiento en un **ServiceFault** cuando el servicio lanza un **FaultException** en el **AuthorizationServiceFault** evento; en caso contrario, realiza un seguimiento de la expresión booleana devuelta por la operación en el **AuthorizationServiceReply** eventos. Ya sea el **AuthorizationServiceReply** OnEvent o **AuthorizationServiceFault** OnEvent se conserva.  
  
> [!NOTE]
>  La implementación de este ejemplo demuestra la exclusividad mutua de los puntos de seguimiento ServiceReply y ServiceFault.  
  
```  
<ic:OnEvent IsBegin ="true" IsEnd="false" Name="AuthorizationServiceReply" Source="ESCreditCardService">  
  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceReply</ic:Argument>  
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
      <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
    </ic:Expression>  
  </ic:CorrelationID>  
  
  <ic:Update DataItemName="Status" Type="NVARCHAR">  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Success</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
  <ic:Update DataItemName="Result" Type="NVARCHAR">  
    <ic:Expression>  
      <wcf:Operation Name ="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:AuthorizeWithDataContractResult</wcf:Argument>  
      </wcf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
  <ic:Update DataItemName ="Service Call Date" Type ="DATETIME">  
    <ic:Expression>  
      <wcf:Operation Name ="GetContextProperty">  
        <wcf:Argument>EventTime</wcf:Argument>  
      </wcf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
</ic:OnEvent>  
  
<ic:OnEvent IsBegin ="true" IsEnd="false" Name="AuthorizationServiceFault" Source="ESCreditCardService">  
  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceFault</ic:Argument>  
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
      <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
    </ic:Expression>  
  </ic:CorrelationID>  
  
  <ic:Update DataItemName="Status" Type="NVARCHAR">  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Fault</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
      <ic:Update DataItemName="Source" Type="NVARCHAR">  
        <ic:Expression>  
          <wcf:Operation Name ="XPath">  
            <wcf:Argument>//s:Body/Fault/Reason/Text</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
  <ic:Update DataItemName ="Service Call Date" Type ="DATETIME">  
    <ic:Expression>  
      <wcf:Operation Name ="GetContextProperty">  
        <wcf:Argument>EventTime</wcf:Argument>  
      </wcf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
</ic:OnEvent>  
```  
  
## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de WCF para interceptar datos de BAM](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)