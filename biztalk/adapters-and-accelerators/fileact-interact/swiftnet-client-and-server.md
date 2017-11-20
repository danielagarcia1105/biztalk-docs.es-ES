---
title: Servidor y cliente SWIFTNet | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89d9f54f-af16-4f14-bbe4-8306758320d8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ea3a1b974a26f90d03bb65675c1c4e8966720f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swiftnet-client-and-server"></a><span data-ttu-id="49039-102">SWIFTNet cliente y servidor</span><span class="sxs-lookup"><span data-stu-id="49039-102">SWIFTNet Client and Server</span></span>
<span data-ttu-id="49039-103">SWIFT utiliza los términos cliente y servidor para describir el envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="49039-103">SWIFT uses the terms client and server to describe sending and receiving.</span></span> <span data-ttu-id="49039-104">Un cliente SWIFT es un proceso que llama el vínculo de SWIFTNet (SNL) para iniciar la comunicación a través de SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="49039-104">A SWIFT client is a process that calls the SWIFTNet Link (SNL) to initiate communication over SWIFTNet.</span></span> <span data-ttu-id="49039-105">En BizTalk Server, esto se denomina el adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="49039-105">In BizTalk Server, this is called the send adapter.</span></span> <span data-ttu-id="49039-106">Un servidor de SWIFT es un programa que llama a la SNL al tráfico entra a través de SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="49039-106">A SWIFT server is a program that is called by the SNL when traffic comes in over SWIFTNet.</span></span> <span data-ttu-id="49039-107">En BizTalk Server, esto se denomina el adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="49039-107">In BizTalk Server, this is called the receive adapter.</span></span>  
  
 <span data-ttu-id="49039-108">No confunda el cliente SWIFT y el servidor con el cliente empresarial y el servidor.</span><span class="sxs-lookup"><span data-stu-id="49039-108">Do not confuse the SWIFT client and server with the business client and server.</span></span> <span data-ttu-id="49039-109">Por ejemplo, un cliente (organización) se basa en los servicios proporcionados por un servidor (organización).</span><span class="sxs-lookup"><span data-stu-id="49039-109">For example, a client (organization) relies on the services provided by a server (organization).</span></span> <span data-ttu-id="49039-110">Si desea que el servidor (organización) iniciar una comunicación con el cliente (organización), debe usar una aplicación de cliente SNL para hacerlo y el cliente (organización) debe tener una aplicación de servidor SNL para recibir el tráfico entrante.</span><span class="sxs-lookup"><span data-stu-id="49039-110">If the server (organization) wants to initiate a communication with the client (organization), it must use an SNL client application to do so, and the client (organization) must have an SNL server application to receive the incoming traffic.</span></span> <span data-ttu-id="49039-111">Esto se describe en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="49039-111">This is described in the following figure.</span></span>  
  
 <span data-ttu-id="49039-112">![Relación SWIFTNet entre el cliente y servidor](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")</span><span class="sxs-lookup"><span data-stu-id="49039-112">![SWIFTNet relationship between client and server](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")</span></span>  
  
 <span data-ttu-id="49039-113">SNL se da por supuesto que las aplicaciones cliente y servidor son archivos ejecutables que se inicia desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="49039-113">SNL assumes both client and server applications are executables started from the command prompt.</span></span> <span data-ttu-id="49039-114">Ambos se vinculan a la DLL de API de SNL, que se comunica con el proceso de instancia real de SNL.</span><span class="sxs-lookup"><span data-stu-id="49039-114">They both link to the SNL API DLL, which communicates with the actual SNL instance process.</span></span>  
  
## <a name="snl-client-applications"></a><span data-ttu-id="49039-115">Aplicaciones de cliente SNL</span><span class="sxs-lookup"><span data-stu-id="49039-115">SNL client applications</span></span>  
 <span data-ttu-id="49039-116">Las aplicaciones de cliente SNL se basan en la API de SwCall se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="49039-116">SNL client applications rely on the SwCall API described below.</span></span> <span data-ttu-id="49039-117">Técnicamente hablando, una aplicación cliente típica se puede describir como sigue:</span><span class="sxs-lookup"><span data-stu-id="49039-117">Technically speaking, a typical client application can be described as follows:</span></span>  
  
