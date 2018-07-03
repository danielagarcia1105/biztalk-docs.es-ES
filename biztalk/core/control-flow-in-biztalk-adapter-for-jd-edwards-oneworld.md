---
title: Controlar el flujo en el adaptador de BizTalk para JD Edwards OneWorld | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection pooling
- control flows
- apartment threading
- apartment threading, business functions
ms.assetid: 1ec865d0-2257-453b-9230-1f3787ebac38
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c777d909d5ffd405caec6641ef4a50a59e66b3b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978933"
---
# <a name="control-flow-in-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="f4f8e-102">Control del flujo del adaptador de BizTalk para JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="f4f8e-102">Control Flow in BizTalk Adapter for JD Edwards OneWorld</span></span>
<span data-ttu-id="f4f8e-103">En este tema se tratan los flujos de control de tiempo de diseño y de tiempo de ejecución en el Adaptador de Microsoft BizTalk para JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-103">This topic discusses the design time and run-time control flows in Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="design-time-flow"></a><span data-ttu-id="f4f8e-104">Flujo de tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="f4f8e-104">Design-Time Flow</span></span>  
 <span data-ttu-id="f4f8e-105">Cuando se abre el adaptador (usando las credenciales y la información del sistema del cuadro de diálogo Propiedades de transporte), una o varias instancias de la función empresarial de la aplicación JD Edwards OneWorld se crean y agrupan.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-105">When the adapter opens (using the credentials and system information from the Transport Properties dialog box), one or more instances of the JD Edwards OneWorld application business function are created and pooled.</span></span> <span data-ttu-id="f4f8e-106">Al examinar el espacio de nombres en el Asistente para el adaptador, aparece una lista de funciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-106">When you browse the namespace in the Adapter Wizard, a list of business functions appear.</span></span> <span data-ttu-id="f4f8e-107">Al hacer clic en una función empresarial se muestran sus métodos lógicos junto con las firmas de métodos.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-107">Clicking a business function displays its logical methods along with the methods signatures.</span></span>  
  
## <a name="run-time-flow"></a><span data-ttu-id="f4f8e-108">Flujo de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f4f8e-108">Run-Time Flow</span></span>  
 <span data-ttu-id="f4f8e-109">Las instancias de la función empresarial de JD Edwards OneWorld se crean y agrupan para cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-109">Instances of the JD Edwards OneWorld business function are created and pooled for each thread.</span></span> <span data-ttu-id="f4f8e-110">Cuando se envía una llamada de método a un servicio empresarial, los metadatos del método se leen usando la función empresarial de la aplicación JD Edwards OneWorld; sin embargo si los metadatos del método ya se han almacenado en caché, la función empresarial usará la información almacenada en caché y realizará una llamada al método correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-110">When a method call is submitted to a business service, the metadata for the method is read using the JD Edwards OneWorld application business function; however, if the metadata for the method has already been cached, the business function uses the cached information and then makes a call to the appropriate method.</span></span> <span data-ttu-id="f4f8e-111">En tiempo de ejecución, una capa de interfaz de JD Edwards OneWorld se construye dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-111">At run time, a JD Edwards OneWorld interface layer is dynamically constructed.</span></span> <span data-ttu-id="f4f8e-112">A través de la capa de interfaz, el Adaptador de BizTalk para JD Edwards OneWorld admite la invocación y las conversiones de datos.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-112">It is through the interface layer that BizTalk Adapter for JD Edwards OneWorld supports invocation and data conversions.</span></span>  
  
 <span data-ttu-id="f4f8e-113">El Adaptador de BizTalk para JD Edwards OneWorld asigna descripciones de interfaz de las firmas del método de la aplicación JD Edwards OneWorld, permitiendo a BizTalk Server interactuar con estas descripciones de interfaz.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-113">BizTalk Adapter for JD Edwards OneWorld maps interface descriptions of the method signatures of the JD Edwards OneWorld application, allowing BizTalk Server to interact with these interface descriptions.</span></span>  
  
 <span data-ttu-id="f4f8e-114">El adaptador habilita las aplicaciones de la empresa para que interactúen con la aplicación JD Edwards OneWorld extendiendo las funciones desde la aplicación en forma de uno o varios de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f4f8e-114">The adapter enables applications in the enterprise to interact with the JD Edwards OneWorld application by extending functionality from the application in the form of one or more of the following:</span></span>  
  
- <span data-ttu-id="f4f8e-115">Formatos de datos nativos</span><span class="sxs-lookup"><span data-stu-id="f4f8e-115">Native data formats</span></span>  
  
- <span data-ttu-id="f4f8e-116">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="f4f8e-116">Procedures</span></span>  
  
- <span data-ttu-id="f4f8e-117">Métodos</span><span class="sxs-lookup"><span data-stu-id="f4f8e-117">Methods</span></span>  
  
- <span data-ttu-id="f4f8e-118">Mensajes</span><span class="sxs-lookup"><span data-stu-id="f4f8e-118">Messages</span></span>  
  
- <span data-ttu-id="f4f8e-119">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f4f8e-119">Properties</span></span>  
  
