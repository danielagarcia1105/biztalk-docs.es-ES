---
title: Optimizar el rendimiento de la orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 437c7325-f037-451a-8dbd-f8d8c8889e20
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 473c6e904def7f58adcb52eb26e46891be9c41d0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971885"
---
# <a name="optimizing-orchestration-performance"></a><span data-ttu-id="1ebf0-102">Optimizar el rendimiento de orquestación</span><span class="sxs-lookup"><span data-stu-id="1ebf0-102">Optimizing Orchestration Performance</span></span>
<span data-ttu-id="1ebf0-103">En este tema se describe los procedimientos recomendados para usar las orquestaciones en soluciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-103">This topic describes best practices for using orchestrations in BizTalk Server solutions.</span></span> <span data-ttu-id="1ebf0-104">Esto incluye recomendaciones para:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-104">This includes recommendations for:</span></span>  
  
-   <span data-ttu-id="1ebf0-105">Reducir la latencia de las soluciones de BizTalk Server que utilizan las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="1ebf0-105">Reducing latency of BizTalk Server solutions that use orchestrations</span></span>  
  
    -   <span data-ttu-id="1ebf0-106">Eliminación de orquestaciones para que sólo los patrones de mensajería</span><span class="sxs-lookup"><span data-stu-id="1ebf0-106">Eliminating orchestrations for messaging only patterns</span></span>  
  
    -   <span data-ttu-id="1ebf0-107">Uso en línea envía desde las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="1ebf0-107">Utilizing inline sends from orchestrations</span></span>  
  
    -   <span data-ttu-id="1ebf0-108">Minimizar los puntos de persistencia de orquestación</span><span class="sxs-lookup"><span data-stu-id="1ebf0-108">Minimizing orchestration persistence points</span></span>  
  
-   <span data-ttu-id="1ebf0-109">Anidación de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="1ebf0-109">Nesting orchestrations</span></span>  
  
-   <span data-ttu-id="1ebf0-110">Patrones de diseño de orquestación</span><span class="sxs-lookup"><span data-stu-id="1ebf0-110">Orchestration design patterns</span></span>  
  
-   <span data-ttu-id="1ebf0-111">Bloques de control de excepciones de orquestación</span><span class="sxs-lookup"><span data-stu-id="1ebf0-111">Orchestration exception handling blocks</span></span>  
  
## <a name="recommendations-for-optimizing-orchestrations-for-low-latency-scenarios"></a><span data-ttu-id="1ebf0-112">Recomendaciones para optimizar las orquestaciones para escenarios de baja latencia</span><span class="sxs-lookup"><span data-stu-id="1ebf0-112">Recommendations for optimizing orchestrations for low latency scenarios</span></span>  
 <span data-ttu-id="1ebf0-113">Las técnicas siguientes pueden usarse para reducir la latencia de las soluciones de BizTalk Server que utilizan las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-113">The following techniques can be used to reduce latency of BizTalk Server solutions that use orchestrations.</span></span>  
  
### <a name="eliminate-orchestrations-for-messaging-only-patterns"></a><span data-ttu-id="1ebf0-114">Eliminar las orquestaciones para que sólo los patrones de mensajería</span><span class="sxs-lookup"><span data-stu-id="1ebf0-114">Eliminate orchestrations for messaging only patterns</span></span>  
 <span data-ttu-id="1ebf0-115">Cuando sea posible minimizar el uso de orquestaciones para aumentar el rendimiento global y reducir la latencia de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-115">When possible minimize the use of orchestrations to increase overall throughput and reduce the latency of business processes.</span></span> <span data-ttu-id="1ebf0-116">Si es necesario ejecutar largo transacciones de ejecución y no es necesario para invocar varios sistemas para cada solicitud, a continuación, considere la posibilidad de eliminar las orquestaciones y mover la lógica de negocios a puertos de envío y recepción para reducir la cantidad total de ida y vuelta a la BizTalkMsgBoxDb y reducir la latencia debido al acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-116">If there is no need to run long running transactions and there is no need to invoke several systems for each request, then consider eliminating orchestrations and moving business logic to Receive and Send Ports to reduce the total amount of roundtrips to the BizTalkMsgBoxDb and decrease the latency due to database access.</span></span> <span data-ttu-id="1ebf0-117">En este caso, implementar canalizaciones personalizadas y volver a usar las clases auxiliares que anteriormente se invocaron desde las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-117">In this case, implement custom pipelines and reuse helper classes that were previously invoked from orchestrations.</span></span> <span data-ttu-id="1ebf0-118">Usar las orquestaciones solo cuando sea estrictamente necesario para implementar patrones de diseño como de dispersión y recopilación o convoyes.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-118">Use orchestrations only when strictly needed to implement design patterns as Scatter and Gather or Convoys.</span></span> <span data-ttu-id="1ebf0-119">Para obtener más información sobre los patrones de diseño de orquestación, vea el tema [implementar patrones de diseño de orquestaciones](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) en la documentación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-119">For more information about Orchestration Design Patterns, see the topic [Implementing Design Patterns in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) in the BizTalk Server documentation.</span></span>  
  
### <a name="use-inline-sends-from-orchestrations-to-accommodate-low-latency-scenarios"></a><span data-ttu-id="1ebf0-120">Usar en línea se envía desde las orquestaciones para dar cabida a escenarios de baja latencia</span><span class="sxs-lookup"><span data-stu-id="1ebf0-120">Use inline sends from orchestrations to accommodate low latency scenarios</span></span>  
 <span data-ttu-id="1ebf0-121">Siempre que sea posible, minimice el uso de las orquestaciones y favorecer patrones únicamente de mensajería para aumentar el rendimiento general y reducir la latencia de los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-121">Whenever possible, minimize the use of orchestrations and favor messaging-only patterns to increase the overall throughput and reduce the latency of the business processes.</span></span> <span data-ttu-id="1ebf0-122">Si no es necesario para las transacciones de larga ejecución y no es necesario para la lógica de negocios invocar varios sistemas, a continuación, considere la posibilidad de mover la lógica de negocios a los puertos de envío y recepción y eliminación del uso de las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-122">If there is no need for long-running transactions and there is no need for business logic to invoke several systems, then consider moving business logic to receive and send Ports and eliminating the use of orchestrations.</span></span> <span data-ttu-id="1ebf0-123">Este enfoque puede implementarse con canalizaciones personalizadas y que volver a usar las clases auxiliares que anteriormente se invocaron desde las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-123">This approach can be implemented with custom pipelines and which reuse the helper classes that were previously invoked from orchestrations.</span></span> <span data-ttu-id="1ebf0-124">Con el fin de lograr un mejor rendimiento en escenarios de baja latencia, puede adoptar uno de los enfoques siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-124">In order to achieve better performance in low latency scenarios, adopt one of the following approaches:</span></span>  
  
