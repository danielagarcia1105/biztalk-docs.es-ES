---
title: Desarrollar un servicio en la solución orientada a servicios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, developing
- service solution tutorial, background information
- service solution tutorial, developing
- developing, tutorials
- developing, service solution tutorial
ms.assetid: 7979a05c-7fd3-4476-a623-55de8abdc493
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d8e33baa51a551d0f1f851410fda696abc96983
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239332"
---
# <a name="developing-a-service-oriented-solution"></a><span data-ttu-id="9eafe-102">Desarrollar un servicio en la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="9eafe-102">Developing a Service Oriented Solution</span></span>
<span data-ttu-id="9eafe-103">La solución orientada a servicios muestra un sistema de saldo de cuenta de crédito para Woodgrove Bank.</span><span class="sxs-lookup"><span data-stu-id="9eafe-103">The service oriented solution demonstrates a credit account balance system for Woodgrove Bank.</span></span> <span data-ttu-id="9eafe-104">Información sobre una cuenta procede de tres sistemas heredados: un sistema SAP que proporciona el límite de crédito, un sistema de transacciones pendientes que se ejecuta en un gran sistema y un sistema de seguimiento de pago con MQSeries.</span><span class="sxs-lookup"><span data-stu-id="9eafe-104">Information about an account comes from three legacy systems: an SAP system that provides the credit limit, a pending transactions system running on a mainframe, and a payment tracking system using MQSeries.</span></span> <span data-ttu-id="9eafe-105">Las solicitudes de comprobación de saldo proceden de un servicio Web o un sistema de respuesta interactiva de voz (IVR).</span><span class="sxs-lookup"><span data-stu-id="9eafe-105">Balance check requests come through a Web service or an Interactive Voice Response (IVR) system.</span></span> <span data-ttu-id="9eafe-106">Para obtener más información acerca del escenario, consulte [descripción de la solución orientada a servicios](../core/understanding-the-service-oriented-solution.md).</span><span class="sxs-lookup"><span data-stu-id="9eafe-106">For more information about the scenario, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="9eafe-107">Esta Guía del programador presenta un enfoque para la generación de una solución de arquitectura orientada a servicios para el escenario de Woodgrove Bank.</span><span class="sxs-lookup"><span data-stu-id="9eafe-107">This Developer's Guide presents one approach to building a service oriented architecture solution for the Woodgrove Bank scenario.</span></span> <span data-ttu-id="9eafe-108">La guía comienza teniendo en cuenta una solución posible en cuanto a patrones estándar del sector.</span><span class="sxs-lookup"><span data-stu-id="9eafe-108">The Guide begins by considering a possible solution in terms of industry-standard patterns.</span></span> <span data-ttu-id="9eafe-109">La sección “Patrones en la solución orientada a servicios” comienza con la traducción de dicho patrón en los artefactos correspondientes de una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9eafe-109">"Patterns in the Service Oriented Solution" begins the translation of that pattern into the appropriate artifacts of a BizTalk application.</span></span> <span data-ttu-id="9eafe-110">La siguiente sección, “Componentes de la solución orientada a servicios”, resume las distintas partes de la aplicación y cómo están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="9eafe-110">The next section, "Components of the Service Oriented Solution," summarizes the various parts of the application and their relationships.</span></span> <span data-ttu-id="9eafe-111">La sección pone de manifiesto de implementación describen las áreas, como el uso de Enterprise Single Sign-On, que requieren tareas especiales para cumplir los criterios del escenario.</span><span class="sxs-lookup"><span data-stu-id="9eafe-111">The Implementation Highlights section discusses areas—such as using Enterprise Single Sign-On—that required special work to meet the criteria of the scenario.</span></span> <span data-ttu-id="9eafe-112">La sección “Supervisar la solución orientada a servicios con BAM” describe cómo la solución utiliza la API de BAM para realizar el seguimiento del progreso de las solicitudes y los resultados.</span><span class="sxs-lookup"><span data-stu-id="9eafe-112">"Monitoring the Service Oriented Solution with BAM" describes how the solution uses the BAM API to track progress of requests and results.</span></span> <span data-ttu-id="9eafe-113">Las secciones “Controlar las versiones de la solución orientada a servicios” y “Escalar la solución orientada a servicios” incluyen modos de ampliar o modificar la solución.</span><span class="sxs-lookup"><span data-stu-id="9eafe-113">The "Versioning the Service Oriented Solution" and "Scaling the Service Oriented Solution" sections suggest ways of extending or modifying the solution.</span></span> <span data-ttu-id="9eafe-114">La sección de referencia muestra los archivos de la solución y suministra una referencia a los mensajes.</span><span class="sxs-lookup"><span data-stu-id="9eafe-114">The reference section lists the files in the solution and provides a reference to the messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9eafe-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9eafe-115">In This Section</span></span>  
  
-   [<span data-ttu-id="9eafe-116">Patrones en la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="9eafe-116">Patterns in the Service Oriented Solution</span></span>](../core/patterns-in-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="9eafe-117">Solución orientada a servicios de componentes del servicio</span><span class="sxs-lookup"><span data-stu-id="9eafe-117">Components of the Service Oriented Solution</span></span>](../core/components-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="9eafe-118">Aspectos destacados de la implementación del servicio en la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="9eafe-118">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="9eafe-119">El servicio de supervisión orientada a servicios solución con BAM</span><span class="sxs-lookup"><span data-stu-id="9eafe-119">Monitoring the Service Oriented Solution with BAM</span></span>](../core/monitoring-the-service-oriented-solution-with-bam.md)  
  
-   [<span data-ttu-id="9eafe-120">Solución orientada a servicios de control de versiones del servicio</span><span class="sxs-lookup"><span data-stu-id="9eafe-120">Versioning the Service Oriented Solution</span></span>](../core/versioning-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="9eafe-121">Escalar la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="9eafe-121">Scaling the Service Oriented Solution</span></span>](../core/scaling-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="9eafe-122">Referencia de la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="9eafe-122">Service Oriented Solution Reference</span></span>](../core/service-oriented-solution-reference.md)