- <span data-ttu-id="f4f8e-120">Interfaces de aplicación</span><span class="sxs-lookup"><span data-stu-id="f4f8e-120">Application interfaces</span></span>  
  
  <span data-ttu-id="f4f8e-121">En tiempo de ejecución, el adaptador de BizTalk para JD Edwards OneWorld benera interfaces de aplicación para las aplicaciones cliente que interactúan con JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-121">At run time, BizTalk Adapter for JD Edwards OneWorld builds a description of application interfaces for client applications that interact with JD Edwards OneWorld.</span></span> <span data-ttu-id="f4f8e-122">El adaptador puede crear, eliminar e invocar objetos empresariales según sea necesario, para realizar cálculos en la aplicación e invocar métodos directamente.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-122">The adapter can create, delete, and invoke business objects as needed, to perform computations in the application and directly invoke methods.</span></span> <span data-ttu-id="f4f8e-123">Todas las llamadas a JD Edwards OneWorld son llamadas sincrónicas.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-123">All calls into JD Edwards OneWorld are synchronous calls.</span></span> <span data-ttu-id="f4f8e-124">El adaptador recibe los mensajes XML desde BizTalk Server, incluye los mensajes en un sobre SOAP y transforma los datos para la llamada desde mensajes SOAP a tipos de Java.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-124">The adapter receives the XML messages from BizTalk Server, encloses the messages in a SOAP envelope, and transforms the data for the call from SOAP messages into Java types.</span></span>  
  
  <span data-ttu-id="f4f8e-125">La respuesta se devuelve siguiendo un proceso similar:</span><span class="sxs-lookup"><span data-stu-id="f4f8e-125">The reply is sent back following a similar process:</span></span>  
  
1.  <span data-ttu-id="f4f8e-126">Los tipos de Java se transforman en mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-126">The Java types are transformed into SOAP messages.</span></span>  
  
2.  <span data-ttu-id="f4f8e-127">Los mensajes SOAP se convierten en mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-127">The SOAP messages are converted into XML messages.</span></span>  
  
3.  <span data-ttu-id="f4f8e-128">Los mensajes XML se envían a BizTalk Server para su posterior procesamiento.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-128">The XML messages are submitted to BizTalk Server for further processing.</span></span>  
  
### <a name="apartment-threading-of-business-functions"></a><span data-ttu-id="f4f8e-129">Apartamento de subproceso de funciones empresariales</span><span class="sxs-lookup"><span data-stu-id="f4f8e-129">Apartment Threading of Business Functions</span></span>  
 <span data-ttu-id="f4f8e-130">Una función empresarial de JD Edwards OneWorld, en cualquier instancia, solo puede usarse en el subproceso donde se creó u obtuvo.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-130">A JD Edwards OneWorld business function, and any instance, can only be used on the thread where it is created or obtained.</span></span> <span data-ttu-id="f4f8e-131">Esto se conoce como *apartamento de subproceso*.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-131">This is known as *apartment threading*.</span></span> <span data-ttu-id="f4f8e-132">El marco de agrupación de conexiones del adaptador de BizTalk para JD Edwards OneWorld administra un grupo de conexiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-132">The connection pooling framework of BizTalk Adapter for JD Edwards OneWorld manages a pool of available connections.</span></span>  
  
### <a name="connection-pooling"></a><span data-ttu-id="f4f8e-133">Agrupar conexiones</span><span class="sxs-lookup"><span data-stu-id="f4f8e-133">Connection Pooling</span></span>  
 <span data-ttu-id="f4f8e-134">La agrupación de conexioens mejora el rendimiento de llamadas manteniendo las conexiones a los sistemas del servidor abiertas y reusándolas en lugar de cerrarlas después de cada llamada.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-134">Connection pooling improves the performance of calls by keeping connections to the server systems open and reusing them instead of closing them after each call.</span></span> <span data-ttu-id="f4f8e-135">El adaptador de BizTalk para JD Edwards OneWorld le permite agrupar conexiones dentro de determinados ID de inicio de sesión, pero manteniendo un control crítico del número total de conexiones en todas las agrupaciones.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-135">BizTalk Adapter for JD Edwards OneWorld enables you to pool connections within particular logon IDs, but still maintains critical control of the total number of connections across all pools.</span></span>  
  
 <span data-ttu-id="f4f8e-136">Cualquier nueva instancia de función empresarial usa el subproceso en el cual se creó y la instancia se destruyó después de cada operación.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-136">Any new business function instance uses the thread on which it is created, and the instance is destroyed after each operation.</span></span> <span data-ttu-id="f4f8e-137">Todas las llamadas de JD Edwards OneWorld a funciones empresariales son sin estado; no obstante, durante la operación, el adaptador se asegura de que la función empresarial se use en el subproceso correcto.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-137">All JD Edwards OneWorld calls to business functions are stateless; however, during the operation, the adapter ensures that the business function is used on the correct thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f8e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4f8e-138">See Also</span></span>  
 <span data-ttu-id="f4f8e-139">[Desarrollo de aplicaciones](../core/developing-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="f4f8e-139">[Developing Applications](../core/developing-applications3.md) </span></span>  
 [<span data-ttu-id="f4f8e-140">Planificación y arquitectura</span><span class="sxs-lookup"><span data-stu-id="f4f8e-140">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)