```  
Main:  
  Initialize SNL API  
  Repeat  
    Call SwCall API  
  Until shutdown  
```  
  
 <span data-ttu-id="49039-118">Cliente SNL aplicaciones deben ejecutarse en un proceso dedicado, porque SNL hace referencia al contexto de cliente por Id. de proceso</span><span class="sxs-lookup"><span data-stu-id="49039-118">SNL client applications must run in a dedicated process, because SNL references the client context by process ID.</span></span> <span data-ttu-id="49039-119">SNL sincroniza las llamadas que utilizan recursos Tuxedo SwCall.</span><span class="sxs-lookup"><span data-stu-id="49039-119">SNL synchronizes calls that use Tuxedo resources to SwCall.</span></span> <span data-ttu-id="49039-120">Como resultado, solo un subproceso de cliente único a la vez puede ejecutar de manera eficaz un SwCall.</span><span class="sxs-lookup"><span data-stu-id="49039-120">As a result, only a single client thread at a time can effectively execute a SwCall.</span></span>  
  
 <span data-ttu-id="49039-121">El cliente admite el modo de comunicación sincrónica.</span><span class="sxs-lookup"><span data-stu-id="49039-121">The client supports the synchronous communication mode.</span></span> <span data-ttu-id="49039-122">Esto significa que la rentabilidad de la SWCall se produce cuando vuelve la respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="49039-122">This means that the return on the SWCall occurs when the response comes back from the server.</span></span> <span data-ttu-id="49039-123">El siguiente SwCall puede realizarse después de esta devolución.</span><span class="sxs-lookup"><span data-stu-id="49039-123">The next SwCall can be performed only after this return.</span></span>  
  
## <a name="snl-server-applications"></a><span data-ttu-id="49039-124">Aplicaciones de SNL server</span><span class="sxs-lookup"><span data-stu-id="49039-124">SNL server applications</span></span>  
 <span data-ttu-id="49039-125">Las aplicaciones de servidor SNL son ligeramente más complejas que las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="49039-125">SNL server applications are slightly more complex than the client applications.</span></span> <span data-ttu-id="49039-126">Las aplicaciones de servidor registrar las funciones de devolución de llamada antes de realizar una llamada de bloqueo en la DLL de SNL.</span><span class="sxs-lookup"><span data-stu-id="49039-126">Server applications register callback functions before performing a blocking call into the SNL DLL.</span></span> <span data-ttu-id="49039-127">Técnicamente hablando, una aplicación de servidor típicos se puede describir como sigue:</span><span class="sxs-lookup"><span data-stu-id="49039-127">Technically speaking, a typical server application can be described as follows:</span></span>  
  
```  
Main:  
  Initialize SNL API  
  Call SwRegisterSwCallback, registering the Callback function  
  Call SwServer, block and receive callbacks  
  
Callback(Request):  
  Process Request  
  Return Response  
```  
  
 <span data-ttu-id="49039-128">La aplicación de servidor puede llamar a la API SwCall mientras se encuentra en la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="49039-128">The server application can call the SwCall API while in the callback function.</span></span> <span data-ttu-id="49039-129">En algunos casos, debe llamar a SwCall para poder generar el resultado deseado o respuesta.</span><span class="sxs-lookup"><span data-stu-id="49039-129">In some cases it must call SwCall to be able to produce the desired result or response.</span></span> <span data-ttu-id="49039-130">Sin embargo, una aplicación de servidor nunca puede iniciar una comunicación a través de la red.</span><span class="sxs-lookup"><span data-stu-id="49039-130">However, a server application can never initiate a communication over the network.</span></span> <span data-ttu-id="49039-131">Una aplicación de servidor nunca puede ser una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="49039-131">A server application can never be a client application.</span></span>  
  
 <span data-ttu-id="49039-132">En la ilustración siguiente, la llamada con la etiqueta **inicializar** es una abstracción para el proceso de inicialización de la API de SNL, que requiere varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="49039-132">In the following figure, the call labeled **Initialize** is an abstraction for the SNL API initialization process, which requires multiple calls.</span></span> <span data-ttu-id="49039-133">La llamada con la etiqueta **SwCallback()** se repetirá varias veces, y la etiqueta de la llamada **SwCall()** es opcional.</span><span class="sxs-lookup"><span data-stu-id="49039-133">The call labeled **SwCallback()** will be repeated several times, and the call labeled **SwCall()** is optional.</span></span>  
  
 <span data-ttu-id="49039-134">![Funcionalidad de SNL Server](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")</span><span class="sxs-lookup"><span data-stu-id="49039-134">![SNL Server functionality](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")</span></span>  
  
 <span data-ttu-id="49039-135">Todas las llamadas entre el servidor y la DLL de la API de SNL son llamadas a funciones sincrónicas convención de llamada estándar de C++.</span><span class="sxs-lookup"><span data-stu-id="49039-135">All calls between the server and the SNL API DLL are standard C calling convention synchronous function calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49039-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="49039-136">See Also</span></span>  
 <span data-ttu-id="49039-137">[Descripción de FileAct e interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="49039-137">[Understanding FileAct and InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="49039-138">[Arquitectura del adaptador de envío SWIFT](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="49039-138">[SWIFT Send Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="49039-139">Arquitectura del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="49039-139">SWIFT Receive Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)