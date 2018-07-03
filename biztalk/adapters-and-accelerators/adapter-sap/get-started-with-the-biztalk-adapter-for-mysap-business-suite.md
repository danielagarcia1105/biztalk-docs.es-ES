---
title: Empezar a trabajar con el adaptador de BizTalk para mySAP Business Suite | Microsoft Docs
description: Instalar RFC personalizadas, obtenga información acerca del adaptador, completar tareas RFC e IDOC en SAP, paso a través de tutoriales para utilizar el adaptador de mySAP en módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2013253-f911-4e35-a33a-b4a9bcb136aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02112b6974a537c9f66cc301014ae16bb4bf326f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967477"
---
# <a name="get-started-with-the-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="6fca3-103">Empezar a trabajar con el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="6fca3-103">Get started with the BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="6fca3-104">En esta sección proporciona información general del adaptador, los requisitos previos y los temas para los usuarios que trabajan con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fca3-104">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="6fca3-105">Describe las características de [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] y las distintas operaciones que se pueden realizar en el sistema SAP mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6fca3-105">It discusses the features of [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] and the different operations that can be performed on the SAP system using the adapter.</span></span>  

## <a name="what-is-an-adapter"></a><span data-ttu-id="6fca3-106">¿Qué es un adaptador?</span><span class="sxs-lookup"><span data-stu-id="6fca3-106">What is an adapter?</span></span> 
<span data-ttu-id="6fca3-107">Un adaptador es un componente de software que le permite enviar y recibir mensajes hacia y desde un sistema de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="6fca3-107">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="6fca3-108">El objetivo principal de diseño de adaptadores es facilitar el intercambio de documentos empresariales entre socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="6fca3-108">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="6fca3-109">Dado que cada sistema de negocio puede adherirse a protocolos y formatos de documento específico, el adaptador debe usar un mecanismo de entrega que se ajusta a los estándares ampliamente reconocidos y protocolos para proporcionar una interfaz uniforme a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6fca3-109">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="6fca3-110">Los adaptadores pueden dividirse en dos amplias categorías:</span><span class="sxs-lookup"><span data-stu-id="6fca3-110">The adapters can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="6fca3-111">**Adaptadores de LOB**.</span><span class="sxs-lookup"><span data-stu-id="6fca3-111">**LOB adapters**.</span></span> <span data-ttu-id="6fca3-112">Estos adaptadores proporcionan el modelo de programación orientada a los sistemas LOB de acceso — por ejemplo, los adaptadores de SAP o Siebel.</span><span class="sxs-lookup"><span data-stu-id="6fca3-112">Such adapters provide service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
- <span data-ttu-id="6fca3-113">**Los adaptadores de datos**.</span><span class="sxs-lookup"><span data-stu-id="6fca3-113">**Data adapters**.</span></span> <span data-ttu-id="6fca3-114">Estos adaptadores proporcionan el modelo de programación orientada a las bases de datos de acceso — por ejemplo, un adaptador para la base de datos de Oracle o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fca3-114">Such adapters provide service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="6fca3-115">Hay cinco adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6fca3-115">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="6fca3-116"> (el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="6fca3-116"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="6fca3-117"> (el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="6fca3-117"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="6fca3-118"> (el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="6fca3-118"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="6fca3-119"> (el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), incluidos [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="6fca3-119"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="6fca3-120"> (el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), incluidos [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="6fca3-120"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6fca3-121">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no está disponible para plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="6fca3-121">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="6fca3-122">Si no ya sabe cómo desea usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en su empresa, se recomienda que primero debe explorar las características y funcionalidad del adaptador se describe en [comprender el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md) .</span><span class="sxs-lookup"><span data-stu-id="6fca3-122">If you do not already know how you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] at your company, it is recommended that you start by exploring features and functionality of the adapter described in [Understand BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6fca3-123">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6fca3-123">Next steps</span></span>  
- [<span data-ttu-id="6fca3-124">Instalar RFC personalizadas para el proveedor de datos para SAP</span><span class="sxs-lookup"><span data-stu-id="6fca3-124">Install Custom RFCs for the Data Provider for SAP</span></span>](install-custom-rfcs-for-the-data-provider-for-sap.md)
  
-   [<span data-ttu-id="6fca3-125">Definición del adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="6fca3-125">Understand BizTalk Adapter for mySAP Business Suite</span></span>](understand-biztalk-adapter-for-mysap-business-suite.md)  

- [<span data-ttu-id="6fca3-126">Completar tareas RFC e IDOC en SAP</span><span class="sxs-lookup"><span data-stu-id="6fca3-126">Complete RFC and IDOC tasks on SAP</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)
  
-   [<span data-ttu-id="6fca3-127">Tutoriales del adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="6fca3-127">SAP Adapter Tutorials</span></span>](sap-adapter-tutorials.md)  