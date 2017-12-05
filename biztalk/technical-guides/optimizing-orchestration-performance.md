---
title: "Optimizar el rendimiento de la orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 437c7325-f037-451a-8dbd-f8d8c8889e20
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4f8a3b0bcc58fbed428152bb9f55c34d867258a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="optimizing-orchestration-performance"></a><span data-ttu-id="39f81-102">Optimizar el rendimiento de la orquestación</span><span class="sxs-lookup"><span data-stu-id="39f81-102">Optimizing Orchestration Performance</span></span>
<span data-ttu-id="39f81-103">Este tema describe las prácticas recomendadas para utilizar orquestaciones en soluciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="39f81-103">This topic describes best practices for using orchestrations in BizTalk Server solutions.</span></span> <span data-ttu-id="39f81-104">Esto incluye recomendaciones para:</span><span class="sxs-lookup"><span data-stu-id="39f81-104">This includes recommendations for:</span></span>  
  
-   <span data-ttu-id="39f81-105">Reducir la latencia de las soluciones de BizTalk Server que utilizan las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="39f81-105">Reducing latency of BizTalk Server solutions that use orchestrations</span></span>  
  
    -   <span data-ttu-id="39f81-106">Eliminación de orquestaciones para solo patrones de mensajería</span><span class="sxs-lookup"><span data-stu-id="39f81-106">Eliminating orchestrations for messaging only patterns</span></span>  
  
    -   <span data-ttu-id="39f81-107">Utilización en línea envía desde las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="39f81-107">Utilizing inline sends from orchestrations</span></span>  
  
    -   <span data-ttu-id="39f81-108">Minimizar los puntos de persistencia de orquestación</span><span class="sxs-lookup"><span data-stu-id="39f81-108">Minimizing orchestration persistence points</span></span>  
  
-   <span data-ttu-id="39f81-109">Anidar orquestaciones</span><span class="sxs-lookup"><span data-stu-id="39f81-109">Nesting orchestrations</span></span>  
  
-   <span data-ttu-id="39f81-110">Patrones de diseño de orquestación</span><span class="sxs-lookup"><span data-stu-id="39f81-110">Orchestration design patterns</span></span>  
  
-   <span data-ttu-id="39f81-111">Bloques de control de excepciones de orquestación</span><span class="sxs-lookup"><span data-stu-id="39f81-111">Orchestration exception handling blocks</span></span>  
  
## <a name="recommendations-for-optimizing-orchestrations-for-low-latency-scenarios"></a><span data-ttu-id="39f81-112">Recomendaciones para optimizar las orquestaciones escenarios de baja latencia</span><span class="sxs-lookup"><span data-stu-id="39f81-112">Recommendations for optimizing orchestrations for low latency scenarios</span></span>  
 <span data-ttu-id="39f81-113">Pueden emplear las técnicas siguientes para reducir la latencia de las soluciones de BizTalk Server que utilizan las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="39f81-113">The following techniques can be used to reduce latency of BizTalk Server solutions that use orchestrations.</span></span>  
  
### <a name="eliminate-orchestrations-for-messaging-only-patterns"></a><span data-ttu-id="39f81-114">Eliminar orquestaciones para solo patrones de mensajería</span><span class="sxs-lookup"><span data-stu-id="39f81-114">Eliminate orchestrations for messaging only patterns</span></span>  
 <span data-ttu-id="39f81-115">Siempre que sea posible minimizar el uso de orquestaciones para aumentar el rendimiento global y reducir la latencia de los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="39f81-115">When possible minimize the use of orchestrations to increase overall throughput and reduce the latency of business processes.</span></span> <span data-ttu-id="39f81-116">Si no queda necesidad de ejecutar mucho las transacciones y no es necesario para invocar varios sistemas para cada solicitud, a continuación, considere la posibilidad de eliminar las orquestaciones y mover la lógica de negocios a puertos de envío y recepción para reducir la cantidad total de ida y vuelta a la BizTalkMsgBoxDb y reducir la latencia al acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="39f81-116">If there is no need to run long running transactions and there is no need to invoke several systems for each request, then consider eliminating orchestrations and moving business logic to Receive and Send Ports to reduce the total amount of roundtrips to the BizTalkMsgBoxDb and decrease the latency due to database access.</span></span> <span data-ttu-id="39f81-117">En este caso, implementar canalizaciones personalizadas y reutilizar clases auxiliares que anteriormente se han invocado desde las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="39f81-117">In this case, implement custom pipelines and reuse helper classes that were previously invoked from orchestrations.</span></span> <span data-ttu-id="39f81-118">Usar orquestaciones solo cuando sea necesario para implementar patrones de diseño como de dispersión y recopilación o convoyes.</span><span class="sxs-lookup"><span data-stu-id="39f81-118">Use orchestrations only when strictly needed to implement design patterns as Scatter and Gather or Convoys.</span></span> <span data-ttu-id="39f81-119">Para obtener más información sobre los patrones de diseño de orquestación, vea el tema [implementar patrones de diseño en orquestaciones](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) en la documentación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="39f81-119">For more information about Orchestration Design Patterns, see the topic [Implementing Design Patterns in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) in the BizTalk Server documentation.</span></span>  
  
### <a name="use-inline-sends-from-orchestrations-to-accommodate-low-latency-scenarios"></a><span data-ttu-id="39f81-120">Usar en línea se envía desde las orquestaciones para dar cabida a escenarios de baja latencia</span><span class="sxs-lookup"><span data-stu-id="39f81-120">Use inline sends from orchestrations to accommodate low latency scenarios</span></span>  
 <span data-ttu-id="39f81-121">Siempre que sea posible, minimizar el uso de las orquestaciones y favorecer patrones únicamente de mensajería para aumentar el rendimiento global y reducir la latencia de los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="39f81-121">Whenever possible, minimize the use of orchestrations and favor messaging-only patterns to increase the overall throughput and reduce the latency of the business processes.</span></span> <span data-ttu-id="39f81-122">Si no es necesario para las transacciones de larga ejecución y no es necesario para la lógica de negocios invocar varios sistemas, a continuación, considere la posibilidad de mover la lógica de negocios para puertos de envío y recepción y eliminación del uso de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="39f81-122">If there is no need for long-running transactions and there is no need for business logic to invoke several systems, then consider moving business logic to receive and send Ports and eliminating the use of orchestrations.</span></span> <span data-ttu-id="39f81-123">Este enfoque puede implementarse con canalizaciones personalizadas que y volver a las clases auxiliares que anteriormente se han invocado desde las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="39f81-123">This approach can be implemented with custom pipelines and which reuse the helper classes that were previously invoked from orchestrations.</span></span> <span data-ttu-id="39f81-124">Para lograr un mejor rendimiento en escenarios de latencia baja, puede adoptar uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="39f81-124">In order to achieve better performance in low latency scenarios, adopt one of the following approaches:</span></span>  
  
-   <span data-ttu-id="39f81-125">Eliminar orquestaciones innecesarias y adoptar patrones únicamente de mensajería para reducir la cantidad total de ida y vuelta a la base de datos de BizTalk MessageBox.</span><span class="sxs-lookup"><span data-stu-id="39f81-125">Eliminate unnecessary orchestrations and adopt messaging-only patterns to reduce the total amount of roundtrips to the BizTalk MessageBox database.</span></span> <span data-ttu-id="39f81-126">Este enfoque permite una latencia baja como envíos en línea omisión el motor y el asociado de mensajería de BizTalk sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="39f81-126">This approach accommodates low latency because inline sends bypass the BizTalk messaging engine and the associated overhead.</span></span> <span data-ttu-id="39f81-127">Funcionalidad de envío de orquestación en línea se proporciona con BizTalk Server 2006 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="39f81-127">Orchestration inline send functionality is provided with BizTalk Server 2006 and later.</span></span>  
  
