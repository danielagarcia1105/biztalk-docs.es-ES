---
title: El servicio Web de control de excepciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe6ebdf-9b92-40c7-93fb-afd6c5f68aaa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8d8f3439e3b99d118e2932d0a158113ec51be2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-exception-handling-web-service"></a><span data-ttu-id="62df8-102">El servicio Web de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="62df8-102">The Exception Handling Web Service</span></span>
<span data-ttu-id="62df8-103">El servicio Web de control de excepciones acepta un mensaje de error y lo publica en el Portal de la excepción de ESB.</span><span class="sxs-lookup"><span data-stu-id="62df8-103">The Exception Handling Web service accepts a fault message and publishes it to the ESB Exception Portal.</span></span> <span data-ttu-id="62df8-104">Una aplicación cliente puede crear mensajes de excepción y enviarlos a ESB, donde cualquier controlador configurado para ese tipo de excepción o un controlador genérico, puede procesar la excepción.</span><span class="sxs-lookup"><span data-stu-id="62df8-104">A client application can create exception messages and submit them to the ESB, where any handler configured for that exception type, or a generic handler, can process the exception.</span></span> <span data-ttu-id="62df8-105">La principal ventaja de este servicio es que permite a las entidades fuera de una aplicación de ESB para participar en el mecanismo de control de excepciones de ESB.</span><span class="sxs-lookup"><span data-stu-id="62df8-105">The major benefit of this service is that it allows entities outside an ESB application to participate in the ESB exception handling mechanism.</span></span>  
  
 <span data-ttu-id="62df8-106">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene dos versiones de este servicio: una versión de ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="62df8-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="62df8-107">Los nombres de servicio son **ESB. ExceptionHandlingServices** y **ESB. ExceptionHandlingServices.WCF**, respectivamente, y los servicios exponen un método único:</span><span class="sxs-lookup"><span data-stu-id="62df8-107">The service names are **ESB.ExceptionHandlingServices** and **ESB.ExceptionHandlingServices.WCF**, respectively, and the services expose a single method:</span></span>  
  
-   <span data-ttu-id="62df8-108">**SubmitFault**.</span><span class="sxs-lookup"><span data-stu-id="62df8-108">**SubmitFault**.</span></span> <span data-ttu-id="62df8-109">Este método toma una instancia de la **FaultMessage** clase y no tiene ningún valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="62df8-109">This method takes an instance of the **FaultMessage** class and has no return value.</span></span>  
  
 <span data-ttu-id="62df8-110">Para obtener información sobre la forma en que funciona el mecanismo de control de excepciones, vea [utilizando Administración de excepciones de ESB](../esb-toolkit/using-esb-exception-management.md).</span><span class="sxs-lookup"><span data-stu-id="62df8-110">For information about the way the exception handling mechanism works, see [Using ESB Exception Management](../esb-toolkit/using-esb-exception-management.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62df8-111">De forma predeterminada, los servicios Web de control de excepciones no estén configurados para requerir Secure Sockets Layer (SSL) a los que tienen acceso los clientes.</span><span class="sxs-lookup"><span data-stu-id="62df8-111">By default, the Exception Handling Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="62df8-112">Debe configurar el servicio para que requiere SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor que hospeda el **ESBExceptions** base de datos uso de IPSec de nivel de red y permisos de lista (ACL) del control de acceso de nivel de archivo adecuado.</span><span class="sxs-lookup"><span data-stu-id="62df8-112">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and the server that hosts the **ESBExceptions** database using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>