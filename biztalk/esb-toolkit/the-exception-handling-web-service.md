---
title: El servicio Web de control de excepciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfe6ebdf-9b92-40c7-93fb-afd6c5f68aaa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bcc8146947f5e3cbaf58e31d1f515a055d102c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974309"
---
# <a name="the-exception-handling-web-service"></a><span data-ttu-id="69432-102">El servicio Web de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="69432-102">The Exception Handling Web Service</span></span>
<span data-ttu-id="69432-103">El servicio Web de control de excepciones acepta un mensaje de error y lo publica en el Portal de excepciones de ESB.</span><span class="sxs-lookup"><span data-stu-id="69432-103">The Exception Handling Web service accepts a fault message and publishes it to the ESB Exception Portal.</span></span> <span data-ttu-id="69432-104">Una aplicación cliente puede crear mensajes de excepción y enviarlas a ESB, donde cualquier controlador configurado para ese tipo de excepción o un controlador genérico, puede procesar la excepción.</span><span class="sxs-lookup"><span data-stu-id="69432-104">A client application can create exception messages and submit them to the ESB, where any handler configured for that exception type, or a generic handler, can process the exception.</span></span> <span data-ttu-id="69432-105">La principal ventaja de este servicio es que permite entidades fuera de una aplicación de ESB para participar en el mecanismo de control de excepciones de ESB.</span><span class="sxs-lookup"><span data-stu-id="69432-105">The major benefit of this service is that it allows entities outside an ESB application to participate in the ESB exception handling mechanism.</span></span>  
  
 <span data-ttu-id="69432-106">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene dos versiones de este servicio: una versión de ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="69432-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="69432-107">Los nombres de servicio son **ESB. ExceptionHandlingServices** y **ESB. ExceptionHandlingServices.WCF**, respectivamente, y los servicios exponen un único método:</span><span class="sxs-lookup"><span data-stu-id="69432-107">The service names are **ESB.ExceptionHandlingServices** and **ESB.ExceptionHandlingServices.WCF**, respectively, and the services expose a single method:</span></span>  
  
- <span data-ttu-id="69432-108">**SubmitFault**.</span><span class="sxs-lookup"><span data-stu-id="69432-108">**SubmitFault**.</span></span> <span data-ttu-id="69432-109">Este método toma una instancia de la **FaultMessage** clase y no tiene ningún valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="69432-109">This method takes an instance of the **FaultMessage** class and has no return value.</span></span>  
  
  <span data-ttu-id="69432-110">Para obtener información sobre la forma en que funciona el mecanismo de control de excepciones, vea [usando administración de excepciones de ESB](../esb-toolkit/using-esb-exception-management.md).</span><span class="sxs-lookup"><span data-stu-id="69432-110">For information about the way the exception handling mechanism works, see [Using ESB Exception Management](../esb-toolkit/using-esb-exception-management.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69432-111">De forma predeterminada, los servicios Web de control de excepciones no se configuran para que requiera Secure Sockets Layer (SSL) cuando obtiene acceso a los clientes.</span><span class="sxs-lookup"><span data-stu-id="69432-111">By default, the Exception Handling Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="69432-112">Debe configurar el servicio para que requiera SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor que hospeda el **ESBExceptions** base de datos uso de IPSec de nivel de red y permisos de lista (ACL) del control de acceso de nivel de archivo adecuado.</span><span class="sxs-lookup"><span data-stu-id="69432-112">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and the server that hosts the **ESBExceptions** database using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>