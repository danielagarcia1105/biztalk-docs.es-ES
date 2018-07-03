---
title: Empezar a trabajar con el adaptador de BizTalk para aplicaciones Siebel eBusiness | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, about
ms.assetid: 0867f95f-977f-48bf-8c46-70fd6e4df56b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f4d03e8b85811db6ea7fe7bcde5bf37f93b255d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968949"
---
# <a name="get-started-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="b8d1a-102">Empezar a trabajar con el adaptador de BizTalk para aplicaciones Siebel eBusiness</span><span class="sxs-lookup"><span data-stu-id="b8d1a-102">Get started with the BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="b8d1a-103">En esta sección proporciona información general del adaptador, los requisitos previos y los temas para los usuarios que trabajan con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8d1a-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="b8d1a-104">Describe las características de [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] y las distintas operaciones que se pueden realizar en el sistema de Siebel mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="b8d1a-104">It discusses the features of [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] and the different operations that can be performed on the Siebel system using the adapter.</span></span>  
  
 <span data-ttu-id="b8d1a-105">¿Qué es un adaptador?</span><span class="sxs-lookup"><span data-stu-id="b8d1a-105">What is an adapter?</span></span> <span data-ttu-id="b8d1a-106">Un adaptador es un componente de software que le permite enviar y recibir mensajes hacia y desde un sistema de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="b8d1a-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="b8d1a-107">El objetivo principal de diseño de adaptadores es facilitar el intercambio de documentos empresariales entre socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="b8d1a-107">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="b8d1a-108">Dado que cada sistema de negocio puede adherirse a protocolos y formatos de documento específico, el adaptador debe usar un mecanismo de entrega que se ajusta a protocolos y estándares comúnmente reconocidos.</span><span class="sxs-lookup"><span data-stu-id="b8d1a-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols.</span></span>  
  
 <span data-ttu-id="b8d1a-109">Los adaptadores pueden dividirse en dos amplias categorías:</span><span class="sxs-lookup"><span data-stu-id="b8d1a-109">The adapters can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="b8d1a-110">**Adaptadores de LOB**.</span><span class="sxs-lookup"><span data-stu-id="b8d1a-110">**LOB adapters**.</span></span> <span data-ttu-id="b8d1a-111">Estos adaptadores proporcionan un modelo de programación orientada a los sistemas LOB de acceso — por ejemplo, los adaptadores de SAP o Siebel.</span><span class="sxs-lookup"><span data-stu-id="b8d1a-111">Such adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
- <span data-ttu-id="b8d1a-112">**Los adaptadores de datos**.</span><span class="sxs-lookup"><span data-stu-id="b8d1a-112">**Data adapters**.</span></span> <span data-ttu-id="b8d1a-113">Estos adaptadores proporcionan un modelo de programación orientada a las bases de datos de acceso — por ejemplo, un adaptador para la base de datos de Oracle o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8d1a-113">Such adapters provide a service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="b8d1a-114">Hay cinco adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b8d1a-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="b8d1a-115"> (el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="b8d1a-115"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="b8d1a-116"> (el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="b8d1a-116"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="b8d1a-117"> (el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="b8d1a-117"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="b8d1a-118"> (el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), incluidos [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="b8d1a-118"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="b8d1a-119"> (el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), incluidos [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="b8d1a-119"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="b8d1a-120">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no está disponible para plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b8d1a-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="b8d1a-121">Si no ya sabe cómo desea usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en su empresa, se recomienda que primero debe explorar las características y funcionalidad del adaptador se describe en [información general sobre el adaptador de BizTalk para aplicaciones Siebel eBusiness ](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md).</span><span class="sxs-lookup"><span data-stu-id="b8d1a-121">If you do not already know how you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Overview of BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8d1a-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b8d1a-122">In This Section</span></span>  
  
-   [<span data-ttu-id="b8d1a-123">Definición del adaptador de BizTalk para las aplicaciones de negocio electrónico de Siebel</span><span class="sxs-lookup"><span data-stu-id="b8d1a-123">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) 
  
-   [<span data-ttu-id="b8d1a-124">Tutoriales del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="b8d1a-124">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)  
  
-   [<span data-ttu-id="b8d1a-125">Recursos de comunidad</span><span class="sxs-lookup"><span data-stu-id="b8d1a-125">Community Resources</span></span>](http://msdn.microsoft.com/library/ff5ec978-8cdd-418a-a25e-fd3746b64d8b)  
  
-   [<span data-ttu-id="b8d1a-126">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="b8d1a-126">Frequently Asked Questions</span></span>](http://msdn.microsoft.com/library/66953c15-08c5-48ac-a4ff-a72a82174f15)