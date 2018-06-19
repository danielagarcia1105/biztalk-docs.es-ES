---
title: El servicio Web de transformación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 788bf4a9-a63b-4fd3-93a2-6e34a1464049
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5abad7a5a7bae3c76fba58ecd92fc3384df5ca25
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294876"
---
# <a name="the-transformation-web-service"></a><span data-ttu-id="216ee-102">El servicio Web de transformación</span><span class="sxs-lookup"><span data-stu-id="216ee-102">The Transformation Web Service</span></span>
<span data-ttu-id="216ee-103">El servicio Web de transformación permite que aplicaciones externas para enviar un documento a una aplicación de ESB y hacer que se transforma utilizando una asignación de Microsoft BizTalk implementada.</span><span class="sxs-lookup"><span data-stu-id="216ee-103">The Transformation Web service enables external applications to submit a document to an ESB application and have it transformed using a deployed Microsoft BizTalk map.</span></span> <span data-ttu-id="216ee-104">Al contrario que el agente de transformación, este servicio no enruta mensajes a través de la base de datos de cuadro de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="216ee-104">Unlike the transformation agent, this service does not route messages through the BizTalk Message Box database.</span></span>  
  
 <span data-ttu-id="216ee-105">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene dos versiones de este servicio: una versión de ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="216ee-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="216ee-106">Los nombres de servicio son **ESB. TransformServices** y **ESB. TransformServices.WCF**, respectivamente, y los servicios exponen un método único:</span><span class="sxs-lookup"><span data-stu-id="216ee-106">The service names are **ESB.TransformServices** and **ESB.TransformServices.WCF**, respectively, and the services expose a single method:</span></span>  
  
-   <span data-ttu-id="216ee-107">**Transformar.**</span><span class="sxs-lookup"><span data-stu-id="216ee-107">**Transform.**</span></span> <span data-ttu-id="216ee-108">Este método toma como parámetros un **cadena** que contiene el mensaje que se va a transformar y un **cadena** que contiene el nombre completo de un mapa que se implementan en BizTalk.</span><span class="sxs-lookup"><span data-stu-id="216ee-108">This method takes as parameters a **String** that contains the message to transform and a **String** that contains the fully qualified name of a map deployed in BizTalk.</span></span> <span data-ttu-id="216ee-109">El método devuelve un **cadena** que contiene el documento transformado.</span><span class="sxs-lookup"><span data-stu-id="216ee-109">The method returns a **String** that contains the transformed document.</span></span> <span data-ttu-id="216ee-110">El uso de parámetros de cadena reduce el riesgo de problemas de interoperabilidad en un entorno heterogéneo; Sin embargo, tenga en cuenta que esto es un servicio Web, por lo que debería evitar utilizarla para transformar documentos de gran tamaño (el servicio de transformación de BizTalk es más adecuado para documentos de gran tamaño).</span><span class="sxs-lookup"><span data-stu-id="216ee-110">The use of string parameters reduces the risk of interoperability issues in a heterogeneous environment; however, keep in mind that this is a Web service, so you should avoid using it to transform large documents (the Transformation Service in BizTalk is better suited for large documents).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="216ee-111">De forma predeterminada, los servicios Web de transformación no estén configurados para requerir Secure Sockets Layer (SSL) a los que tienen acceso los clientes.</span><span class="sxs-lookup"><span data-stu-id="216ee-111">By default, the Transformation Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="216ee-112">Debe configurar el servicio para que requiere SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor de BizTalk mediante IPSec de nivel de red y acceso de nivel de archivo adecuado permisos de control de lista (ACL).</span><span class="sxs-lookup"><span data-stu-id="216ee-112">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and your BizTalk Server using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>