-   <span data-ttu-id="39f81-128">Orquestaciones interior, eliminar los puertos lógicos que se enlaza a puertos físicos y uso en línea se envía en su lugar.</span><span class="sxs-lookup"><span data-stu-id="39f81-128">Inside orchestrations, eliminate logical ports bound to physical ports and use in-line sends in their place.</span></span> <span data-ttu-id="39f81-129">Por ejemplo, un envío en línea podría utilizarse para crear una instancia de una clase de proxy WCF para invocar un servicio Web descendente o un componente ADO.NET para tener acceso a una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="39f81-129">For example, an inline send could be used to create an instance of a  WCF proxy class to invoke a downstream Web service or an ADO.NET component to access a SQL Server database.</span></span> <span data-ttu-id="39f81-130">En el diagrama siguiente, se realiza un envío en línea cuando la orquestación crea una instancia de un componente de negocio, lo que hace internamente el uso de WCF objeto de proxy para llamar directamente a un servicio Web descendente:</span><span class="sxs-lookup"><span data-stu-id="39f81-130">In the following diagram, an inline send is performed when the orchestration instantiates a business component, which internally makes use of a WCF  proxy object to directly invoke a downstream Web service:</span></span>  
  
     <span data-ttu-id="39f81-131">![Representación de envío en línea de orquestación de BizTalk](../technical-guides/media/inlinesend.gif "InlineSend")</span><span class="sxs-lookup"><span data-stu-id="39f81-131">![Depiction of BizTalk Orchestration Inline Send](../technical-guides/media/inlinesend.gif "InlineSend")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39f81-132">Aunque el uso de envíos en línea desde las orquestaciones reducirá considerablemente la latencia, existen limitaciones en este enfoque.</span><span class="sxs-lookup"><span data-stu-id="39f81-132">Although using inline sends from orchestrations will significantly reduce latency, there are limitations to this approach.</span></span> <span data-ttu-id="39f81-133">Como en línea envía omite el motor de mensajería de BizTalk, la siguiente funcionalidad proporcionada con el motor de mensajería no está disponible:</span><span class="sxs-lookup"><span data-stu-id="39f81-133">Because inline sends bypass the BizTalk messaging engine, the following functionality provided with the messaging engine is not available:</span></span>  
