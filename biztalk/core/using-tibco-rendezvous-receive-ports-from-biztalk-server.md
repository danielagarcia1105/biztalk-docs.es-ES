---
title: "Con TIBCO Rendezvous puertos de recepción de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive ports, using from BizTalk Server
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8e0999362844570bb56cfbc488e5fd5775e286
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a><span data-ttu-id="abc81-102">Uso de puertos de recepción TIBCO Rendezvous desde BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="abc81-102">Using TIBCO Rendezvous Receive Ports from BizTalk Server</span></span>
<span data-ttu-id="abc81-103">Para usar un puerto de recepción, puede proporcionar un esquema a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="abc81-103">To use a receive port, you can provide a schema to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for the incoming messages.</span></span> <span data-ttu-id="abc81-104">Un puerto de recepción se configura para escuchar un determinado conjunto de nombres de asunto.</span><span class="sxs-lookup"><span data-stu-id="abc81-104">A receive port is configured to listen for a particular set of subject names.</span></span> <span data-ttu-id="abc81-105">Usa un nombre de asunto con caracteres comodín opcionales para coincidir con varios nombres de asunto.</span><span class="sxs-lookup"><span data-stu-id="abc81-105">It uses a subject name with optional wildcard characters to match multiple subject names.</span></span> <span data-ttu-id="abc81-106">Defina diferentes operaciones de puerto en la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para cada posible asunto que coincida con la cadena dada.</span><span class="sxs-lookup"><span data-stu-id="abc81-106">You define different port operations in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for each possible subject that matches the given string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abc81-107">El Adaptador admite escenarios tanto de mensajería como de orquestación.</span><span class="sxs-lookup"><span data-stu-id="abc81-107">The Adapter supports both orchestration and messaging scenarios.</span></span>  
  
## <a name="defining-schemas"></a><span data-ttu-id="abc81-108">Definición de esquemas</span><span class="sxs-lookup"><span data-stu-id="abc81-108">Defining Schemas</span></span>  
 <span data-ttu-id="abc81-109">Por ejemplo, si el puerto está configurado para escuchar el nombre del sujeto, **existencias. MERCADO. ÍNDICES. >** ('**>**' es un carácter comodín que significa cualquier cosa a la derecha), sería válido definir operaciones para nombres de asunto como **existencias. MERCADO. ÍNDICES. NYSE. SP500**, **existencias. MERCADO. ÍNDICES. TSX.TSX60**, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="abc81-109">For example, if the port is configured to listen to the subject name, **STOCK.MARKET.INDICES.>** ('**>**' is a wildcard character that means anything else to the right), it would be valid to define operations for subject names such as **STOCK.MARKET.INDICES.NYSE.SP500**, **STOCK.MARKET.INDICES.TSX.TSX60**, and so on.</span></span> <span data-ttu-id="abc81-110">El adaptador genera mensajes usando la estrategia descrita en [Data Type Mapping para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)y genera el nombre del elemento raíz y espacios de nombres basado en la escucha del firmante nombre y un mensaje recibido asunto nombres respectivamente.</span><span class="sxs-lookup"><span data-stu-id="abc81-110">The adapter generates messages using the strategy described in [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md), and generates the root element name and namespaces based on the listen subject name and received message subject names respectively.</span></span>  
  
 <span data-ttu-id="abc81-111">En el ejemplo anterior, el adaptador genera un mensaje similar a este para el evento SP500:</span><span class="sxs-lookup"><span data-stu-id="abc81-111">In the previous example, the adapter generates a message that looks like this for the SP500 event:</span></span>  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 <span data-ttu-id="abc81-112">Debe definir un esquema que usa las mismas convenciones.</span><span class="sxs-lookup"><span data-stu-id="abc81-112">You must define a schema that uses the same conventions.</span></span> <span data-ttu-id="abc81-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc81-113">For example:</span></span>  
  
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
  
 <span data-ttu-id="abc81-114">Tenga en cuenta el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName** anotación.</span><span class="sxs-lookup"><span data-stu-id="abc81-114">Note the use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**recordInfo/rootTypeName** annotation.</span></span> <span data-ttu-id="abc81-115">Esto es para indicar a la integración de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk que use dicho nombre para los tipos de .NET Framework generados, en lugar del nombre que contiene puntos.</span><span class="sxs-lookup"><span data-stu-id="abc81-115">This is to instruct the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk integration to use that name for the generated .NET Framework types, instead of the name that contains dots.</span></span> <span data-ttu-id="abc81-116">Puede especificar cualquier cosa.</span><span class="sxs-lookup"><span data-stu-id="abc81-116">You can specify anything.</span></span> <span data-ttu-id="abc81-117">En los ejemplos, los puntos se reemplazan por caracteres de subrayado.</span><span class="sxs-lookup"><span data-stu-id="abc81-117">In the examples, the dots are replaced with underscores.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abc81-118">Los puntos dan lugar a que las herramientas de desarrollo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generen nombres no válidos.</span><span class="sxs-lookup"><span data-stu-id="abc81-118">The dots cause invalid names to be generated by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development tools.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abc81-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="abc81-119">See Also</span></span>  
 <span data-ttu-id="abc81-120">[Asignación de tipos de datos para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="abc81-120">[Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="abc81-121">Controladores de recepción de creación TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="abc81-121">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)