-   <span data-ttu-id="1ebf0-125">Eliminar orquestaciones innecesarias y adopte patrones únicamente de mensajería para reducir la cantidad total de ida y vuelta a la base de datos de BizTalk MessageBox.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-125">Eliminate unnecessary orchestrations and adopt messaging-only patterns to reduce the total amount of roundtrips to the BizTalk MessageBox database.</span></span> <span data-ttu-id="1ebf0-126">Este enfoque contempla una latencia baja porque envía insertada omitir el asociado y motor de mensajería de BizTalk sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-126">This approach accommodates low latency because inline sends bypass the BizTalk messaging engine and the associated overhead.</span></span> <span data-ttu-id="1ebf0-127">Se proporciona la funcionalidad de envío de orquestación en línea con BizTalk Server 2006 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-127">Orchestration inline send functionality is provided with BizTalk Server 2006 and later.</span></span>  
  
-   <span data-ttu-id="1ebf0-128">Dentro de orquestaciones, eliminar los puertos lógicos que se enlaza a los puertos físicos y uso en línea se envía en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-128">Inside orchestrations, eliminate logical ports bound to physical ports and use in-line sends in their place.</span></span> <span data-ttu-id="1ebf0-129">Por ejemplo, un envío en línea podría usarse para crear una instancia de una clase de proxy WCF para invocar un servicio Web auxiliar o un componente ADO.NET para tener acceso a una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-129">For example, an inline send could be used to create an instance of a  WCF proxy class to invoke a downstream Web service or an ADO.NET component to access a SQL Server database.</span></span> <span data-ttu-id="1ebf0-130">En el diagrama siguiente, se realiza un envío en línea cuando la orquestación crea una instancia de un componente empresarial, que internamente hace uso de WCF objeto de proxy para llamar directamente a un servicio Web auxiliar:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-130">In the following diagram, an inline send is performed when the orchestration instantiates a business component, which internally makes use of a WCF  proxy object to directly invoke a downstream Web service:</span></span>  
  
     <span data-ttu-id="1ebf0-131">![Representación de envío en línea de orquestación de BizTalk](../technical-guides/media/inlinesend.gif "InlineSend")</span><span class="sxs-lookup"><span data-stu-id="1ebf0-131">![Depiction of BizTalk Orchestration Inline Send](../technical-guides/media/inlinesend.gif "InlineSend")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ebf0-132">Aunque el uso de los envíos en línea desde las orquestaciones reducirá significativamente la latencia, existen limitaciones en este enfoque.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-132">Although using inline sends from orchestrations will significantly reduce latency, there are limitations to this approach.</span></span> <span data-ttu-id="1ebf0-133">Dado que los envíos en línea omiten el motor de mensajería de BizTalk, no está disponible la siguiente funcionalidad proporcionada con el motor de mensajería:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-133">Because inline sends bypass the BizTalk messaging engine, the following functionality provided with the messaging engine is not available:</span></span>  