>   
>  -   <span data-ttu-id="39f81-134">Canalizaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="39f81-134">Transactional pipelines</span></span>  
> -   <span data-ttu-id="39f81-135">Canalizaciones recuperables</span><span class="sxs-lookup"><span data-stu-id="39f81-135">Recoverable pipelines</span></span>  
> -   <span data-ttu-id="39f81-136">Canalizaciones que llaman a la API de interceptor de BAM</span><span class="sxs-lookup"><span data-stu-id="39f81-136">Pipelines that call the BAM interceptor API</span></span>  
> -   <span data-ttu-id="39f81-137">La compatibilidad con adaptadores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="39f81-137">BizTalk Server adapter support</span></span>  
> -   <span data-ttu-id="39f81-138">Procesar por lotes</span><span class="sxs-lookup"><span data-stu-id="39f81-138">Batching</span></span>  
> -   <span data-ttu-id="39f81-139">Reintentos</span><span class="sxs-lookup"><span data-stu-id="39f81-139">Retries</span></span>  
> -   <span data-ttu-id="39f81-140">Inicialización de conjunto de correlaciones</span><span class="sxs-lookup"><span data-stu-id="39f81-140">Correlation set initialization</span></span>  
> -   <span data-ttu-id="39f81-141">Configuración declarativa</span><span class="sxs-lookup"><span data-stu-id="39f81-141">Declarative configuration</span></span>  
> -   <span data-ttu-id="39f81-142">Transportes secundarios</span><span class="sxs-lookup"><span data-stu-id="39f81-142">Secondary transports</span></span>  
> -   <span data-ttu-id="39f81-143">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="39f81-143">Tracking</span></span>  
> -   <span data-ttu-id="39f81-144">Uso declarativo de BAM</span><span class="sxs-lookup"><span data-stu-id="39f81-144">Declarative use of BAM</span></span>  
  
 <span data-ttu-id="39f81-145">Para obtener más información acerca de los tipos de canalizaciones que no se puede ejecutar desde una orquestación, consulte la sección "Restricciones" del tema [cómo usar expresiones para ejecutar canalizaciones](http://go.microsoft.com/fwlink/?LinkId=158008) (http://go.Microsoft.com/fwlink/?) LinkId = 158008) en la documentación de BizTalk Server 2010.</span><span class="sxs-lookup"><span data-stu-id="39f81-145">For more information about the types of pipelines that cannot be executed from within an orchestration, see the “Restrictions” section of the topic [How to Use Expressions to Execute Pipelines](http://go.microsoft.com/fwlink/?LinkId=158008) (http://go.microsoft.com/fwlink/?LinkId=158008) in the BizTalk Server 2010 documentation.</span></span>  
  
### <a name="optimize-orchestration-latency-by-reducing-the-number-of-persistence-points-if-possible"></a><span data-ttu-id="39f81-146">Optimizar la latencia de orquestación al reducir el número de puntos de persistencia, si es posible</span><span class="sxs-lookup"><span data-stu-id="39f81-146">Optimize orchestration latency by reducing the number of persistence points, if possible</span></span>  
 <span data-ttu-id="39f81-147">Un ámbito de la orquestación sólo debe estar marcada como "transaccional de larga ejecución" Si desea utilizar tiempos de espera de compensación o en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="39f81-147">An orchestration scope only needs to be marked as “long-running transactional” if you want to use compensation or scope timeouts.</span></span> <span data-ttu-id="39f81-148">Un ámbito transaccional de larga duración provoca un punto de persistencia adicional al final del ámbito, por lo que debería evitarse cuando no necesite usar la compensación o tiempos de espera de ámbito.</span><span class="sxs-lookup"><span data-stu-id="39f81-148">A long-running transactional scope causes an extra persistence point at the end of the scope, so they should be avoided when you don’t need to use compensation or scope timeouts.</span></span> <span data-ttu-id="39f81-149">Un ámbito atómico hace que un punto de persistencia al final del ámbito, pero también garantiza que no hay puntos de persistencia se produzcan dentro del ámbito atómico.</span><span class="sxs-lookup"><span data-stu-id="39f81-149">An atomic scope causes a persistence point at the end of the scope, but also guarantees that no persistence points will occur inside the atomic scope.</span></span> <span data-ttu-id="39f81-150">Este efecto secundario de ninguna persistencia dentro del ámbito a veces puede utilizarse para aprovechar para puntos de persistencia de lote (al realizar varias envía, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="39f81-150">This side-effect of no persistence inside the scope can sometimes be used to your advantage to batch persistence points (when doing multiple sends, for example).</span></span> <span data-ttu-id="39f81-151">En general, no obstante, se recomienda evitar ámbitos atómicos si es posible.</span><span class="sxs-lookup"><span data-stu-id="39f81-151">In general, though, we recommend avoiding atomic scopes if possible.</span></span> <span data-ttu-id="39f81-152">El motor de orquestaciones guarda en el almacenamiento persistente el estado completo de una instancia de orquestación de ejecución en varios puntos, para que la instancia más adelante se restaura en la memoria y llevan a cabo hasta su finalización.</span><span class="sxs-lookup"><span data-stu-id="39f81-152">The orchestration engine saves to persistent storage the entire state of a running orchestration instance at various points, so that the instance can later be restored in memory and carried out to completion.</span></span>   
<span data-ttu-id="39f81-153">**El número de puntos de persistencia en una orquestación es uno de los factores clave que influyen en la latencia de mensajes que fluyen a través de orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="39f81-153">**The number of persistence points in an orchestration is one of the key factors influencing the latency of messages flowing through orchestrations**.</span></span> <span data-ttu-id="39f81-154">Cada vez que el motor llega a un punto de persistencia, el estado interno de una orquestación en ejecución se serializa y se guarda en el cuadro de mensajes y esta operación conlleva un costo de latencia.</span><span class="sxs-lookup"><span data-stu-id="39f81-154">Each time the engine hits a persistence point, the internal state of a running orchestration is serialized and saved to the MessageBox and this operation incurs a latency cost.</span></span> <span data-ttu-id="39f81-155">La serialización del estado interno incluye todos los mensajes y las variables que se crea una instancia y no se ha liberado en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="39f81-155">The serialization of the internal state includes all messages and variables instantiated and not yet released in the orchestration.</span></span> <span data-ttu-id="39f81-156">Cuanto mayores sean los mensajes y las variables y cuanto mayor sea el número de ellas, más tiempo tardará para conservar el estado interno de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="39f81-156">The larger the messages and variables and the greater the number of these, the longer it will take to persist the internal state of an orchestration.</span></span> <span data-ttu-id="39f81-157">Un número excesivo de puntos de persistencia puede provocar una degradación significativa del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="39f81-157">An excessive number of persistence points can lead to significant performance degradation.</span></span> <span data-ttu-id="39f81-158">Por este motivo, se recomienda la eliminación de puntos de persistencia innecesarios desde las orquestaciones al reducir el número de ámbitos transaccionales y formas de envío.</span><span class="sxs-lookup"><span data-stu-id="39f81-158">For this reason, we recommend eliminating unnecessary persistence points from orchestrations by reducing the number of transactional scopes and Send shapes.</span></span> <span data-ttu-id="39f81-159">Este enfoque permite reducir la contención en el cuadro de mensajes debido a la orquestación deshidratación y rehidratación, lo que aumenta la escalabilidad global y reduce la latencia de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="39f81-159">This approach allows decreasing the contention on the MessageBox due to orchestration dehydration and rehydration, increasing the overall scalability, and reducing orchestration latency.</span></span>   
<span data-ttu-id="39f81-160">Otra recomendación es mantener siempre el estado interno de una orquestación lo más pequeño posible.</span><span class="sxs-lookup"><span data-stu-id="39f81-160">Another recommendation is to always keep the internal state of an orchestration as small as possible.</span></span> <span data-ttu-id="39f81-161">Esta técnica puede reducir significativamente el tiempo empleado por el motor XLANG serializar, guardar y restaurar el estado interno de una orquestación en el caso de punto de persistencia.</span><span class="sxs-lookup"><span data-stu-id="39f81-161">This technique can significantly reduce the time spent by the XLANG Engine serializing, persisting and restoring the internal state of an orchestration in case of persistence point.</span></span> <span data-ttu-id="39f81-162">Una manera de conseguirlo es crear variables y mensajes lo más tarde posible y liberarlos tan pronto como sea posible; Por ejemplo incluyen ámbitos no transaccionales en las orquestaciones y declare variables y mensajes dentro de estos ámbitos internos en lugar de declarar a ellos en el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="39f81-162">One way to achieve this is to create variables and messages as late as possible and release them as early as possible; for example introduce non transactional scopes inside your orchestrations and declare variables and messages within these inner scopes instead of declaring them at the top-most level.</span></span> <span data-ttu-id="39f81-163">Para obtener más información acerca de cómo minimizar los puntos de persistencia de orquestación, vea los temas siguientes en la documentación de BizTalk Server 2010:</span><span class="sxs-lookup"><span data-stu-id="39f81-163">For more information about minimizing orchestration persistence points, see the following topics in the BizTalk Server  2010 documentation:</span></span>  
  
-   <span data-ttu-id="39f81-164">[Persistencia y el motor de orquestaciones](http://go.microsoft.com/fwlink/?LinkID=155292) (http://go.microsoft.com/fwlink/?LinkID=155292).</span><span class="sxs-lookup"><span data-stu-id="39f81-164">[Persistence and the Orchestration Engine](http://go.microsoft.com/fwlink/?LinkID=155292) (http://go.microsoft.com/fwlink/?LinkID=155292).</span></span>  
  
-   <span data-ttu-id="39f81-165">[Orquestación deshidratación y rehidratación](http://go.microsoft.com/fwlink/?LinkID=155284) (http://go.microsoft.com/fwlink/?LinkID=155292).</span><span class="sxs-lookup"><span data-stu-id="39f81-165">[Orchestration Dehydration and Rehydration](http://go.microsoft.com/fwlink/?LinkID=155284) (http://go.microsoft.com/fwlink/?LinkID=155292).</span></span>  
  
## <a name="guidelines-for-using-promoted-properties-to-access-message-tags-or-attributes-from-an-orchestration"></a><span data-ttu-id="39f81-166">Directrices para utilizar las propiedades promocionan que atributos o etiquetas de mensaje de acceso desde una orquestación</span><span class="sxs-lookup"><span data-stu-id="39f81-166">Guidelines for using promoted properties to access message tags or attributes from an orchestration</span></span>  
 <span data-ttu-id="39f81-167">Si es necesario promocionar propiedades, promocionar solo las propiedades que se usan para el enrutamiento de mensajes, filtros y correlación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="39f81-167">If you do need to promote properties, promote only those properties that are used for message routing, filters, and message correlation.</span></span> <span data-ttu-id="39f81-168">La promoción de cada propiedad requiere el componente de desensamblador (personalizada de sin formato, XML,) para reconocer el tipo de documento y recuperar datos desde el mensaje mediante la expresión XPath de la anotación relativa contenida en el esquema XSD que define el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="39f81-168">The promotion of each property requires the disassembler component (XML, Flat, custom) to recognize the document type and to retrieve data from the message using the XPath expression from the relative annotation contained in the XSD that defines the document type.</span></span> <span data-ttu-id="39f81-169">Además, cada promoción de propiedades hace una llamada independiente del procedimiento almacenado de bts_InsertProperty cuando el agente de mensaje se publica el mensaje en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="39f81-169">In addition, each property promotion causes a separate call of the bts_InsertProperty stored procedure when the Message Agent publishes the message to the MessageBox database.</span></span> <span data-ttu-id="39f81-170">Si una orquestación necesita acceder a un determinado elemento o atributo que contiene un documento XML, utilice una de las técnicas siguientes:</span><span class="sxs-lookup"><span data-stu-id="39f81-170">If an orchestration needs to access a particular element or attribute contained by an XML document, use one of the following techniques:</span></span>  
  
-   <span data-ttu-id="39f81-171">Reduzca el número de propiedades promocionadas y escritos y elimine aquellos que no son estrictamente necesarios.</span><span class="sxs-lookup"><span data-stu-id="39f81-171">Reduce the number of written and promoted properties and eliminate those that are not strictly necessary.</span></span>  
  
-   <span data-ttu-id="39f81-172">Eliminar campos distintivos innecesarios.</span><span class="sxs-lookup"><span data-stu-id="39f81-172">Eliminate unnecessary distinguished fields.</span></span> <span data-ttu-id="39f81-173">Los campos distintivos se escriben las propiedades de contexto y fácilmente que pueden ocupar espacio significativo como su nombre es igual a la expresión XPath que se utiliza para recuperar datos.</span><span class="sxs-lookup"><span data-stu-id="39f81-173">The distinguished fields are written context properties and they can easily occupy significant space as their name is equal to the XPath expression that is used to retrieve data.</span></span> <span data-ttu-id="39f81-174">La propiedad distintivo se define como anotaciones en el esquema XSD que define el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="39f81-174">The distinguished property is defined as annotations in the XSD that defines the document type.</span></span> <span data-ttu-id="39f81-175">El componente de desensamblador utiliza el mismo enfoque adoptado para las propiedades promocionadas y la expresión XPath que define un campo distintivo para buscar dentro del documento entrante.</span><span class="sxs-lookup"><span data-stu-id="39f81-175">The disassembler component uses the same approach adopted for promoted properties and uses the XPath expression that defines a distinguished field to find it within in the incoming document.</span></span> <span data-ttu-id="39f81-176">A continuación, el componente de desensamblador escribe una propiedad en el contexto de donde:</span><span class="sxs-lookup"><span data-stu-id="39f81-176">Then, the disassembler component writes a property in the context where:</span></span>  
  
    -   <span data-ttu-id="39f81-177">**Nombre**: expresión XPath definido en la anotación.</span><span class="sxs-lookup"><span data-stu-id="39f81-177">**Name**: XPath Expression defined in the annotation.</span></span>  
  
    -   <span data-ttu-id="39f81-178">**Valor**: valor del elemento identificado por la expresión XPath dentro de un documento entrante.</span><span class="sxs-lookup"><span data-stu-id="39f81-178">**Value**: Value of the element identified by the XPath expression within an incoming document.</span></span>  
  
     <span data-ttu-id="39f81-179">Las expresiones XPath pueden ser muy largos, especialmente cuando el elemento en cuestión es muy profundo en el esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="39f81-179">The XPath Expressions can be very long, especially when the element in question is very deep in the document schema.</span></span> <span data-ttu-id="39f81-180">Por lo tanto, cuantos más distinguen campos, cuanto mayor sea el tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="39f81-180">So, the more distinguished fields, the larger the context size.</span></span> <span data-ttu-id="39f81-181">Esto afecta a su vez afecta negativamente al rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="39f81-181">This in turn adversely affects the overall performance.</span></span>  
  
-   <span data-ttu-id="39f81-182">Utilice la función de XPath integrada proporcionada por el tiempo de ejecución de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="39f81-182">Use the XPath built-in function provided by the orchestration runtime.</span></span>  
  
-   <span data-ttu-id="39f81-183">Si los mensajes son bastante pequeños (algunos kilobytes) y con formato XML, puede deserializar el mensaje en una instancia de la clase de .NET y trabajar con campos y propiedades públicos.</span><span class="sxs-lookup"><span data-stu-id="39f81-183">If messages are quite small (a few kilobytes) and XML-formatted, you can de-serialize the message into a .NET class instance and work with public fields and properties.</span></span> <span data-ttu-id="39f81-184">Si el mensaje una elaboración complejo (código personalizado, las directivas del motor de reglas de negocios, etc.) debe obtener acceso a datos utilizando las propiedades expuestas por una instancia de una clase .NET es mucho más rápido con expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="39f81-184">If the message needs a complex elaboration (custom code, Business Rule Engine policies, etc.) accessing data using the properties exposed by an instance of a .NET class is much faster using XPath expressions.</span></span> <span data-ttu-id="39f81-185">Cuando haya finalizado la lógica de negocios que invoca la orquestación, se puede serializar el objeto de entidad en un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="39f81-185">When the business logic invoked by the orchestration has completed, the entity object can be serialized back into a BizTalk message.</span></span> <span data-ttu-id="39f81-186">Puede crear clases de .NET de un esquema XML utilizando una de las siguientes herramientas: herramienta XSD (.NET Framework 2.0) o SVCUTIL (.NET Framework 3.0).</span><span class="sxs-lookup"><span data-stu-id="39f81-186">You can create .NET classes from an XML schema using one of the following tools: XSD tool (.NET Framework 2.0) or SVCUTIL (.NET Framework 3.0).</span></span>  
  
-   <span data-ttu-id="39f81-187">Habilitar un componente de aplicación auxiliar desde una orquestación.</span><span class="sxs-lookup"><span data-stu-id="39f81-187">Enable a helper component from an orchestration.</span></span> <span data-ttu-id="39f81-188">Esta técnica tiene la ventaja con respecto a los campos distintivos.</span><span class="sxs-lookup"><span data-stu-id="39f81-188">This technique has an advantage over using distinguished fields.</span></span> <span data-ttu-id="39f81-189">De hecho, una orquestación puede leer el XPath expresión desde un archivo de configuración almacenar (archivo de configuración, el almacén de configuración de SSO, base de datos personalizado etc.), por lo tanto, cuando tiene que cambiar la expresión XPath, no es necesario cambiar y volver a implementar un esquema, que debe hacer para las propiedades promocionadas y d campos de istinguished.</span><span class="sxs-lookup"><span data-stu-id="39f81-189">In fact, an orchestration may read the XPath expression from a config store (config file, SSO Config Store, custom Db, and so on) so, when you have to change the XPath expression, you do not have to change and redeploy a schema, as you should do for promoted properties and distinguished fields.</span></span> <span data-ttu-id="39f81-190">El ejemplo de código siguiente proporciona un ejemplo de un componente de aplicación auxiliar.</span><span class="sxs-lookup"><span data-stu-id="39f81-190">The following code sample provides an example of a helper component.</span></span> <span data-ttu-id="39f81-191">El componente utiliza la clase XPathReader proporcionada por el tiempo de ejecución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="39f81-191">The component uses the XPathReader class that is provided by the BizTalk runtime.</span></span> <span data-ttu-id="39f81-192">Esto permite que el código para leer la secuencia del documento hasta que se encuentra la expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="39f81-192">This allows the code to read through the document stream until the XPath expression is found.</span></span>  
  
```  
#region Copyright  
//===  
//Microsoft Windows Server AppFabric Customer Advisory Team (CAT)   
//  
// This sample is supplemental to the technical guidance published on the community  
// blog.  
//   
// Author: Paolo Salvatori.  
//===  
// Copyright © 2010 Microsoft Corporation. All rights reserved.  
//   
// THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER   
// EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE IMPLIED WARRANTIES OF   
// MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. YOU BEAR THE RISK OF USING IT.  
//===  
#endregion  
#region Using Directives  
using System;  
using System.Collections.Generic;  
using System.IO;  
using System.Xml;  
using System.Linq;  
using System.Text;  
using System.Globalization;  
using Microsoft.XLANGs.BaseTypes;   
using Microsoft.BizTalk.Streaming;  
using Microsoft.BizTalk.XPath;  
#endregion  
namespace Microsoft.AppFabric.CAT.Samples.DuplexMEP.Helpers  
{  
public class XPathHelper  
{  
#region Private Constants   
private const string MessageCannotBeNull = "[XPathReader] The message cannot be null.";  
#endregion  
#region Public Static Methods  
public static string GetValue(XLANGMessage message, int partIndex, string xpath)  
{  
try  
{  
if (message == null)  
{  
throw new ApplicationException(MessageCannotBeNull);  
}  
using (Stream stream = message[partIndex].RetrieveAs(typeof(Stream)) as Stream)  
{  
XmlTextReader xmlTextReader = new XmlTextReader(stream);  
XPathCollection xPathCollection = new XPathCollection();  
XPathReader xPathReader = new XPathReader(xmlTextReader, xPathCollection);  
xPathCollection.Add(xpath);  
while (xPathReader.Read())  
{  
if (xPathReader.HasAttributes)  
{  
for (int i = 0; i < xPathReader.AttributeCount; i++)  
{  
xPathReader.MoveToAttribute(i);  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.GetAttribute(i);  
}  
}  
}  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.ReadString();  
}  
}  
}  
}  
finally  
{  
message.Dispose();  
}  
return string.Empty;  
}  
#endregion  
}  
}  
```  
  
## <a name="minimize-orchestration-complexity-to-improve-performance"></a><span data-ttu-id="39f81-193">Minimizar la complejidad de la orquestación para mejorar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="39f81-193">Minimize orchestration complexity to improve performance</span></span>  
 <span data-ttu-id="39f81-194">La complejidad de las orquestaciones tiene un impacto significativo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="39f81-194">The complexity of orchestrations has a significant impact on performance.</span></span> <span data-ttu-id="39f81-195">A medida que aumenta la complejidad de la orquestación, se reduce el rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="39f81-195">As orchestration complexity increases, overall performance decreases.</span></span> <span data-ttu-id="39f81-196">Orquestaciones pueden usarse en una variedad casi infinita de escenarios, y cada escenario puede implicar orquestaciones de complejidad variable.</span><span class="sxs-lookup"><span data-stu-id="39f81-196">Orchestrations can be used in an almost infinite variety of scenarios, and each scenario might involve orchestrations of varying complexity.</span></span> <span data-ttu-id="39f81-197">Evite orquestaciones complejas cuando sea posible en favor de un enfoque modular.</span><span class="sxs-lookup"><span data-stu-id="39f81-197">Avoid complex orchestrations when possible in favor of a modular approach.</span></span> <span data-ttu-id="39f81-198">En otras palabras, dividir la lógica de negocios en varias orquestaciones reutilizables.</span><span class="sxs-lookup"><span data-stu-id="39f81-198">In other words, split your business logic into multiple, reusable orchestrations.</span></span>  
  
 <span data-ttu-id="39f81-199">Si necesita implementar una orquestación compleja, definir mensajes y variables a los ámbitos internos siempre que sea posible, en lugar de en el nivel raíz.</span><span class="sxs-lookup"><span data-stu-id="39f81-199">If you do need to implement a complex orchestration, define messages and variables into inner scopes whenever possible rather than at the root level.</span></span> <span data-ttu-id="39f81-200">Esta técnica mantiene una superficie menor en la memoria para cada orquestación porque las variables y los mensajes se eliminan cuando el flujo abandona el ámbito en el que se definieron las variables y mensajes.</span><span class="sxs-lookup"><span data-stu-id="39f81-200">This technique maintains a smaller footprint in memory for each orchestration because variables and messages are disposed of when the flow leaves the scope where the variables and messages were defined.</span></span> <span data-ttu-id="39f81-201">Este enfoque es especialmente útil cuando las orquestaciones se guardan en el cuadro de mensajes en puntos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="39f81-201">This approach is particularly beneficial when orchestrations are saved to the MessageBox at persistence points.</span></span>  
  
## <a name="use-the-call-orchestration-shape-versus-the-start-orchestration-shape-to-improve-performance"></a><span data-ttu-id="39f81-202">Utilice la forma orquestación de llamada frente a la forma Iniciar orquestación para mejorar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="39f81-202">Use the Call Orchestration shape versus the Start Orchestration shape to improve performance</span></span>  
 <span data-ttu-id="39f81-203">Evitar la **Iniciar orquestación** y dar forma a usar el **orquestación de llamada** forma que se va a ejecutar una orquestación anidada.</span><span class="sxs-lookup"><span data-stu-id="39f81-203">Avoid the **Start Orchestration** shape and use the **Call Orchestration** shape to execute a nested orchestration.</span></span> <span data-ttu-id="39f81-204">De hecho, el **orquestación de llamada** forma puede utilizarse para llamar a una orquestación que se hace referencia en otro proyecto de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="39f81-204">In fact, The **Call Orchestration** shape can be used to synchronously call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="39f81-205">Este enfoque permite la reutilización de los patrones comunes de flujo de trabajo de orquestación en proyectos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="39f81-205">This approach allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="39f81-206">Cuando se invoca otra orquestación anidada sincrónicamente con la **orquestación de llamada** forma, la orquestación envolvente espera a que la orquestación anidada finalice antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="39f81-206">When you invoke another nested orchestration synchronously with the **Call Orchestration** shape, the enclosing orchestration waits for the nested orchestration to finish before continuing.</span></span> <span data-ttu-id="39f81-207">La orquestación anidada se ejecuta en el mismo subproceso que se ejecuta la orquestación de llamada.</span><span class="sxs-lookup"><span data-stu-id="39f81-207">The nested orchestration is executed on the same thread that runs the calling orchestration.</span></span>  
  
 <span data-ttu-id="39f81-208">El **Iniciar orquestación** forma es similar a la **orquestación de llamada** forma, pero en este caso la orquestación anidada se llama de forma asincrónica: el flujo de control de la llamada orquestación continúa más allá de la invocación, sin esperar a la orquestación invocada finalizar su trabajo.</span><span class="sxs-lookup"><span data-stu-id="39f81-208">The **Start Orchestration** shape is similar to the **Call Orchestration** shape, but in this case the nested orchestration is called in an asynchronous manner: the flow of control in the invoking orchestration proceeds beyond the invocation, without waiting for the invoked orchestration to finish its work.</span></span> <span data-ttu-id="39f81-209">Para implementar esta separación entre el llamador y las orquestaciones llamadas, el **Iniciar orquestación** se implementa a través de la publicación de un mensaje a BizTalk Messagebox.</span><span class="sxs-lookup"><span data-stu-id="39f81-209">In order to implement this decoupling between the caller and the called orchestrations, the **Start Orchestration** is implemented via publication of a message to the BizTalk Messagebox.</span></span> <span data-ttu-id="39f81-210">Este mensaje, a continuación, se consume por una instancia de host de BizTalk en el proceso que ejecuta la orquestación anidada.</span><span class="sxs-lookup"><span data-stu-id="39f81-210">This message is then consumed by an in-process BizTalk host instance which executes the nested orchestration.</span></span> <span data-ttu-id="39f81-211">Cuando sea posible, utilice **orquestación de llamada**, especialmente si la orquestación que realiza la llamada debe esperar para obtener un resultado de la orquestación anidada con el fin de continuar con el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="39f81-211">When possible, use **Call Orchestration**, especially if the calling orchestration needs to wait for a result from the nested orchestration in order to continue processing.</span></span>  <span data-ttu-id="39f81-212">Para obtener más información sobre el uso de la forma orquestación de llamada, vea los temas siguientes en la documentación de BizTalk Server 2010:</span><span class="sxs-lookup"><span data-stu-id="39f81-212">For more information about using the Call Orchestration shape, see the following topics in the BizTalk Server 2010 documentation:</span></span>  
  
-   <span data-ttu-id="39f81-213">[Trabajar con puertos de enlace directo en orquestaciones](http://go.microsoft.com/fwlink/?LinkId=139902) (http://go.microsoft.com/fwlink/?LinkId=139902).</span><span class="sxs-lookup"><span data-stu-id="39f81-213">[Working with Direct Bound Ports in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=139902) (http://go.microsoft.com/fwlink/?LinkId=139902).</span></span>  
  
-   <span data-ttu-id="39f81-214">[Anidar orquestaciones](http://go.microsoft.com/fwlink/?LinkId=139903) (http://go.microsoft.com/fwlink/?LinkId=139903).</span><span class="sxs-lookup"><span data-stu-id="39f81-214">[Nesting Orchestrations](http://go.microsoft.com/fwlink/?LinkId=139903) (http://go.microsoft.com/fwlink/?LinkId=139903).</span></span>  
  
## <a name="use-xmlreader-with-xlangmessage-versus-using-xmlreader-with-xmldocument-to-improve-orchestration-performance"></a><span data-ttu-id="39f81-215">Usar XmlReader con XLANGMessage frente al uso de XmlReader con XmlDocument para mejorar el rendimiento de la orquestación</span><span class="sxs-lookup"><span data-stu-id="39f81-215">Use XmlReader with XLANGMessage versus using XmlReader with XmlDocument to improve orchestration performance</span></span>  
 <span data-ttu-id="39f81-216">Para mejorar el rendimiento de la orquestación para los métodos de .NET que se llama desde una orquestación, utilice XmlReader con XLANGMessage, no XmlDocument.</span><span class="sxs-lookup"><span data-stu-id="39f81-216">To improve orchestration performance for .NET methods called from an orchestration, use XmlReader with XLANGMessage, not XmlDocument.</span></span> <span data-ttu-id="39f81-217">En el ejemplo de código siguiente se ilustra esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="39f81-217">The following code example illustrates this functionality.</span></span>  
  
```csharp  
// As a general rule, use XmlReader with XLANGMessage, not XmlDocument.   
// This is illustrated in the parameter passed into the following code.   
// The XLANG/s compiler doesn't allow a return value of XmlReader   
// so documents must be initially constructed as XmlDocument()  
public static XmlDocument FromMsg(XLANGMessage old)  
{  
    //get at the data  
    XmlDocument ret = new XmlDocument();  
  
    try{  
        XmlReader reader = (XmlReader)old[0].RetrieveAs(typeof(XmlReader));  
        //construct new message from old  
        //read property  
        object msgid = old.GetPropertyValue(typeof(BTS.MessageID));  
    }  
    finally {  
        // Call Dispose on the XLANGMessage object   
        // because the message doesn't belong to the   
        // .NET runtime - it belongs to the Messagebox database   
        old.Dispose();  
    }  
    return ret;  
}  
```  
  
 <span data-ttu-id="39f81-218">Otro método sería crear una clase .NET basada en el esquema.</span><span class="sxs-lookup"><span data-stu-id="39f81-218">Another method would be to create a .NET class based on the schema.</span></span> <span data-ttu-id="39f81-219">Esto consume menos memoria que cargar el documento en un **XmlDocument** objeto, así como proporcionar un acceso sencillo a los elementos de esquema para los desarrolladores de .NET.</span><span class="sxs-lookup"><span data-stu-id="39f81-219">This takes less memory than loading the document into an **XmlDocument** object, as well as providing easy access to the schema elements for .NET developers.</span></span> <span data-ttu-id="39f81-220">Para generar una clase basada en un esquema de BizTalk, puede usar la herramienta xsd.exe incluida con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="39f81-220">To generate a class based on a BizTalk schema, you can use the xsd.exe tool provided with Visual Studio.</span></span> <span data-ttu-id="39f81-221">Por ejemplo, ejecutar **xsd.exe \<schema.xsd\> /classes** con un esquema simple que contiene campos denominados ItemA, ItemB, ItemC, producirá la siguiente clase.</span><span class="sxs-lookup"><span data-stu-id="39f81-221">For example, running **xsd.exe \<schema.xsd\> /classes** against a simple schema containing fields named ItemA, ItemB, ItemC, will produce the following class.</span></span>  
  
```csharp  
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:2.0.50727.1433  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
using System.Xml.Serialization;  
  
//   
// This source code was auto-generated by xsd, Version=2.0.50727.42.  
//  
  
/// <remarks/>  
[System.CodeDom.Compiler.GeneratedCodeAttribute("xsd", "2.0.50727.42")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://Schemas.MySchema")]  
[System.Xml.Serialization.XmlRootAttribute(Namespace="http://Schemas.MySchema", IsNullable=false)]  
public partial class MySchemaRoot {  
  
    private string itemAField;  
  
    private string itemBField;  
  
    private string itemCField;  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemA {  
        get {  
            return this.itemAField;  
        }  
        set {  
            this.itemAField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemB {  
        get {  
            return this.itemBField;  
        }  
        set {  
            this.itemBField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemC {  
        get {  
            return this.itemCField;  
        }  
        set {  
            this.itemCField = value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="39f81-222">Esta clase, a continuación, puede hacer referencia en el ensamblado de .NET para tener acceso a los elementos del mensaje y el objeto devuelto se puede asignar directamente a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="39f81-222">This class can then be referenced in your .NET assembly in order to access the message elements, and the returned object can be directly assigned to a message.</span></span> <span data-ttu-id="39f81-223">El siguiente es un ejemplo del uso de la clase generada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="39f81-223">The following is an example use of the class generated above.</span></span>  
  
```csharp  
public static Root SetValues(Microsoft.XLANGs.BaseTypes.XLANGMessage msg)  
{  
   try  
   {  
   MySchemaRoot rootObj=(MySchemaRoot)msg[0].RetrieveAs(typeof(MySchemaRoot);  
   rootObj.ItemA="value a";  
   rootObj.ItemB="value b";  
   rootObj.ItemC="value c";  
   }  
    finally {  
        msg.Dispose();  
            }  
  
   return rootObj;  
}  
```  
  
 <span data-ttu-id="39f81-224">Esta técnica permite usar un enfoque orientado a objetos al procesar mensajes.</span><span class="sxs-lookup"><span data-stu-id="39f81-224">This technique allows you to use an object-oriented approach when processing messages.</span></span> <span data-ttu-id="39f81-225">Esta técnica se debe utilizar principalmente con mensajes relativamente pequeños.</span><span class="sxs-lookup"><span data-stu-id="39f81-225">This technique should be used primarily with relatively small messages.</span></span> <span data-ttu-id="39f81-226">Esto es porque, aunque esta técnica utiliza mucho menos memoria que al cargar el mensaje en una **XmlDocument** de objeto, el mensaje completo se seguirá cargando en memoria.</span><span class="sxs-lookup"><span data-stu-id="39f81-226">This is because even though this technique uses considerably less memory than when loading the message into an **XmlDocument** object, the entire message is still loaded into memory.</span></span> <span data-ttu-id="39f81-227">Al procesar mensajes más grandes, utilice el **XmlReader** clase para leer los mensajes y la **XmlWriter** clase para escribir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="39f81-227">When processing larger messages, use the **XmlReader** class to read messages and the **XmlWriter** class to write messages.</span></span> <span data-ttu-id="39f81-228">Cuando se usa **XmlReader** y **XmlWriter**, el mensaje se encuentra en un **VirtualStream** objeto.</span><span class="sxs-lookup"><span data-stu-id="39f81-228">When using **XmlReader** and **XmlWriter**, the message is contained in a **VirtualStream** object.</span></span> <span data-ttu-id="39f81-229">Si el tamaño del mensaje supera el valor especificado para **umbral de mensajes de gran tamaño (bytes)** que se expone en la página de configuración de propiedades del grupo de BizTalk, el mensaje se escribe en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="39f81-229">If the message size exceeds the value specified for **Large message threshold (bytes)** that is exposed on the BizTalk Group Properties configuration page, the message is written to the file system.</span></span> <span data-ttu-id="39f81-230">Esto reduce el rendimiento global, pero evita la excepción de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="39f81-230">This decreases overall performance, but avoids out of memory exceptions.</span></span>  
  
## <a name="improve-performance-by-minimizing-the-use-of-logical-ports-bound-to-physical-ports"></a><span data-ttu-id="39f81-231">Mejorar el rendimiento al reducir el uso de puertos lógicos que se enlaza a puertos físicos</span><span class="sxs-lookup"><span data-stu-id="39f81-231">Improve performance by minimizing the use of logical ports bound to physical ports</span></span>  
 <span data-ttu-id="39f81-232">Se puede mejorar el rendimiento al reducir el uso de puertos lógicos que se enlaza a puertos físicos que utilizan los siguientes adaptadores:</span><span class="sxs-lookup"><span data-stu-id="39f81-232">You can increase performance by minimizing the use of logical ports bound to physical ports that use the following adapters:</span></span>  
  
-   <span data-ttu-id="39f81-233">SQL Server, Oracle</span><span class="sxs-lookup"><span data-stu-id="39f81-233">SQL Server, Oracle</span></span>  
  
-   <span data-ttu-id="39f81-234">WSE, HTTP, WCF</span><span class="sxs-lookup"><span data-stu-id="39f81-234">WSE, HTTP, WCF</span></span>  
  
-   <span data-ttu-id="39f81-235">MSMQ, MQSeries</span><span class="sxs-lookup"><span data-stu-id="39f81-235">MSMQ, MQSeries</span></span>  
  
 <span data-ttu-id="39f81-236">En BizTalk Server 2010, enviar y recibir las canalizaciones se pueden invocar directamente desde una orquestación mediante la clase XLANGPipelineManager contenida en el Microsoft.XLANGs.Pipeline.dll.</span><span class="sxs-lookup"><span data-stu-id="39f81-236">In BizTalk Server 2010, send and receive pipelines can be directly invoked from an orchestration using the XLANGPipelineManager class contained in the Microsoft.XLANGs.Pipeline.dll.</span></span> <span data-ttu-id="39f81-237">Por lo tanto, se puede mover el procesamiento de canalizaciones de puertos en orquestaciones; puertos lógicos de una orquestación pueden sustituirse con una forma de expresión, que invoca una instancia de una clase determinada de .NET (por ejemplo, un componente de acceso a datos con ADO.NET).</span><span class="sxs-lookup"><span data-stu-id="39f81-237">Thus, the processing of pipelines can be moved from ports to orchestrations; logical ports in an orchestration can be substituted with an Expression shape, which invokes an instance of a given .NET class (for example, a Data Access component using ADO.NET).</span></span> <span data-ttu-id="39f81-238">Antes de la adopción de esta técnica, debe tener en cuenta que si no utiliza adaptadores y puertos físicos, perderá la capacidad de aprovechar sus funciones, como el procesamiento por lotes, reintentos, configuración declarativa y transportes secundarios.</span><span class="sxs-lookup"><span data-stu-id="39f81-238">Before adopting this technique, you should be aware that if you do not use adapters and physical ports, you lose the ability to leverage their functions, such as batching, retries, declarative configuration, and secondary transports.</span></span>  
  
## <a name="orchestration-design-patterns"></a><span data-ttu-id="39f81-239">Patrones de diseño de orquestación</span><span class="sxs-lookup"><span data-stu-id="39f81-239">Orchestration Design Patterns</span></span>  
 <span data-ttu-id="39f81-240">El Diseñador de orquestaciones permite a los desarrolladores implementar una amplia gama de patrones de integración empresarial.</span><span class="sxs-lookup"><span data-stu-id="39f81-240">The Orchestration Designer allows developers to implement a wide range of enterprise integration patterns.</span></span> <span data-ttu-id="39f81-241">Algunos modelos comunes incluyen el agregador, control de excepciones y compensación, agente de mensajes, dispersión y recopilación y secuenciales y Convoy paralelo.</span><span class="sxs-lookup"><span data-stu-id="39f81-241">Some common patterns include Aggregator, Exception Handling and Compensation, Message Broker, Scatter and Gather, and Sequential and Parallel Convoy.</span></span> <span data-ttu-id="39f81-242">Estos patrones se pueden utilizar para desarrollar soluciones de integración de aplicaciones empresariales (EAI), la arquitectura orientada a servicios (SOA) y la administración de procesos empresariales (BPM) complejas con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="39f81-242">Those patterns can be utilized to develop complex Enterprise Application Integration (EAI), Service-Oriented Architecture (SOA), and Business Process Management (BPM) solutions with BizTalk Server.</span></span> <span data-ttu-id="39f81-243">Para obtener más información sobre los patrones de diseño de orquestación, vea el tema [implementar patrones de diseño en orquestaciones](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.Microsoft.com/fwlink/?) LinkId = 140042) en la documentación de BizTalk Server y [patrones y prácticas recomendadas para la integración de Enterprise](http://go.microsoft.com/fwlink/?LinkId=140043) (http://go.Microsoft.com/fwlink/?) LinkId = 140043).</span><span class="sxs-lookup"><span data-stu-id="39f81-243">For more information about Orchestration Design Patterns, see the topic [Implementing Design Patterns in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) in the BizTalk Server documentation and [Patterns and Best Practices for Enterprise Integration](http://go.microsoft.com/fwlink/?LinkId=140043) (http://go.microsoft.com/fwlink/?LinkId=140043).</span></span>  
  
## <a name="make-appropriate-use-of-net-classes-in-orchestrations-to-maximize-performance"></a><span data-ttu-id="39f81-244">Hacer un uso adecuado de las clases de .NET en orquestaciones para maximizar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="39f81-244">Make appropriate use of .NET classes in orchestrations to maximize performance</span></span>  
 <span data-ttu-id="39f81-245">En general, las clases de .NET Framework que se utiliza dentro de una orquestación pueden dividirse en dos categorías distintas:</span><span class="sxs-lookup"><span data-stu-id="39f81-245">In general, the .NET classes used inside an orchestration can be divided into two distinct categories:</span></span>  
  
-   <span data-ttu-id="39f81-246">**Los ayudantes y servicios -** estas clases proporcionan servicios comunes a las orquestaciones, como el seguimiento, control de errores, el almacenamiento en caché y serialización/deserialización.</span><span class="sxs-lookup"><span data-stu-id="39f81-246">**Helpers and services -** These classes provide common services to orchestrations such as tracing, error handling, caching, and serialization/deserialization.</span></span> <span data-ttu-id="39f81-247">La mayoría de estas clases se puede implementar como las clases estáticas con ningún estado interno y varios métodos estáticos públicos.</span><span class="sxs-lookup"><span data-stu-id="39f81-247">Most of these classes can be implemented as static classes with no internal state and multiple public static methods.</span></span> <span data-ttu-id="39f81-248">Este enfoque evita la creación de varios objetos de la misma clase en orquestaciones diferentes que se ejecutan al mismo tiempo, lo que ayuda a reducir el espacio de trabajo de procesos de host y ahorrar memoria.</span><span class="sxs-lookup"><span data-stu-id="39f81-248">This approach avoids creating multiple objects of the same class in different orchestrations running at the same time, which helps to reduce the working space of host processes and save memory.</span></span> <span data-ttu-id="39f81-249">Una clase que no tiene estada ayuda a reducir el tamaño total del estado interno que se debe serializar y conservan a BizTalk MessageBox cuando una orquestación se deshidratará.</span><span class="sxs-lookup"><span data-stu-id="39f81-249">A class that is stateless helps to reduce the overall size of the internal state that must be serialized and persisted to the BizTalk MessageBox when an orchestration is dehydrated.</span></span>  
  
-   <span data-ttu-id="39f81-250">**Entidades y objetos de negocios -** puede usar estas clases para administrar entidades, como pedidos, elementos del pedido y los clientes.</span><span class="sxs-lookup"><span data-stu-id="39f81-250">**Entities and Business Objects -** You can use these classes to manage entities, such as orders, order items, and customers.</span></span> <span data-ttu-id="39f81-251">Internamente, una orquestación única puede crear y administrar varias instancias del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="39f81-251">A single orchestration can internally create and manage multiple instances of the same type.</span></span> <span data-ttu-id="39f81-252">Estas clases son normalmente con estado y exponen campos públicos o propiedades junto con los métodos para modificar el estado interno del objeto.</span><span class="sxs-lookup"><span data-stu-id="39f81-252">These classes are typically stateful, and expose public fields and/or properties along with methods to modify the internal state of the object.</span></span> <span data-ttu-id="39f81-253">Se pueden crear dinámicamente instancias de estas clases mediante la deserialización de una parte de XLANGMessage en un objeto de .NET mediante el uso de la **XmlSerializer** o **DataContractSerializer** clases o mediante el  **XLANGPart.RetrieveAs** método.</span><span class="sxs-lookup"><span data-stu-id="39f81-253">Instances of these classes can be dynamically created by deserializing an XLANGMessage part into a .NET object by using the **XmlSerializer** or the **DataContractSerializer** classes or by using the **XLANGPart.RetrieveAs** method.</span></span> <span data-ttu-id="39f81-254">Debe estructurar una orquestación mediante ámbitos no transaccionales de tal manera que se crean lo más tarde posible y se liberan en cuanto ya no son necesarios instancias de clases con estado.</span><span class="sxs-lookup"><span data-stu-id="39f81-254">You should structure an orchestration using non-transactional scopes in such a way that instances of stateful classes are created as late as possible and released as soon as they are no longer needed.</span></span> <span data-ttu-id="39f81-255">Este enfoque reduce el espacio de trabajo de procesos de host y reduce el tamaño total del estado interno que se serializa y se conservan en la base de datos de cuadro de mensajes cuando una orquestación es deshidratada.</span><span class="sxs-lookup"><span data-stu-id="39f81-255">This approach reduces the working space of host processes and minimizes the overall size of the internal state that is serialized and persisted to the MessageBox database when an orchestration is dehydrated.</span></span> <span data-ttu-id="39f81-256">Para obtener más información sobre el uso de las orquestaciones de BizTalk Server, vea el artículo [preguntas más frecuentes sobre las orquestaciones de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=116886) (http://go.microsoft.com/fwlink/?LinkID=116886).</span><span class="sxs-lookup"><span data-stu-id="39f81-256">For more information about using orchestrations in BizTalk Server, see the article [FAQ for BizTalk Server Orchestrations](http://go.microsoft.com/fwlink/?LinkID=116886) (http://go.microsoft.com/fwlink/?LinkID=116886).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="39f81-257">Mientras se escribe este artículo para BizTalk Server 2004 y BizTalk Server 2006, los conceptos presentados también se aplican a las orquestaciones de BizTalk Server 2010.</span><span class="sxs-lookup"><span data-stu-id="39f81-257">While this article is written for BizTalk Server 2004 and BizTalk Server 2006, the concepts presented also apply to BizTalk Server 2010 orchestrations.</span></span>  
  
## <a name="orchestration-exception-handler-blocks"></a><span data-ttu-id="39f81-258">Bloques de controlador de excepción de orquestación</span><span class="sxs-lookup"><span data-stu-id="39f81-258">Orchestration Exception Handler Blocks</span></span>  
 <span data-ttu-id="39f81-259">Al utilizar bloques de controlador de excepción de orquestación, incluya todas las formas de orquestación en uno o varios ámbitos (ámbitos no transaccionales siempre que sea posible) y cree al menos los siguientes bloques de controlador de excepción:</span><span class="sxs-lookup"><span data-stu-id="39f81-259">When using Orchestration exception Handler blocks, include all orchestration shapes in one or multiple scopes (non transactional scopes whenever possible) and create at least the following exception handler blocks:</span></span>  
  
-   <span data-ttu-id="39f81-260">Un bloque de controlador de excepciones para controlar un error genérico de System.Exception.</span><span class="sxs-lookup"><span data-stu-id="39f81-260">An exception handler block for handling a generic System.Exception error.</span></span>  
  
-   <span data-ttu-id="39f81-261">Un bloque de controlador de excepciones para controlar una excepción general con el fin de detectar y controlar los posibles errores de no administrados, como excepciones COM.</span><span class="sxs-lookup"><span data-stu-id="39f81-261">An exception handler block for handling a general exception in order to catch and handle possible unmanaged errors, such as COM exceptions.</span></span>  
  
 <span data-ttu-id="39f81-262">Para obtener más información sobre el uso de bloques de control de excepciones de orquestación, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="39f81-262">For more information about using Orchestration exception handling blocks, see the following articles:</span></span>  
  
-   <span data-ttu-id="39f81-263">[Mediante el control de excepciones de BizTalk Server](http://msdn.microsoft.com/library/aa561229.aspx) (http://msdn.microsoft.com/library/aa561229.aspx).</span><span class="sxs-lookup"><span data-stu-id="39f81-263">[Using BizTalk Server Exception Handling](http://msdn.microsoft.com/library/aa561229.aspx) (http://msdn.microsoft.com/library/aa561229.aspx).</span></span>  
  
-   <span data-ttu-id="39f81-264">[Blog de Charles Young, BizTalk Server 2006: El modelo de compensación](http://go.microsoft.com/fwlink/?LinkId=158017) (http://go.microsoft.com/fwlink/?LinkId=158017).</span><span class="sxs-lookup"><span data-stu-id="39f81-264">[Charles Young Blog, BizTalk Server 2006: The Compensation Model](http://go.microsoft.com/fwlink/?LinkId=158017) (http://go.microsoft.com/fwlink/?LinkId=158017).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="39f81-265">Aunque este blog se ha redactado teniendo [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] en mente, los principios descritos en el blog de también se aplican a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="39f81-265">While this blog was written with [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] in mind, the principles described in the blog also apply to BizTalk Server.</span></span>  
  
## <a name="considerations-when-using-maps-in-orchestrations"></a><span data-ttu-id="39f81-266">Consideraciones al usar asignaciones en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="39f81-266">Considerations when using maps in orchestrations</span></span>  
 <span data-ttu-id="39f81-267">Al utilizar asignaciones en orquestaciones, se aplican las consideraciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="39f81-267">The following considerations apply when using maps in orchestrations:</span></span>  
  
-   <span data-ttu-id="39f81-268">Si está usando una asignación para extraer o establecer las propiedades usadas con lógica de negocios en una orquestación, utilice los campos distintivos o propiedades promocionadas.</span><span class="sxs-lookup"><span data-stu-id="39f81-268">If you are using a map to extract or set properties used with business logic in an orchestration, use distinguished fields or promoted properties.</span></span> <span data-ttu-id="39f81-269">Se debe seguir esta práctica porque al extraer o establecer valores con un mapa del documento se ha cargado en la memoria sin embargo al usar campos distintivos o propiedades promocionadas, el motor de orquestaciones obtiene acceso al contexto de mensaje y no se carga el documento en la memoria.</span><span class="sxs-lookup"><span data-stu-id="39f81-269">This practice should be followed because when extracting or setting values with a map the document is loaded into memory however when using distinguished fields or promoted properties, the orchestration engine accesses the message context and does not load the document into memory.</span></span>  
  
-   <span data-ttu-id="39f81-270">Si utiliza una asignación para agregar varios campos a un campo, use campos distintivos o propiedades promocionadas con una variable de orquestación para acumular el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="39f81-270">If you are using a map to aggregate several fields into one field, use distinguished fields or promoted properties with an orchestration variable to accumulate the result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f81-271">Vea también</span><span class="sxs-lookup"><span data-stu-id="39f81-271">See Also</span></span>  
 [<span data-ttu-id="39f81-272">Optimización del rendimiento</span><span class="sxs-lookup"><span data-stu-id="39f81-272">Optimizing Performance</span></span>](../technical-guides/optimizing-performance.md)