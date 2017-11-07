---
title: "Esquemas de recepción y procesar los eventos con el adaptador de TIBCO Rendezvous | Documentos de Microsoft"
description: "Trabajar con esquemas de TIBCO Rendezvous en el lado de recepción y procesamiento de eventos con el adaptador de BizTalk para TIBCO Rendezvous en BizTalk"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbbae69dc1b7df1f5675442dde544a444cec02fb
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a><span data-ttu-id="b2521-103">Uso de puertos de recepción TIBCO Rendezvous desde BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b2521-103">Using TIBCO Rendezvous Receive Ports from BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="b2521-104">Información general</span><span class="sxs-lookup"><span data-stu-id="b2521-104">Overview</span></span>
<span data-ttu-id="b2521-105">Para usar un puerto de recepción, puede proporcionar un esquema a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="b2521-105">To use a receive port, you can provide a schema to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for the incoming messages.</span></span> <span data-ttu-id="b2521-106">Un puerto de recepción se configura para escuchar un determinado conjunto de nombres de asunto.</span><span class="sxs-lookup"><span data-stu-id="b2521-106">A receive port is configured to listen for a particular set of subject names.</span></span> <span data-ttu-id="b2521-107">Usa un nombre de asunto con caracteres comodín opcionales para coincidir con varios nombres de asunto.</span><span class="sxs-lookup"><span data-stu-id="b2521-107">It uses a subject name with optional wildcard characters to match multiple subject names.</span></span> <span data-ttu-id="b2521-108">Defina diferentes operaciones de puerto en la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para cada posible asunto que coincida con la cadena dada.</span><span class="sxs-lookup"><span data-stu-id="b2521-108">You define different port operations in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for each possible subject that matches the given string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2521-109">El adaptador admite escenarios de mensajería y orquestación.</span><span class="sxs-lookup"><span data-stu-id="b2521-109">The adapter supports both orchestration and messaging scenarios.</span></span>  
  
## <a name="define-schemas"></a><span data-ttu-id="b2521-110">Definir esquemas</span><span class="sxs-lookup"><span data-stu-id="b2521-110">Define schemas</span></span>  
 <span data-ttu-id="b2521-111">Por ejemplo, si el puerto está configurado para escuchar el nombre del sujeto, **existencias. MERCADO. ÍNDICES. >** ('**>**' es un carácter comodín que significa cualquier cosa a la derecha), sería válido definir operaciones para nombres de asunto como **existencias. MERCADO. ÍNDICES. NYSE. SP500**, **existencias. MERCADO. ÍNDICES. TSX.TSX60**, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="b2521-111">For example, if the port is configured to listen to the subject name, **STOCK.MARKET.INDICES.>** ('**>**' is a wildcard character that means anything else to the right), it would be valid to define operations for subject names such as **STOCK.MARKET.INDICES.NYSE.SP500**, **STOCK.MARKET.INDICES.TSX.TSX60**, and so on.</span></span> <span data-ttu-id="b2521-112">El adaptador genera mensajes usando la estrategia descrita en [Data Type Mapping para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)y genera el nombre del elemento raíz y espacios de nombres basado en la escucha del firmante nombre y un mensaje recibido asunto nombres respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b2521-112">The adapter generates messages using the strategy described in [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md), and generates the root element name and namespaces based on the listen subject name and received message subject names respectively.</span></span>  
  
 <span data-ttu-id="b2521-113">En el ejemplo anterior, el adaptador genera un mensaje que es similar al siguiente para el evento SP500:</span><span class="sxs-lookup"><span data-stu-id="b2521-113">In the previous example, the adapter generates a message that looks like the following for the SP500 event:</span></span>  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 <span data-ttu-id="b2521-114">Debe definir un esquema que usa las mismas convenciones.</span><span class="sxs-lookup"><span data-stu-id="b2521-114">You must define a schema that uses the same conventions.</span></span> <span data-ttu-id="b2521-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b2521-115">For example:</span></span>  
  
