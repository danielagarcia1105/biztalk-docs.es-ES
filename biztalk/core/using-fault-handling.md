---
title: Use el control de errores | Documentos de Microsoft
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
ms.openlocfilehash: 00547917da65253123cb2067715a09633547eb4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287468"
---
# <a name="using-fault-handling"></a><span data-ttu-id="9475f-102">Utilizar el control de errores</span><span class="sxs-lookup"><span data-stu-id="9475f-102">Using Fault Handling</span></span>
<span data-ttu-id="9475f-103">Durante la [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] un mensaje de excepción de control de errores no se devuelven al cliente a menos que un **FaultException** (o un subtipo) se produce o un **FaultContract** se implementa.</span><span class="sxs-lookup"><span data-stu-id="9475f-103">During [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] fault handling an exception message is not returned to the client unless a **FaultException** (or a subtype) is thrown or a **FaultContract** is implemented.</span></span> <span data-ttu-id="9475f-104">Por este motivo, sólo se puede realizar el seguimiento de datos desde el propio mensaje de error en estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="9475f-104">So you can only track data from the fault message itself in these scenarios.</span></span> <span data-ttu-id="9475f-105">Una excepción en las implementaciones de devolución de llamada vuelve automáticamente como un mensaje de error para ambos **ServerFault** y **ClientFault** puntos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9475f-105">An exception in callback implementations automatically comes back as a fault message for both **ServerFault** and **ClientFault** track points.</span></span> <span data-ttu-id="9475f-106">Sin embargo, siempre devuelve un error genérico con un mensaje genérico.</span><span class="sxs-lookup"><span data-stu-id="9475f-106">However, it will always return a generic fault with a generic message.</span></span> <span data-ttu-id="9475f-107">Para obtener más información acerca de los contratos de errores WCF, vea [http://go.microsoft.com/fwlink/?LinkId=83132](http://go.microsoft.com/fwlink/?LinkId=83132).</span><span class="sxs-lookup"><span data-stu-id="9475f-107">For more information about WCF fault contracts, see [http://go.microsoft.com/fwlink/?LinkId=83132](http://go.microsoft.com/fwlink/?LinkId=83132).</span></span>  
  
 <span data-ttu-id="9475f-108">También puede realizar el seguimiento de constantes y de propiedades de contexto a través de puntos de seguimiento de error.</span><span class="sxs-lookup"><span data-stu-id="9475f-108">You can also track constants and context properties through the fault track points.</span></span>  
  
 <span data-ttu-id="9475f-109">Si se devuelven los detalles de excepción en errores con el **IncludeExceptionDetailInFaults** atributo, extraer el mensaje de excepción real a través de la expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="9475f-109">If exception details are returned in faults using the **IncludeExceptionDetailInFaults** attribute, you extract the actual exception message through the XPath.</span></span>  
  
 <span data-ttu-id="9475f-110">Control de errores proporcionada por los puntos de seguimiento de error definidos en [getservicecontractcallpoint (operación)](../core/getservicecontractcallpoint.md):</span><span class="sxs-lookup"><span data-stu-id="9475f-110">Fault handling is provided by the fault track points defined in [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md):</span></span>  
  
-   <span data-ttu-id="9475f-111">ServiceFault</span><span class="sxs-lookup"><span data-stu-id="9475f-111">ServiceFault</span></span>  
  
-   <span data-ttu-id="9475f-112">ClientFault</span><span class="sxs-lookup"><span data-stu-id="9475f-112">ClientFault</span></span>  
  
-   <span data-ttu-id="9475f-113">CallbackFault</span><span class="sxs-lookup"><span data-stu-id="9475f-113">CallbackFault</span></span>  
  
 <span data-ttu-id="9475f-114">Cuando se utilizan estos puntos de seguimiento de errores, los datos de error se guardan siempre, incluso cuando se trabaja en un escenario basado en transacciones.</span><span class="sxs-lookup"><span data-stu-id="9475f-114">When using these fault track points, fault data is always persisted, even when operating in a transaction-based scenario.</span></span> <span data-ttu-id="9475f-115">La integridad transaccional se mantiene en todos los datos de seguimiento sin error y los datos de seguimiento sin error se revierten como respuesta al error.</span><span class="sxs-lookup"><span data-stu-id="9475f-115">Transactional integrity is maintained on all non-fault tracked data and non-fault tracked data is rolled back as a response to the fault.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9475f-116">Pista de estos puntos se aplican a la ruta de acceso de respuesta y solo se aplican a los ServiceReply, ClientReply y callbackreply que contrato llamada puntos de servicio proporcionados por [getservicecontractcallpoint (operación)](../core/getservicecontractcallpoint.md).</span><span class="sxs-lookup"><span data-stu-id="9475f-116">These track points are applied to the reply path and apply only to the ServiceReply, ClientReply and CallbackReply service contract call points provided by [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md).</span></span>  
  
## <a name="fault-configuration-sample"></a><span data-ttu-id="9475f-117">Ejemplo de configuración de error</span><span class="sxs-lookup"><span data-stu-id="9475f-117">Fault Configuration Sample</span></span>  
 <span data-ttu-id="9475f-118">El siguiente ejemplo muestra el mensaje de excepción de seguimiento en un **ServiceFault** cuando el servicio lanza un **FaultException** en el **AuthorizationServiceFault** evento; en caso contrario, realiza un seguimiento de la expresión booleana devuelta por la operación en el **AuthorizationServiceReply** eventos.</span><span class="sxs-lookup"><span data-stu-id="9475f-118">The following sample demonstrates tracking the exception message on a **ServiceFault** when the service throws a **FaultException** in the **AuthorizationServiceFault** event; otherwise it tracks the Boolean expression returned by the operation in the **AuthorizationServiceReply** event.</span></span> <span data-ttu-id="9475f-119">Ya sea la **AuthorizationServiceReply** OnEvent o **AuthorizationServiceFault** OnEvent se conserva.</span><span class="sxs-lookup"><span data-stu-id="9475f-119">Either the **AuthorizationServiceReply** OnEvent or the **AuthorizationServiceFault** OnEvent is persisted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9475f-120">La implementación de este ejemplo demuestra la exclusividad mutua de los puntos de seguimiento ServiceReply y ServiceFault.</span><span class="sxs-lookup"><span data-stu-id="9475f-120">The implementation of this sample demonstrates the mutual exclusivity of the ServiceReply and ServiceFault trackpoints.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9475f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9475f-121">See Also</span></span>  
 [<span data-ttu-id="9475f-122">Configurar el adaptador WCF para interceptar datos BAM</span><span class="sxs-lookup"><span data-stu-id="9475f-122">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)