> 
> - <span data-ttu-id="1ebf0-134">Canalizaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-134">Transactional pipelines</span></span>  
>   -   <span data-ttu-id="1ebf0-135">Canalizaciones recuperables</span><span class="sxs-lookup"><span data-stu-id="1ebf0-135">Recoverable pipelines</span></span>  
>   -   <span data-ttu-id="1ebf0-136">Canalizaciones que llaman a la API de interceptor de BAM</span><span class="sxs-lookup"><span data-stu-id="1ebf0-136">Pipelines that call the BAM interceptor API</span></span>  
>   -   <span data-ttu-id="1ebf0-137">Compatibilidad del adaptador de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1ebf0-137">BizTalk Server adapter support</span></span>  
>   -   <span data-ttu-id="1ebf0-138">Procesar por lotes</span><span class="sxs-lookup"><span data-stu-id="1ebf0-138">Batching</span></span>  
>   -   <span data-ttu-id="1ebf0-139">Reintentos</span><span class="sxs-lookup"><span data-stu-id="1ebf0-139">Retries</span></span>  
>   -   <span data-ttu-id="1ebf0-140">Conjunto de correlaciones de inicialización</span><span class="sxs-lookup"><span data-stu-id="1ebf0-140">Correlation set initialization</span></span>  
>   -   <span data-ttu-id="1ebf0-141">Configuración declarativa</span><span class="sxs-lookup"><span data-stu-id="1ebf0-141">Declarative configuration</span></span>  
>   -   <span data-ttu-id="1ebf0-142">Transportes secundarios</span><span class="sxs-lookup"><span data-stu-id="1ebf0-142">Secondary transports</span></span>  
>   -   <span data-ttu-id="1ebf0-143">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="1ebf0-143">Tracking</span></span>  
>   -   <span data-ttu-id="1ebf0-144">Uso declarativo de BAM</span><span class="sxs-lookup"><span data-stu-id="1ebf0-144">Declarative use of BAM</span></span>  
  
 <span data-ttu-id="1ebf0-145">Para obtener más información sobre los tipos de canalizaciones que no se puede ejecutar desde una orquestación, consulte la sección "Restricciones" del tema [cómo usar expresiones para ejecutar canalizaciones](http://go.microsoft.com/fwlink/?LinkId=158008) (http://go.microsoft.com/fwlink/?LinkId=158008) en el servidor BizTalk Server documentación de 2010.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-145">For more information about the types of pipelines that cannot be executed from within an orchestration, see the “Restrictions” section of the topic [How to Use Expressions to Execute Pipelines](http://go.microsoft.com/fwlink/?LinkId=158008) (http://go.microsoft.com/fwlink/?LinkId=158008) in the BizTalk Server 2010 documentation.</span></span>  
  
### <a name="optimize-orchestration-latency-by-reducing-the-number-of-persistence-points-if-possible"></a><span data-ttu-id="1ebf0-146">Optimizar la latencia de la orquestación al reducir el número de puntos de persistencia, si es posible</span><span class="sxs-lookup"><span data-stu-id="1ebf0-146">Optimize orchestration latency by reducing the number of persistence points, if possible</span></span>  
 <span data-ttu-id="1ebf0-147">Un ámbito de la orquestación sólo debe estar marcada como "transaccional de larga ejecución" Si desea utilizar tiempos de espera de compensación o ámbito.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-147">An orchestration scope only needs to be marked as “long-running transactional” if you want to use compensation or scope timeouts.</span></span> <span data-ttu-id="1ebf0-148">Un ámbito transaccional de larga ejecución hace que un punto de persistencia adicional al final del ámbito, por lo que debe evitarse cuando no necesite usar la compensación o tiempos de espera de ámbito.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-148">A long-running transactional scope causes an extra persistence point at the end of the scope, so they should be avoided when you don’t need to use compensation or scope timeouts.</span></span> <span data-ttu-id="1ebf0-149">Un ámbito atómico hace que un punto de persistencia al final del ámbito, pero también garantiza que no se produzca ningún punto de persistencia dentro del ámbito atómico.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-149">An atomic scope causes a persistence point at the end of the scope, but also guarantees that no persistence points will occur inside the atomic scope.</span></span> <span data-ttu-id="1ebf0-150">Este efecto secundario de ninguna persistencia dentro del ámbito a veces puede utilizarse para su beneficio a los puntos de persistencia de lote (al realizar varias envía, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-150">This side-effect of no persistence inside the scope can sometimes be used to your advantage to batch persistence points (when doing multiple sends, for example).</span></span> <span data-ttu-id="1ebf0-151">En general, sin embargo, se recomienda evitar los ámbitos atómicos si es posible.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-151">In general, though, we recommend avoiding atomic scopes if possible.</span></span> <span data-ttu-id="1ebf0-152">El motor de orquestaciones guarda en almacenamiento persistente todo el estado de una instancia de orquestación de ejecución en varios puntos, para que la instancia más adelante se puede restaurar en la memoria y lleva a cabo hasta su finalización.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-152">The orchestration engine saves to persistent storage the entire state of a running orchestration instance at various points, so that the instance can later be restored in memory and carried out to completion.</span></span>   
<span data-ttu-id="1ebf0-153">**El número de puntos de persistencia en una orquestación es uno de los factores claves que influyen en la latencia de mensajes que fluyen a través de orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-153">**The number of persistence points in an orchestration is one of the key factors influencing the latency of messages flowing through orchestrations**.</span></span> <span data-ttu-id="1ebf0-154">Cada vez que el motor alcanza un punto de persistencia, se serializa el estado interno de una orquestación en ejecución y se guarda en el cuadro de mensajes y esta operación implica un costo de latencia.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-154">Each time the engine hits a persistence point, the internal state of a running orchestration is serialized and saved to the MessageBox and this operation incurs a latency cost.</span></span> <span data-ttu-id="1ebf0-155">La serialización del estado interno incluye todos los mensajes y variables que crea una instancia y aún no se han publicado en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-155">The serialization of the internal state includes all messages and variables instantiated and not yet released in the orchestration.</span></span> <span data-ttu-id="1ebf0-156">Cuanto mayor sea el mensajes y las variables y mayor es el número de estos, cuanto más tiempo se tardará en conservar el estado interno de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-156">The larger the messages and variables and the greater the number of these, the longer it will take to persist the internal state of an orchestration.</span></span> <span data-ttu-id="1ebf0-157">Un número excesivo de puntos de persistencia puede provocar una degradación del rendimiento significativa.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-157">An excessive number of persistence points can lead to significant performance degradation.</span></span> <span data-ttu-id="1ebf0-158">Por este motivo, se recomienda la eliminación de puntos de persistencia innecesarios desde las orquestaciones al reducir el número de ámbitos transaccionales y formas envío.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-158">For this reason, we recommend eliminating unnecessary persistence points from orchestrations by reducing the number of transactional scopes and Send shapes.</span></span> <span data-ttu-id="1ebf0-159">Este enfoque permite reducir la contención en el cuadro de mensajes debido a la deshidratación de orquestaciones y rehidratación, aumentar la escalabilidad global y reducir la latencia de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-159">This approach allows decreasing the contention on the MessageBox due to orchestration dehydration and rehydration, increasing the overall scalability, and reducing orchestration latency.</span></span>   
<span data-ttu-id="1ebf0-160">Otra recomendación es mantener siempre el estado interno de una orquestación tan pequeña como sea posible.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-160">Another recommendation is to always keep the internal state of an orchestration as small as possible.</span></span> <span data-ttu-id="1ebf0-161">Esta técnica puede reducir significativamente el tiempo empleado por el motor XLANG serializar, guardar y restaurar el estado interno de una orquestación en el caso de punto de persistencia.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-161">This technique can significantly reduce the time spent by the XLANG Engine serializing, persisting and restoring the internal state of an orchestration in case of persistence point.</span></span> <span data-ttu-id="1ebf0-162">Una manera de conseguirlo es crear variables y mensajes tan tarde como sea posible y liberarlos tan pronto como sea posible; Por ejemplo, introducir los ámbitos no transaccionales dentro de las orquestaciones y declarar variables y mensajes dentro de estos ámbitos internos en lugar de declarar a ellos en el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-162">One way to achieve this is to create variables and messages as late as possible and release them as early as possible; for example introduce non transactional scopes inside your orchestrations and declare variables and messages within these inner scopes instead of declaring them at the top-most level.</span></span> <span data-ttu-id="1ebf0-163">Para obtener más información acerca de cómo minimizar los puntos de persistencia de orquestación, vea los temas siguientes en la documentación de BizTalk Server 2010:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-163">For more information about minimizing orchestration persistence points, see the following topics in the BizTalk Server  2010 documentation:</span></span>  
  
-   <span data-ttu-id="1ebf0-164">[Persistencia y el motor de orquestaciones](http://go.microsoft.com/fwlink/?LinkID=155292) (http://go.microsoft.com/fwlink/?LinkID=155292).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-164">[Persistence and the Orchestration Engine](http://go.microsoft.com/fwlink/?LinkID=155292) (http://go.microsoft.com/fwlink/?LinkID=155292).</span></span>  
  
-   <span data-ttu-id="1ebf0-165">[Orquestación deshidratación y rehidratación](http://go.microsoft.com/fwlink/?LinkID=155284) (http://go.microsoft.com/fwlink/?LinkID=155292).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-165">[Orchestration Dehydration and Rehydration](http://go.microsoft.com/fwlink/?LinkID=155284) (http://go.microsoft.com/fwlink/?LinkID=155292).</span></span>  
  
## <a name="guidelines-for-using-promoted-properties-to-access-message-tags-or-attributes-from-an-orchestration"></a><span data-ttu-id="1ebf0-166">Directrices para usar promocionan propiedades, atributos o las etiquetas de mensaje de acceso desde una orquestación</span><span class="sxs-lookup"><span data-stu-id="1ebf0-166">Guidelines for using promoted properties to access message tags or attributes from an orchestration</span></span>  
 <span data-ttu-id="1ebf0-167">Si es necesario promocionar propiedades, promocionar solo las propiedades que se usan para el enrutamiento de mensajes, filtros y correlación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-167">If you do need to promote properties, promote only those properties that are used for message routing, filters, and message correlation.</span></span> <span data-ttu-id="1ebf0-168">La promoción de cada propiedad requiere el componente de desensamblador (personalizada de formato, XML,) para reconocer el tipo de documento y recuperar datos desde el mensaje mediante la expresión XPath de la anotación relativa contenida en el esquema XSD que define el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-168">The promotion of each property requires the disassembler component (XML, Flat, custom) to recognize the document type and to retrieve data from the message using the XPath expression from the relative annotation contained in the XSD that defines the document type.</span></span> <span data-ttu-id="1ebf0-169">Además, cada promoción de propiedades hace una llamada independiente del procedimiento almacenado de bts_InsertProperty cuando el agente de mensaje se publica el mensaje en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-169">In addition, each property promotion causes a separate call of the bts_InsertProperty stored procedure when the Message Agent publishes the message to the MessageBox database.</span></span> <span data-ttu-id="1ebf0-170">Si una orquestación necesita tener acceso a un elemento o atributo concreto contenidos en un documento XML, utilice una de las técnicas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-170">If an orchestration needs to access a particular element or attribute contained by an XML document, use one of the following techniques:</span></span>  
  
- <span data-ttu-id="1ebf0-171">Reduzca el número de propiedades promocionadas y escritos y eliminar aquellas que no son estrictamente necesarios.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-171">Reduce the number of written and promoted properties and eliminate those that are not strictly necessary.</span></span>  
  
- <span data-ttu-id="1ebf0-172">Eliminar campos distintivos innecesarios.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-172">Eliminate unnecessary distinguished fields.</span></span> <span data-ttu-id="1ebf0-173">Los campos distintivos se escriben las propiedades de contexto y fácilmente que pueden ocupar espacio significativo como su nombre es igual a la expresión XPath que se usa para recuperar datos.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-173">The distinguished fields are written context properties and they can easily occupy significant space as their name is equal to the XPath expression that is used to retrieve data.</span></span> <span data-ttu-id="1ebf0-174">La propiedad distintivo se define como anotaciones en el esquema XSD que define el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-174">The distinguished property is defined as annotations in the XSD that defines the document type.</span></span> <span data-ttu-id="1ebf0-175">El componente de desensamblador usa el mismo enfoque adoptado para las propiedades promocionadas y la expresión XPath que define un campo distintivo para buscarlo en el documento entrante.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-175">The disassembler component uses the same approach adopted for promoted properties and uses the XPath expression that defines a distinguished field to find it within in the incoming document.</span></span> <span data-ttu-id="1ebf0-176">A continuación, el componente de desensamblador escribe una propiedad en el contexto donde:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-176">Then, the disassembler component writes a property in the context where:</span></span>  
  
  - <span data-ttu-id="1ebf0-177">**Nombre**: expresión XPath definida en la anotación.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-177">**Name**: XPath Expression defined in the annotation.</span></span>  
  
  - <span data-ttu-id="1ebf0-178">**Valor**: valor del elemento identificado por la expresión XPath dentro de un documento entrante.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-178">**Value**: Value of the element identified by the XPath expression within an incoming document.</span></span>  
  
    <span data-ttu-id="1ebf0-179">Las expresiones XPath pueden ser muy largos, especialmente cuando el elemento en cuestión es muy profundo en el esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-179">The XPath Expressions can be very long, especially when the element in question is very deep in the document schema.</span></span> <span data-ttu-id="1ebf0-180">Por lo que más distinguen los campos, cuanto mayor sea el tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-180">So, the more distinguished fields, the larger the context size.</span></span> <span data-ttu-id="1ebf0-181">Esto afecta negativamente a su vez el rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-181">This in turn adversely affects the overall performance.</span></span>  
  
- <span data-ttu-id="1ebf0-182">Use la función integrada XPath proporcionada por el tiempo de ejecución de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-182">Use the XPath built-in function provided by the orchestration runtime.</span></span>  
  
- <span data-ttu-id="1ebf0-183">Si los mensajes son bastante pequeños (unos pocos kilobytes) y con formato XML, puede deserializar el mensaje en una instancia de la clase de .NET y trabajar con campos públicos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-183">If messages are quite small (a few kilobytes) and XML-formatted, you can de-serialize the message into a .NET class instance and work with public fields and properties.</span></span> <span data-ttu-id="1ebf0-184">Si el mensaje una elaboración complejo (código personalizado, las directivas del motor de reglas de negocio, etc.) debe tener acceso a datos mediante las propiedades expuestas por una instancia de una clase .NET es mucho más rápido con expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-184">If the message needs a complex elaboration (custom code, Business Rule Engine policies, etc.) accessing data using the properties exposed by an instance of a .NET class is much faster using XPath expressions.</span></span> <span data-ttu-id="1ebf0-185">Cuando haya finalizado la lógica de negocios invocada por la orquestación, se puede serializar el objeto de entidad en un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-185">When the business logic invoked by the orchestration has completed, the entity object can be serialized back into a BizTalk message.</span></span> <span data-ttu-id="1ebf0-186">Puede crear clases de .NET desde un esquema XML utilizando una de las siguientes herramientas: herramienta XSD (.NET Framework 2.0) o SVCUTIL (.NET Framework 3.0).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-186">You can create .NET classes from an XML schema using one of the following tools: XSD tool (.NET Framework 2.0) or SVCUTIL (.NET Framework 3.0).</span></span>  
  
- <span data-ttu-id="1ebf0-187">Habilitar un componente de aplicación auxiliar desde una orquestación.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-187">Enable a helper component from an orchestration.</span></span> <span data-ttu-id="1ebf0-188">Esta técnica tiene la ventaja con respecto a los campos distintivos.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-188">This technique has an advantage over using distinguished fields.</span></span> <span data-ttu-id="1ebf0-189">De hecho, una orquestación puede leer el XPath expresión desde un archivo de configuración almacenar (archivo de configuración, SSO Config Store, base de datos personalizado etc.), por lo tanto, cuando se tiene que cambiar la expresión XPath, no es necesario cambiar y volver a implementar un esquema, que debe hacer para las propiedades promocionadas y d istinguished campos.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-189">In fact, an orchestration may read the XPath expression from a config store (config file, SSO Config Store, custom Db, and so on) so, when you have to change the XPath expression, you do not have to change and redeploy a schema, as you should do for promoted properties and distinguished fields.</span></span> <span data-ttu-id="1ebf0-190">Ejemplo de código siguiente proporciona un ejemplo de un componente de aplicación auxiliar.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-190">The following code sample provides an example of a helper component.</span></span> <span data-ttu-id="1ebf0-191">El componente utiliza la clase XPathReader proporcionada por el tiempo de ejecución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-191">The component uses the XPathReader class that is provided by the BizTalk runtime.</span></span> <span data-ttu-id="1ebf0-192">Esto permite al código que leerá la secuencia de documentos hasta que se encuentra la expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-192">This allows the code to read through the document stream until the XPath expression is found.</span></span>  
  
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
  
## <a name="minimize-orchestration-complexity-to-improve-performance"></a><span data-ttu-id="1ebf0-193">Minimizar la complejidad de la orquestación para mejorar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="1ebf0-193">Minimize orchestration complexity to improve performance</span></span>  
 <span data-ttu-id="1ebf0-194">La complejidad de las orquestaciones tiene un impacto significativo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-194">The complexity of orchestrations has a significant impact on performance.</span></span> <span data-ttu-id="1ebf0-195">A medida que aumenta la complejidad de la orquestación, se reduce el rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-195">As orchestration complexity increases, overall performance decreases.</span></span> <span data-ttu-id="1ebf0-196">Las orquestaciones se pueden usar en una variedad casi infinita de escenarios, y cada escenario puede implicar las orquestaciones de complejidad variable.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-196">Orchestrations can be used in an almost infinite variety of scenarios, and each scenario might involve orchestrations of varying complexity.</span></span> <span data-ttu-id="1ebf0-197">Evite las orquestaciones complejas cuando sea posible en favor de un enfoque modular.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-197">Avoid complex orchestrations when possible in favor of a modular approach.</span></span> <span data-ttu-id="1ebf0-198">En otras palabras, dividir la lógica de negocios en varias orquestaciones reutilizables.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-198">In other words, split your business logic into multiple, reusable orchestrations.</span></span>  
  
 <span data-ttu-id="1ebf0-199">Si es necesario implementar una orquestación compleja, definir mensajes y variables en los ámbitos internos siempre que sea posible en lugar de en el nivel raíz.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-199">If you do need to implement a complex orchestration, define messages and variables into inner scopes whenever possible rather than at the root level.</span></span> <span data-ttu-id="1ebf0-200">Esta técnica mantiene una superficie menor en la memoria para cada orquestación porque las variables y los mensajes se eliminan cuando el flujo sale del ámbito en el que se definieron las variables y mensajes.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-200">This technique maintains a smaller footprint in memory for each orchestration because variables and messages are disposed of when the flow leaves the scope where the variables and messages were defined.</span></span> <span data-ttu-id="1ebf0-201">Este enfoque resulta especialmente útil cuando las orquestaciones se guardan en el cuadro de mensajes en puntos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-201">This approach is particularly beneficial when orchestrations are saved to the MessageBox at persistence points.</span></span>  
  
## <a name="use-the-call-orchestration-shape-versus-the-start-orchestration-shape-to-improve-performance"></a><span data-ttu-id="1ebf0-202">Utilice la forma de orquestación de llamada frente a la forma Iniciar orquestación para mejorar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="1ebf0-202">Use the Call Orchestration shape versus the Start Orchestration shape to improve performance</span></span>  
 <span data-ttu-id="1ebf0-203">Evitar la **Iniciar orquestación** y dar forma a utilizar el **orquestación de llamada** forma para ejecutar una orquestación anidada.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-203">Avoid the **Start Orchestration** shape and use the **Call Orchestration** shape to execute a nested orchestration.</span></span> <span data-ttu-id="1ebf0-204">De hecho, el **orquestación de llamada** forma puede usarse para llamar sincrónicamente a una orquestación que se hace referencia en otro proyecto.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-204">In fact, The **Call Orchestration** shape can be used to synchronously call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="1ebf0-205">Este enfoque permite la reutilización de los patrones comunes de flujo de trabajo de orquestación en proyectos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-205">This approach allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="1ebf0-206">Cuando se invoca otra orquestación anidada de forma sincrónica con el **orquestación de llamada** forma, la orquestación envolvente espera a que la orquestación anidada finalice antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-206">When you invoke another nested orchestration synchronously with the **Call Orchestration** shape, the enclosing orchestration waits for the nested orchestration to finish before continuing.</span></span> <span data-ttu-id="1ebf0-207">La orquestación anidada se ejecuta en el mismo subproceso que se ejecuta la orquestación de llamada.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-207">The nested orchestration is executed on the same thread that runs the calling orchestration.</span></span>  
  
 <span data-ttu-id="1ebf0-208">El **Iniciar orquestación** forma es similar a la **orquestación de llamada** forma, pero en este caso la orquestación anidada se denomina de forma asincrónica: el flujo de control en la invocación orquestación continúa más allá de la invocación, sin esperar a la orquestación invocada termine.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-208">The **Start Orchestration** shape is similar to the **Call Orchestration** shape, but in this case the nested orchestration is called in an asynchronous manner: the flow of control in the invoking orchestration proceeds beyond the invocation, without waiting for the invoked orchestration to finish its work.</span></span> <span data-ttu-id="1ebf0-209">Para implementar esta separación entre el llamador y las orquestaciones llamadas, el **Iniciar orquestación** se implementa a través de la publicación de un mensaje a BizTalk Messagebox.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-209">In order to implement this decoupling between the caller and the called orchestrations, the **Start Orchestration** is implemented via publication of a message to the BizTalk Messagebox.</span></span> <span data-ttu-id="1ebf0-210">Este mensaje, a continuación, se consume por una instancia de host de BizTalk en el proceso que ejecuta la orquestación anidada.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-210">This message is then consumed by an in-process BizTalk host instance which executes the nested orchestration.</span></span> <span data-ttu-id="1ebf0-211">Cuando sea posible, use **orquestación de llamada**, especialmente si la orquestación de llamada debe esperar un resultado de la orquestación anidada con el fin de continuar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-211">When possible, use **Call Orchestration**, especially if the calling orchestration needs to wait for a result from the nested orchestration in order to continue processing.</span></span>  <span data-ttu-id="1ebf0-212">Para obtener más información sobre el uso de la forma orquestación de llamada, vea los temas siguientes en la documentación de BizTalk Server 2010:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-212">For more information about using the Call Orchestration shape, see the following topics in the BizTalk Server 2010 documentation:</span></span>  
  
-   <span data-ttu-id="1ebf0-213">[Trabajar con puertos de enlace directo en orquestaciones](http://go.microsoft.com/fwlink/?LinkId=139902) (http://go.microsoft.com/fwlink/?LinkId=139902).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-213">[Working with Direct Bound Ports in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=139902) (http://go.microsoft.com/fwlink/?LinkId=139902).</span></span>  
  
-   <span data-ttu-id="1ebf0-214">[Anidar orquestaciones](http://go.microsoft.com/fwlink/?LinkId=139903) (http://go.microsoft.com/fwlink/?LinkId=139903).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-214">[Nesting Orchestrations](http://go.microsoft.com/fwlink/?LinkId=139903) (http://go.microsoft.com/fwlink/?LinkId=139903).</span></span>  
  
## <a name="use-xmlreader-with-xlangmessage-versus-using-xmlreader-with-xmldocument-to-improve-orchestration-performance"></a><span data-ttu-id="1ebf0-215">Uso de XmlReader con XLANGMessage frente al uso de XmlReader con XmlDocument para mejorar el rendimiento de la orquestación</span><span class="sxs-lookup"><span data-stu-id="1ebf0-215">Use XmlReader with XLANGMessage versus using XmlReader with XmlDocument to improve orchestration performance</span></span>  
 <span data-ttu-id="1ebf0-216">Para mejorar el rendimiento de las orquestaciones para los métodos de .NET que se llama desde una orquestación, utilice XmlReader con XLANGMessage, no XmlDocument.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-216">To improve orchestration performance for .NET methods called from an orchestration, use XmlReader with XLANGMessage, not XmlDocument.</span></span> <span data-ttu-id="1ebf0-217">En el ejemplo de código siguiente se ilustra esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-217">The following code example illustrates this functionality.</span></span>  
  
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
  
 <span data-ttu-id="1ebf0-218">Otro método sería crear una clase .NET en función del esquema.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-218">Another method would be to create a .NET class based on the schema.</span></span> <span data-ttu-id="1ebf0-219">Este proceso tarda menos memoria que carga el documento en un **XmlDocument** objeto, así como proporcionar un acceso sencillo a los elementos de esquema para los desarrolladores de .NET.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-219">This takes less memory than loading the document into an **XmlDocument** object, as well as providing easy access to the schema elements for .NET developers.</span></span> <span data-ttu-id="1ebf0-220">Para generar una clase basada en un esquema de BizTalk, puede usar la herramienta xsd.exe incluida con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-220">To generate a class based on a BizTalk schema, you can use the xsd.exe tool provided with Visual Studio.</span></span> <span data-ttu-id="1ebf0-221">Por ejemplo, ejecutar **xsd.exe \<schema.xsd\> /classes** contra un esquema simple que contiene campos denominados ItemA, ItemB, ItemC, generará la siguiente clase.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-221">For example, running **xsd.exe \<schema.xsd\> /classes** against a simple schema containing fields named ItemA, ItemB, ItemC, will produce the following class.</span></span>  
  
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
  
 <span data-ttu-id="1ebf0-222">Esta clase, a continuación, se puede hacer referencia en el ensamblado de .NET para tener acceso a los elementos del mensaje y el objeto devuelto se puede asignar directamente a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-222">This class can then be referenced in your .NET assembly in order to access the message elements, and the returned object can be directly assigned to a message.</span></span> <span data-ttu-id="1ebf0-223">El siguiente es un ejemplo del uso de la clase generada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-223">The following is an example use of the class generated above.</span></span>  
  
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
  
 <span data-ttu-id="1ebf0-224">Esta técnica permite usar un enfoque orientado al procesar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-224">This technique allows you to use an object-oriented approach when processing messages.</span></span> <span data-ttu-id="1ebf0-225">Esta técnica debe usarse principalmente con mensajes relativamente pequeños.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-225">This technique should be used primarily with relatively small messages.</span></span> <span data-ttu-id="1ebf0-226">Esto es porque, aunque esta técnica usa considerablemente menos memoria que al cargar el mensaje en una **XmlDocument** objeto, el mensaje completo se siga estando cargado en memoria.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-226">This is because even though this technique uses considerably less memory than when loading the message into an **XmlDocument** object, the entire message is still loaded into memory.</span></span> <span data-ttu-id="1ebf0-227">Al procesar los mensajes más grandes, utilice el **XmlReader** clase para leer mensajes y el **XmlWriter** clase para escribir mensajes.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-227">When processing larger messages, use the **XmlReader** class to read messages and the **XmlWriter** class to write messages.</span></span> <span data-ttu-id="1ebf0-228">Cuando se usa **XmlReader** y **XmlWriter**, el mensaje está contenido en un **VirtualStream** objeto.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-228">When using **XmlReader** and **XmlWriter**, the message is contained in a **VirtualStream** object.</span></span> <span data-ttu-id="1ebf0-229">Si el tamaño del mensaje supera el valor especificado para **umbral de mensajes grandes (bytes)** que se expone en la página de configuración de propiedades del grupo de BizTalk, el mensaje se escribe en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-229">If the message size exceeds the value specified for **Large message threshold (bytes)** that is exposed on the BizTalk Group Properties configuration page, the message is written to the file system.</span></span> <span data-ttu-id="1ebf0-230">Esto disminuye el rendimiento global, pero evita las excepciones de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-230">This decreases overall performance, but avoids out of memory exceptions.</span></span>  
  
## <a name="improve-performance-by-minimizing-the-use-of-logical-ports-bound-to-physical-ports"></a><span data-ttu-id="1ebf0-231">Mejorar el rendimiento, ya que minimiza el uso de puertos lógicos que se enlaza a los puertos físicos</span><span class="sxs-lookup"><span data-stu-id="1ebf0-231">Improve performance by minimizing the use of logical ports bound to physical ports</span></span>  
 <span data-ttu-id="1ebf0-232">Puede aumentar el rendimiento, ya que minimiza el uso de puertos lógicos que se enlaza a los puertos físicos que utilizan los siguientes adaptadores:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-232">You can increase performance by minimizing the use of logical ports bound to physical ports that use the following adapters:</span></span>  
  
- <span data-ttu-id="1ebf0-233">SQL Server, Oracle</span><span class="sxs-lookup"><span data-stu-id="1ebf0-233">SQL Server, Oracle</span></span>  
  
- <span data-ttu-id="1ebf0-234">WSE, HTTP, WCF</span><span class="sxs-lookup"><span data-stu-id="1ebf0-234">WSE, HTTP, WCF</span></span>  
  
- <span data-ttu-id="1ebf0-235">MSMQ, MQSeries</span><span class="sxs-lookup"><span data-stu-id="1ebf0-235">MSMQ, MQSeries</span></span>  
  
  <span data-ttu-id="1ebf0-236">En BizTalk Server 2010, enviar y recibir las canalizaciones se pueden invocar directamente desde una orquestación mediante la clase XLANGPipelineManager contenida en el Microsoft.XLANGs.Pipeline.dll.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-236">In BizTalk Server 2010, send and receive pipelines can be directly invoked from an orchestration using the XLANGPipelineManager class contained in the Microsoft.XLANGs.Pipeline.dll.</span></span> <span data-ttu-id="1ebf0-237">Por lo tanto, se puede mover el procesamiento de canalizaciones de puertos en orquestaciones; puertos lógicos de una orquestación pueden sustituirse con una forma de expresión, que llama a una instancia de una clase determinada de .NET (por ejemplo, un componente de acceso a datos mediante ADO.NET).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-237">Thus, the processing of pipelines can be moved from ports to orchestrations; logical ports in an orchestration can be substituted with an Expression shape, which invokes an instance of a given .NET class (for example, a Data Access component using ADO.NET).</span></span> <span data-ttu-id="1ebf0-238">Antes de adoptar esta técnica, debe tener en cuenta que si no utiliza adaptadores y puertos físicos, perder la capacidad de aprovechar sus funciones, como el procesamiento por lotes, reintentos, configuración declarativa y transportes secundarios.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-238">Before adopting this technique, you should be aware that if you do not use adapters and physical ports, you lose the ability to leverage their functions, such as batching, retries, declarative configuration, and secondary transports.</span></span>  
  
## <a name="orchestration-design-patterns"></a><span data-ttu-id="1ebf0-239">Patrones de diseño de orquestación</span><span class="sxs-lookup"><span data-stu-id="1ebf0-239">Orchestration Design Patterns</span></span>  
 <span data-ttu-id="1ebf0-240">El Diseñador de orquestaciones permite a los desarrolladores implementar una amplia variedad de patrones de integración empresarial.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-240">The Orchestration Designer allows developers to implement a wide range of enterprise integration patterns.</span></span> <span data-ttu-id="1ebf0-241">Algunos modelos comunes incluyen el agregador, control de excepciones y compensación, agente de mensajes, dispersión y recopilación y secuencial y Convoy paralelo.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-241">Some common patterns include Aggregator, Exception Handling and Compensation, Message Broker, Scatter and Gather, and Sequential and Parallel Convoy.</span></span> <span data-ttu-id="1ebf0-242">Estos patrones se pueden usar para desarrollar soluciones complejas de administración de procesos empresariales (BPM), la arquitectura orientada a servicios (SOA) y Enterprise Application Integration (EAI) con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-242">Those patterns can be utilized to develop complex Enterprise Application Integration (EAI), Service-Oriented Architecture (SOA), and Business Process Management (BPM) solutions with BizTalk Server.</span></span> <span data-ttu-id="1ebf0-243">Para obtener más información sobre los patrones de diseño de orquestación, vea el tema [implementar patrones de diseño de orquestaciones](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) en la documentación de BizTalk Server y [patrones y procedimientos recomendados para Enterprise Integration Pack](http://go.microsoft.com/fwlink/?LinkId=140043) (http://go.microsoft.com/fwlink/?LinkId=140043).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-243">For more information about Orchestration Design Patterns, see the topic [Implementing Design Patterns in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) in the BizTalk Server documentation and [Patterns and Best Practices for Enterprise Integration](http://go.microsoft.com/fwlink/?LinkId=140043) (http://go.microsoft.com/fwlink/?LinkId=140043).</span></span>  
  
## <a name="make-appropriate-use-of-net-classes-in-orchestrations-to-maximize-performance"></a><span data-ttu-id="1ebf0-244">Hacer un uso adecuado de clases de .NET en orquestaciones para maximizar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="1ebf0-244">Make appropriate use of .NET classes in orchestrations to maximize performance</span></span>  
 <span data-ttu-id="1ebf0-245">En general, las clases de .NET que se usa dentro de una orquestación pueden dividirse en dos categorías distintas:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-245">In general, the .NET classes used inside an orchestration can be divided into two distinct categories:</span></span>  
  
-   <span data-ttu-id="1ebf0-246">**Las aplicaciones auxiliares y servicios -** estas clases proporcionan servicios comunes a las orquestaciones, como el seguimiento, control de errores, almacenamiento en caché y serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-246">**Helpers and services -** These classes provide common services to orchestrations such as tracing, error handling, caching, and serialization/deserialization.</span></span> <span data-ttu-id="1ebf0-247">La mayoría de estas clases se puede implementar como clases estáticas con ningún estado interno y varios métodos estáticos públicos.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-247">Most of these classes can be implemented as static classes with no internal state and multiple public static methods.</span></span> <span data-ttu-id="1ebf0-248">Este enfoque evita la creación de varios objetos de la misma clase en orquestaciones diferentes que se ejecutan al mismo tiempo, lo que ayuda a reducir el espacio de trabajo de procesos de host y ahorrar memoria.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-248">This approach avoids creating multiple objects of the same class in different orchestrations running at the same time, which helps to reduce the working space of host processes and save memory.</span></span> <span data-ttu-id="1ebf0-249">Una clase que no tiene estada ayuda a reducir el tamaño total del estado interno que se debe serializar y almacena BizTalk MessageBox cuando una orquestación se deshidratará.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-249">A class that is stateless helps to reduce the overall size of the internal state that must be serialized and persisted to the BizTalk MessageBox when an orchestration is dehydrated.</span></span>  
  
-   <span data-ttu-id="1ebf0-250">**Las entidades y objetos de negocios -** puede utilizar estas clases para administrar entidades, como pedidos, elementos pedidos y clientes.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-250">**Entities and Business Objects -** You can use these classes to manage entities, such as orders, order items, and customers.</span></span> <span data-ttu-id="1ebf0-251">Internamente, una orquestación única puede crear y administrar varias instancias del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-251">A single orchestration can internally create and manage multiple instances of the same type.</span></span> <span data-ttu-id="1ebf0-252">Estas clases son normalmente con estado y exponen campos públicos o propiedades junto con los métodos para modificar el estado interno del objeto.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-252">These classes are typically stateful, and expose public fields and/or properties along with methods to modify the internal state of the object.</span></span> <span data-ttu-id="1ebf0-253">Instancias de estas clases se pueden crear dinámicamente mediante la deserialización de una parte de XLANGMessage en un objeto .NET mediante el uso de la **XmlSerializer** o **DataContractSerializer** clases o bien utilizando el  **XLANGPart.RetrieveAs** método.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-253">Instances of these classes can be dynamically created by deserializing an XLANGMessage part into a .NET object by using the **XmlSerializer** or the **DataContractSerializer** classes or by using the **XLANGPart.RetrieveAs** method.</span></span> <span data-ttu-id="1ebf0-254">Debe estructurar una orquestación mediante ámbitos no transaccionales de tal manera que las instancias de clases con estado se crean en tiempo de ejecución como sea posible y se liberan en cuanto ya no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-254">You should structure an orchestration using non-transactional scopes in such a way that instances of stateful classes are created as late as possible and released as soon as they are no longer needed.</span></span> <span data-ttu-id="1ebf0-255">Este enfoque reduce el espacio de trabajo de procesos de host y minimiza el tamaño total del estado interno que se serializa y se conservan en la base de datos de cuadro de mensajes cuando se deshidrata una orquestación.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-255">This approach reduces the working space of host processes and minimizes the overall size of the internal state that is serialized and persisted to the MessageBox database when an orchestration is dehydrated.</span></span> <span data-ttu-id="1ebf0-256">Para obtener más información acerca de cómo utilizar orquestaciones de BizTalk Server, consulte el artículo [preguntas más frecuentes sobre las orquestaciones de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=116886) (http://go.microsoft.com/fwlink/?LinkID=116886).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-256">For more information about using orchestrations in BizTalk Server, see the article [FAQ for BizTalk Server Orchestrations](http://go.microsoft.com/fwlink/?LinkID=116886) (http://go.microsoft.com/fwlink/?LinkID=116886).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1ebf0-257">Aunque este artículo se escribió para BizTalk Server 2004 y BizTalk Server 2006, los conceptos presentados también se aplican a las orquestaciones de BizTalk Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-257">While this article is written for BizTalk Server 2004 and BizTalk Server 2006, the concepts presented also apply to BizTalk Server 2010 orchestrations.</span></span>  
  
## <a name="orchestration-exception-handler-blocks"></a><span data-ttu-id="1ebf0-258">Bloques de controlador de excepciones de orquestación</span><span class="sxs-lookup"><span data-stu-id="1ebf0-258">Orchestration Exception Handler Blocks</span></span>  
 <span data-ttu-id="1ebf0-259">Al utilizar bloques de controlador de excepciones de orquestación, incluir todas las formas de orquestación en uno o varios ámbitos (ámbitos no transaccionales siempre que sea posible) y cree al menos los siguientes bloques de controlador de excepción:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-259">When using Orchestration exception Handler blocks, include all orchestration shapes in one or multiple scopes (non transactional scopes whenever possible) and create at least the following exception handler blocks:</span></span>  
  
- <span data-ttu-id="1ebf0-260">Un bloque de controlador de excepción para controlar un error genérico de System.Exception.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-260">An exception handler block for handling a generic System.Exception error.</span></span>  
  
- <span data-ttu-id="1ebf0-261">Un bloque de controlador de excepción para controlar una excepción general con el fin de detectar y controlar los posibles errores de no administrados, como las excepciones de COM.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-261">An exception handler block for handling a general exception in order to catch and handle possible unmanaged errors, such as COM exceptions.</span></span>  
  
  <span data-ttu-id="1ebf0-262">Para obtener más información sobre el uso de bloques de control de excepciones de orquestación, consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-262">For more information about using Orchestration exception handling blocks, see the following articles:</span></span>  
  
- <span data-ttu-id="1ebf0-263">[Mediante el control de excepciones de BizTalk Server](http://msdn.microsoft.com/library/aa561229.aspx) (http://msdn.microsoft.com/library/aa561229.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-263">[Using BizTalk Server Exception Handling](http://msdn.microsoft.com/library/aa561229.aspx) (http://msdn.microsoft.com/library/aa561229.aspx).</span></span>  
  
- <span data-ttu-id="1ebf0-264">[Blog de Young Charles, BizTalk Server 2006: El modelo de compensación](http://go.microsoft.com/fwlink/?LinkId=158017) (http://go.microsoft.com/fwlink/?LinkId=158017).</span><span class="sxs-lookup"><span data-stu-id="1ebf0-264">[Charles Young Blog, BizTalk Server 2006: The Compensation Model](http://go.microsoft.com/fwlink/?LinkId=158017) (http://go.microsoft.com/fwlink/?LinkId=158017).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="1ebf0-265">Aunque esta entrada de blog se ha redactado teniendo [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] en mente, los principios descritos en el blog también se aplican a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-265">While this blog was written with [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] in mind, the principles described in the blog also apply to BizTalk Server.</span></span>  
  
## <a name="considerations-when-using-maps-in-orchestrations"></a><span data-ttu-id="1ebf0-266">Consideraciones al usar asignaciones en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="1ebf0-266">Considerations when using maps in orchestrations</span></span>  
 <span data-ttu-id="1ebf0-267">Las siguientes consideraciones se aplican al uso de asignaciones en orquestaciones:</span><span class="sxs-lookup"><span data-stu-id="1ebf0-267">The following considerations apply when using maps in orchestrations:</span></span>  
  
-   <span data-ttu-id="1ebf0-268">Si está usando una asignación para extraer o establecer las propiedades usadas con lógica de negocios en una orquestación, utilice los campos distintivos o propiedades promocionadas.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-268">If you are using a map to extract or set properties used with business logic in an orchestration, use distinguished fields or promoted properties.</span></span> <span data-ttu-id="1ebf0-269">Se debe seguir esta práctica porque al extraer o establecer valores con un mapa del documento se carga en memoria pero al usar campos distintivos o propiedades promocionadas, el motor de orquestaciones obtiene acceso al contexto de mensaje y no se carga el documento en la memoria.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-269">This practice should be followed because when extracting or setting values with a map the document is loaded into memory however when using distinguished fields or promoted properties, the orchestration engine accesses the message context and does not load the document into memory.</span></span>  
  
-   <span data-ttu-id="1ebf0-270">Si utiliza una asignación para agregar varios campos a un campo, use campos distintivos o propiedades promocionadas con una variable de orquestación para acumular el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1ebf0-270">If you are using a map to aggregate several fields into one field, use distinguished fields or promoted properties with an orchestration variable to accumulate the result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ebf0-271">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ebf0-271">See Also</span></span>  
 [<span data-ttu-id="1ebf0-272">Optimización del rendimiento</span><span class="sxs-lookup"><span data-stu-id="1ebf0-272">Optimizing Performance</span></span>](../technical-guides/optimizing-performance.md)