```  
<xsd:schema  
targetNamespace='   
  
http://schemas.microsoft.com/TibcoRendezvous/Types/STOCK.MARKET.INDICES.N  
YSE.GTWILDCARD'  
xmlns:xsd=' http://www.w3.org/2001/XMLSchema'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types'>  
xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
<xsd:element name='STOCK.MARKET.INDICES.NYSE.SP500'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_NYSE_SP500" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<SP500 message definitions goes here>  
</xsd:complexType>  
<xsd:element name='STOCK.MARKET.INDICES.TSX.TSX60'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_TSX_TSX60" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<TSX60 message definitions goes here>  
</xsd:complexType>  
  
```  
  
 <span data-ttu-id="b2521-116">Tenga en cuenta el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName** anotación.</span><span class="sxs-lookup"><span data-stu-id="b2521-116">Note the use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**recordInfo/rootTypeName** annotation.</span></span> <span data-ttu-id="b2521-117">Esto es para indicar a la integración de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk que use dicho nombre para los tipos de .NET Framework generados, en lugar del nombre que contiene puntos.</span><span class="sxs-lookup"><span data-stu-id="b2521-117">This is to instruct the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk integration to use that name for the generated .NET Framework types, instead of the name that contains dots.</span></span> <span data-ttu-id="b2521-118">Puede especificar cualquier cosa.</span><span class="sxs-lookup"><span data-stu-id="b2521-118">You can specify anything.</span></span> <span data-ttu-id="b2521-119">En los ejemplos, los puntos se reemplazan por caracteres de subrayado.</span><span class="sxs-lookup"><span data-stu-id="b2521-119">In the examples, the dots are replaced with underscores.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2521-120">Los puntos dan lugar a que las herramientas de desarrollo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generen nombres no válidos.</span><span class="sxs-lookup"><span data-stu-id="b2521-120">The dots cause invalid names to be generated by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development tools.</span></span>  

## <a name="event-processing"></a><span data-ttu-id="b2521-121">Procesamiento de eventos</span><span class="sxs-lookup"><span data-stu-id="b2521-121">Event processing</span></span>
<span data-ttu-id="b2521-122">El adaptador de Microsoft BizTalk para TIBCO Rendezvous distribuye eventos de una cola en varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="b2521-122">Microsoft BizTalk Adapter for TIBCO Rendezvous dispatches events from a queue on multiple threads.</span></span> <span data-ttu-id="b2521-123">Ubicación de recepción de un servidor BizTalk Server está asociado a una cola de eventos de TIBCO Rendezvous y su grupo de subprocesos de distribución.</span><span class="sxs-lookup"><span data-stu-id="b2521-123">A BizTalk Server receive location is associated with one TIBCO Rendezvous event queue, and its pool of dispatcher threads.</span></span>  
  
### <a name="memory-use-and-errors"></a><span data-ttu-id="b2521-124">Uso de memoria y errores</span><span class="sxs-lookup"><span data-stu-id="b2521-124">Memory Use and Errors</span></span>  
 <span data-ttu-id="b2521-125">Al procesar eventos, el adaptador vigila los recursos usados.</span><span class="sxs-lookup"><span data-stu-id="b2521-125">While processing events, the adapter keeps an eye on used resources.</span></span> <span data-ttu-id="b2521-126">Si el uso de memoria supera el umbral de marca de agua superior, el adaptador deja de distribuir eventos hasta que llega al consumo de memoria de la marca de agua inferior.</span><span class="sxs-lookup"><span data-stu-id="b2521-126">If memory use goes above the high-watermark, the adapter stops dispatching events until it reaches the low-watermark memory consumption.</span></span> <span data-ttu-id="b2521-127">Tenga en cuenta que, debido a esto, podrían perderse mensajes de TIBCO Rendezvous para mensajes no certificados (un consumidor de TIBCO RV tiene 60 segundos para quitar mensajes de una cola).</span><span class="sxs-lookup"><span data-stu-id="b2521-127">Note that this might result in TIBCO Rendezvous messages being missed for non certified messages (a TIBCO RV consumer has 60 seconds to remove messages from a queue).</span></span> <span data-ttu-id="b2521-128">Esta pérdida de datos se notifica como un error.</span><span class="sxs-lookup"><span data-stu-id="b2521-128">This data loss is reported as an error.</span></span> <span data-ttu-id="b2521-129">Si el adaptador recibe un mensaje NO_MEMORY de aviso del sistema de TIBCO Rendezvous, significa que ya se han perdido mensajes.</span><span class="sxs-lookup"><span data-stu-id="b2521-129">If the adapter receives a TIBCO Rendezvous system advisory NO_MEMORY message, messages have already been lost.</span></span>  
  
 <span data-ttu-id="b2521-130">El Adaptador de BizTalk para TIBCO Rendezvous mantiene un estado y ejecuta las tareas de diferente forma basándose en dicho estado.</span><span class="sxs-lookup"><span data-stu-id="b2521-130">BizTalk Adapter for TIBCO Rendezvous maintains a state, and it executes tasks differently based on that state.</span></span> <span data-ttu-id="b2521-131">Si el Motor de mensajes de BizTalk notifica un error y el adaptador está configurado para ser una escucha certificada, notificará el error a TIBCO Rendezvous de modo que pueda reenviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b2521-131">If the BizTalk Message Engine reports an error, and the adapter is configured to be a certified listener, it reports the error to TIBCO Rendezvous so that it can resubmit the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2521-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2521-132">See Also</span></span>  
 <span data-ttu-id="b2521-133">[Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="b2521-133">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 <span data-ttu-id="b2521-134">[Asignación de tipos de datos para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="b2521-134">[Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="b2521-135">Creación de controladores de recepción de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="b2521-135">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)