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
# <a name="how-to-configure-the-bam-wcf-interception"></a><span data-ttu-id="d34bb-102">Cómo configurar la intercepción de WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="d34bb-102">How to Configure the BAM WCF Interception</span></span>
<span data-ttu-id="d34bb-103">Para configurar BAM para la intercepción de WCF, es necesario modificar el archivo de configuración del interceptor para obtener acceso al manifiesto del ensamblado adecuado para los orígenes de eventos.</span><span class="sxs-lookup"><span data-stu-id="d34bb-103">To configure BAM for WCF interception, you must modify the interceptor configuration file to access the proper assembly manifest for your event sources.</span></span>  
  
 <span data-ttu-id="d34bb-104">Al configurar los eventos debe especificar con el formato correcto [XPath](../core/xpath.md) expresiones para las acciones.</span><span class="sxs-lookup"><span data-stu-id="d34bb-104">When you are configuring the events you must specify properly formatted [XPath](../core/xpath.md) expressions for the actions.</span></span>  
  
 <span data-ttu-id="d34bb-105">Puede crear con el formato correcto [XPath](../core/xpath.md) expresiones que se usan en la configuración del interceptor habilitando el seguimiento de WCF y ejecutar la aplicación para generar un registro de WCF de ejemplo que contiene el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d34bb-105">You can create properly formatted [XPath](../core/xpath.md) expressions to use in the interceptor configuration by enabling WCF tracing and running the application to produce a sample WCF log which contains the message.</span></span> <span data-ttu-id="d34bb-106">Puede usar el **Microsoft Service Trace Viewer** (SvcTraceViewer.exe) para ver el registro y extraer el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d34bb-106">You can use the **Microsoft Service Trace Viewer** (SvcTraceViewer.exe) to view the log and extract the message.</span></span> <span data-ttu-id="d34bb-107">El visor se incluye con el SDK de WCF.</span><span class="sxs-lookup"><span data-stu-id="d34bb-107">The viewer is included with the WCF SDK.</span></span> <span data-ttu-id="d34bb-108">Lo que se desea [XPath](../core/xpath.md) expresión podrá formar basándose en el mensaje y aplicar a la configuración del interceptor.</span><span class="sxs-lookup"><span data-stu-id="d34bb-108">The desired [XPath](../core/xpath.md) expression can then be formed based on the message and applied to the interceptor configuration.</span></span>  
  
 <span data-ttu-id="d34bb-109">Al configurar la intercepción de WCF de BAM, es fundamental que la extensión del comportamiento usada en el archivo machine.config coincida con la extensión usada en la configuración de comportamiento personalizado de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="d34bb-109">When configuring the BAM WCF interception, it is essential that the behavior extension used in the machine.config file matches the extension used in the custom behavior configuration of the receive location.</span></span> <span data-ttu-id="d34bb-110">Si se cambia el nombre de la extensión de una ubicación de recepción configurada en el archivo machine.config se producirán errores en la carga del comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d34bb-110">Changing the extension name of a configured receive location in the machine.config file causes the behavior to fail to load.</span></span> <span data-ttu-id="d34bb-111">Además, también se producirán errores en la interfaz de usuario de configuración de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="d34bb-111">In addition, the configuration UI of the receive location will fail.</span></span>  
  
 <span data-ttu-id="d34bb-112">Si se trata de un escenario agrupado, dado que el comportamiento personalizado se configura sólo una vez, debe asegurarse de que todos los archivos machine.config en los equipos del clúster especifican la misma extensión del nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="d34bb-112">In case of a clustered scenario, since the custom behavior is configured only once, you must ensure that all the machine.config files on the computers in the cluster specify the same file name extension.</span></span>  
  
### <a name="to-set-the-manifest"></a><span data-ttu-id="d34bb-113">Para establecer el manifiesto</span><span class="sxs-lookup"><span data-stu-id="d34bb-113">To set the manifest</span></span>  
  
