---
title: Arquitectura de BizTalk Adapter para PeopleSoft Enterprise | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, XML messages
- architecture
- XML, messages
- XML, validating
ms.assetid: f246e974-a082-430c-ad15-23a5e597738b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 377e49af3a20302b92a4214959b534c9d0949a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="0c4ea-102">Arquitectura del adaptador de BizTalk para PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="0c4ea-102">Architecture of BizTalk Adapter for PeopleSoft Enterprise</span></span>
<span data-ttu-id="0c4ea-103">Durante el funcionamiento básico del adaptador de Microsoft BizTalk para PeopleSoft Enterprise, el adaptador recibe un mensaje XML de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-103">During the basic operation of Microsoft BizTalk Adapter for PeopleSoft Enterprise, the adapter receives an XML message from BizTalk Server.</span></span> <span data-ttu-id="0c4ea-104">Incluye el mensaje XML en un sobre SOAP.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-104">It encloses the XML message in a SOAP envelope.</span></span> <span data-ttu-id="0c4ea-105">El adaptador de BizTalk para PeopleSoft Enterprise reenvía las solicitudes SOAP al servidor.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-105">BizTalk Adapter for PeopleSoft Enterprise forwards the SOAP requests to the server.</span></span> <span data-ttu-id="0c4ea-106">El adaptador se comunica con el sistema PeopleSoft mediante las clases psjoa de PeopleSoft, que conectan a este sistema mediante el protocolo de transacción Jolt.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-106">The adapter communicates with the PeopleSoft system using the PeopleSoft psjoa classes, which connect to the PeopleSoft system through Jolt Transaction Protocol.</span></span> <span data-ttu-id="0c4ea-107">El sistema PeopleSoft recibe la solicitud y ejecuta la lógica empresarial.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-107">The PeopleSoft system receives the request and executes the business logic.</span></span> <span data-ttu-id="0c4ea-108">La respuesta se devuelve a través de un proceso similar.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-108">The reply is sent back through a similar process.</span></span>  
  
 ![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")  
<span data-ttu-id="0c4ea-109">Arquitectura del adaptador</span><span class="sxs-lookup"><span data-stu-id="0c4ea-109">Adapter Architecture</span></span>  
  
## <a name="peoplesoft-component-interface-methods"></a><span data-ttu-id="0c4ea-110">Métodos de interfaces de componentes de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="0c4ea-110">PeopleSoft Component Interface Methods</span></span>  
 <span data-ttu-id="0c4ea-111">Las API básicas proporcionadas por la interfaz de componente de PeopleSoft son de una naturaleza de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-111">The basic APIs that are provided by the PeopleSoft component interface are low-level in nature.</span></span> <span data-ttu-id="0c4ea-112">El cliente requiere múltiples invocaciones de estos API.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-112">The client requires multiple invocations of these APIs.</span></span> <span data-ttu-id="0c4ea-113">Por ejemplo, para obtener la propiedad de una instancia de un componente de interfaz, el cliente necesita una o dos llamadas para establecer los valores clave, seguidas de una llamada del método Get de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-113">For example, to obtain the property of an instance of a component interface, the client needs one or more calls to set the key values followed by a low-level Get method call.</span></span> <span data-ttu-id="0c4ea-114">A continuación, debe enviar varias llamadas para obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-114">It must then send multiple calls to get the properties.</span></span> <span data-ttu-id="0c4ea-115">Con el adaptador de BizTalk para PeopleSoft Enterprise, se proporciona un nuevo conjunto de métodos estándar (Get, Create, Find y Update), de modo que el cliente solo debe realizar una única llamada para obtener el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-115">With BizTalk Adapter for PeopleSoft Enterprise, a new set of standard methods (Get, Create, Find, and Update) are provided in such a way that the client is required to make a single call to accomplish the same result.</span></span> <span data-ttu-id="0c4ea-116">Para ello, se deja que el adaptador de BizTalk para PeopleSoft Enterprise realice varias llamadas de parte del cliente.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-116">You do this by having BizTalk Adapter for PeopleSoft Enterprise perform multiple calls on behalf of the client.</span></span> <span data-ttu-id="0c4ea-117">Para obtener más información acerca de los métodos, vea [métodos de interfaz de componente de apéndice A:](../core/appendix-a-component-interface-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0c4ea-117">For more information about the methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
 <span data-ttu-id="0c4ea-118">Para crear un esquema para PeopleSoft, el adaptador de BizTalk para PeopleSoft Enterprise recupera las definiciones o metadatos de la interfaz del componente PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-118">To create a schema for PeopleSoft, BizTalk Adapter for PeopleSoft Enterprise retrieves the PeopleSoft component interface definitions or metadata.</span></span>  
  
 <span data-ttu-id="0c4ea-119">El adaptador de BizTalk para PeopleSoft Enterprise se basa en interfaces de componente para la funcionalidad de envío y no requiere PeopleSoft Integration Broker.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-119">BizTalk Adapter for PeopleSoft Enterprise is based on component interfaces for the Send functionality and does not require the PeopleSoft Integration Broker.</span></span> <span data-ttu-id="0c4ea-120">Las interfaces de componente se exponen como servicios Web, a los que se puede tener acceso desde BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-120">The component interfaces are exposed as Web services, which can be accessed from BizTalk Server.</span></span>  
  
### <a name="validation"></a><span data-ttu-id="0c4ea-121">Validación</span><span class="sxs-lookup"><span data-stu-id="0c4ea-121">Validation</span></span>  
 <span data-ttu-id="0c4ea-122">Cuando el adaptador de BizTalk para PeopleSoft Enterprise recibe un mensaje XML de BizTalk Server, se llevan a cabo dos niveles de validación:</span><span class="sxs-lookup"><span data-stu-id="0c4ea-122">When BizTalk Adapter for PeopleSoft Enterprise receives an XML message from BizTalk Server, two levels of validation are performed:</span></span>  
  
-   <span data-ttu-id="0c4ea-123">El mensaje XML debe ser válido con respecto a la especificación XML.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-123">The XML message must be valid with regard to XML specification.</span></span>  
  
-   <span data-ttu-id="0c4ea-124">El mensaje XML debe coincidir con lo que el servicio Web específico requiere (por ejemplo, coincidencia de interfaz como los tipos de datos).</span><span class="sxs-lookup"><span data-stu-id="0c4ea-124">The XML message must match what is required by the specific Web service (for example, interface matching such as data types).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c4ea-125">No hay ninguna validación en relación con la lógica empresarial, que es el dominio de sistema PeopleSoft y es transparente para el adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0c4ea-125">There is no validation with regard to business logic, which is the domain of the PeopleSoft system, and is transparent to BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c4ea-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c4ea-126">See Also</span></span>  
 <span data-ttu-id="0c4ea-127">[Introducción](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="0c4ea-127">[Getting Started](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span></span>  
 [<span data-ttu-id="0c4ea-128">Planeamiento y arquitectura</span><span class="sxs-lookup"><span data-stu-id="0c4ea-128">Planning and Architecture</span></span>](../core/planning-and-architecture13.md)