1.  <span data-ttu-id="d34bb-114">Establezca el manifiesto en EventSource en la configuración de intercepción como "Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid, Microsoft.BizTalk.Adapter.Wcf.Runtime, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35”.</span><span class="sxs-lookup"><span data-stu-id="d34bb-114">Set the manifest in the EventSource in the Interception Configuration to 'Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid, Microsoft.BizTalk.Adapter.Wcf.Runtime, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d34bb-115">La interfaz cambia de acuerdo con el tipo de puerto de recepción/servicio utilizado.</span><span class="sxs-lookup"><span data-stu-id="d34bb-115">The interface changes based on the type of service/receive port used.</span></span> <span data-ttu-id="d34bb-116">Cambie la línea de manifiesto para reflejar el tipo de puerto que va a utilizar según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d34bb-116">Change the manifest line to reflect the type of port you are using according to the table below.</span></span>  
  
    |<span data-ttu-id="d34bb-117">Tipo de puerto</span><span class="sxs-lookup"><span data-stu-id="d34bb-117">Port Type</span></span>|<span data-ttu-id="d34bb-118">Utilice</span><span class="sxs-lookup"><span data-stu-id="d34bb-118">Use</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="d34bb-119">Puertos bidireccionales</span><span class="sxs-lookup"><span data-stu-id="d34bb-119">Two-way ports</span></span>|<span data-ttu-id="d34bb-120">ITwoWayAsync</span><span class="sxs-lookup"><span data-stu-id="d34bb-120">ITwoWayAsync</span></span>|  
    |<span data-ttu-id="d34bb-121">Puertos unidireccionales con enlaces que son de forma inherente bidireccionales (por ejemplo, HTTP).</span><span class="sxs-lookup"><span data-stu-id="d34bb-121">One-way ports with binding that are inherently two 2 way (for example, HTTP).</span></span>|<span data-ttu-id="d34bb-122">ITwoWayAsyncVoid</span><span class="sxs-lookup"><span data-stu-id="d34bb-122">ITwoWayAsyncVoid</span></span>|  
    |<span data-ttu-id="d34bb-123">Puertos unidireccionales con enlaces que son de forma inherente bidireccionales con transacciones.</span><span class="sxs-lookup"><span data-stu-id="d34bb-123">One-way ports with binding that are inherently two two-way with transactions.</span></span>|<span data-ttu-id="d34bb-124">ITwoWayAsyncVoidTxn</span><span class="sxs-lookup"><span data-stu-id="d34bb-124">ITwoWayAsyncVoidTxn</span></span>|  
    |<span data-ttu-id="d34bb-125">Enlaces que son unidireccionales (por ejemplo, MSMQ).</span><span class="sxs-lookup"><span data-stu-id="d34bb-125">Bindings that are one way (for example, MSMQ).</span></span>|<span data-ttu-id="d34bb-126">IOneWayAsync</span><span class="sxs-lookup"><span data-stu-id="d34bb-126">IOneWayAsync</span></span>|  
    |<span data-ttu-id="d34bb-127">Enlaces que son unidireccionales con transacciones.</span><span class="sxs-lookup"><span data-stu-id="d34bb-127">Bindings that are one way with transactions.</span></span>|<span data-ttu-id="d34bb-128">IOneWayAsyncTxn</span><span class="sxs-lookup"><span data-stu-id="d34bb-128">IOneWayAsyncTxn</span></span>|  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d34bb-129">En el filtro, en lugar de utilizar el [GetOperationName](../core/getoperationname.md) operación, utilice la operación XPath como se resalta en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d34bb-129">In the filter, instead of using the [GetOperationName](../core/getoperationname.md) operation, use XPath operation as highlighted in the following sample.</span></span> <span data-ttu-id="d34bb-130">Para los contratos genéricos todos los mensajes llegan a alguna operación genérica, en cuyo punto se enrutan a operaciones específicas según el propio mensaje (atributo de acción).</span><span class="sxs-lookup"><span data-stu-id="d34bb-130">For generic contracts all messages arrive at some generic operation, at which point they get routed to specific operations based on the message itself (Action attribute).</span></span>  
  
2.  <span data-ttu-id="d34bb-131">El nombre de operación será siempre el mismo en este punto.</span><span class="sxs-lookup"><span data-stu-id="d34bb-131">The operation name will always be the same at this point.</span></span> <span data-ttu-id="d34bb-132">Si se trata de adaptadores de WCF (que utilizan contratos genéricos) el método que se utiliza es BizTalkSubmit.</span><span class="sxs-lookup"><span data-stu-id="d34bb-132">In case of WCF adapters (which uses generic contracts) the method used is BizTalkSubmit.</span></span> <span data-ttu-id="d34bb-133">Puede utilizar un XPath para el nodo Acción en vez de GetOperationName para recuperar el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="d34bb-133">You can use an XPath for the Action node instead of GetOperationName to retrieve the operation name.</span></span> <span data-ttu-id="d34bb-134">Después, puede filtrar según el nombre de operación.</span><span class="sxs-lookup"><span data-stu-id="d34bb-134">You can then filter on the operation name.</span></span>  
  
## <a name="sample-interceptor-configurations"></a><span data-ttu-id="d34bb-135">Configuraciones de interceptor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d34bb-135">Sample Interceptor Configurations</span></span>  
 <span data-ttu-id="d34bb-136">En este ejemplo se muestra el uso de ServiceRequest y de ServiceReply para el adaptador de WCF.</span><span class="sxs-lookup"><span data-stu-id="d34bb-136">This sample shows the usage of ServiceRequest and ServiceReply for the WCF adapter.</span></span> <span data-ttu-id="d34bb-137">En la sección resaltada una [XPath](../core/xpath.md) expresión en la acción se usa para filtrar en la operación en lugar de usar [GetOperationName](../core/getoperationname.md).</span><span class="sxs-lookup"><span data-stu-id="d34bb-137">In the highlighted section an [XPath](../core/xpath.md) expression on the Action is used to filter on the operation instead of using [GetOperationName](../core/getoperationname.md).</span></span> <span data-ttu-id="d34bb-138">También puede filtrar en la respuesta aunque sólo en el caso de ITwoWayAsync.</span><span class="sxs-lookup"><span data-stu-id="d34bb-138">You can filter on the reply as well, but only in the case of ITwoWayAsync.</span></span> <span data-ttu-id="d34bb-139">Las demás interfaces no devuelven nada o valores nulos.</span><span class="sxs-lookup"><span data-stu-id="d34bb-139">All other interfaces return nothing or void.</span></span>  
  
### <a name="servicerequest"></a><span data-ttu-id="d34bb-140">ServiceRequest</span><span class="sxs-lookup"><span data-stu-id="d34bb-140">ServiceRequest</span></span>  
  
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
  
### <a name="servicereply"></a><span data-ttu-id="d34bb-141">ServiceReply</span><span class="sxs-lookup"><span data-stu-id="d34bb-141">ServiceReply</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d34bb-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d34bb-142">See Also</span></span>  
 [<span data-ttu-id="d34bb-143">Configurar el adaptador WCF para interceptar datos BAM</span><span class="sxs-lookup"><span data-stu-id="d34bb-143">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)