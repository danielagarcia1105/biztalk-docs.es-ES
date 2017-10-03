---
title: Empezar a trabajar con el adaptador de BizTalk para SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c3b6e36-ddfb-4ede-adf5-b9762231224b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61a2ecd7ae8020865dff7b67fbc57388d1f15af6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-biztalk-adapter-for-sql"></a><span data-ttu-id="90359-102">Empezar a trabajar con el adaptador de BizTalk para SQL</span><span class="sxs-lookup"><span data-stu-id="90359-102">Get started with the BizTalk adapter for SQL</span></span>

  
 <span data-ttu-id="90359-103">Esta sección proporciona información general sobre el adaptador, los requisitos previos y los temas para los usuarios que están familiarizados con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90359-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="90359-104">Describe las características de [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] y las distintas operaciones que se pueden realizar en la base de datos de SQL Server mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="90359-104">It discusses the features of [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] and the different operations that can be performed on the SQL Server database by using the adapter.</span></span>  
  
 <span data-ttu-id="90359-105">¿Qué es un adaptador?</span><span class="sxs-lookup"><span data-stu-id="90359-105">What is an adapter?</span></span> <span data-ttu-id="90359-106">Un adaptador es un componente de software que le permite enviar y recibir mensajes hacia y desde un sistema de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="90359-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="90359-107">El objetivo de diseño principal de un adaptador es facilitar el intercambio de documentos empresariales entre socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="90359-107">The primary design goal of an adapter is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="90359-108">Dado que cada sistema de negocio puede cumplir protocolos y formatos de documento específico, el adaptador debe usar un mecanismo de entrega que cumple con los estándares más habituales y protocolos para proporcionar una interfaz uniforme a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="90359-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="90359-109">Los adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] puede dividirse en dos amplias categorías:</span><span class="sxs-lookup"><span data-stu-id="90359-109">The adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] can be divided into two broad categories:</span></span>  
  
-   <span data-ttu-id="90359-110">**Los adaptadores de LOB**.</span><span class="sxs-lookup"><span data-stu-id="90359-110">**LOB adapters**.</span></span> <span data-ttu-id="90359-111">Estos adaptadores proporcionan el modelo de programación orientada a los sistemas LOB de acceso — por ejemplo, los adaptadores de SAP o Siebel.</span><span class="sxs-lookup"><span data-stu-id="90359-111">Such adapters provide service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
-   <span data-ttu-id="90359-112">**Adaptadores de datos de**.</span><span class="sxs-lookup"><span data-stu-id="90359-112">**Data adapters**.</span></span> <span data-ttu-id="90359-113">Estos adaptadores proporcionan el modelo de programación orientada a bases de datos de acceso, por ejemplo, los adaptadores para la base de datos de Oracle o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="90359-113">Such adapters provide service-oriented programming model to access databases—for example, adapters for the Oracle database or SQL Server.</span></span>  
  
 <span data-ttu-id="90359-114">Hay cinco adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="90359-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="90359-115"> ([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="90359-115"> ([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90359-116">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] también está disponible fuera de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] como un adaptador independiente.</span><span class="sxs-lookup"><span data-stu-id="90359-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is also available outside the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] as a separate adapter.</span></span>  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="90359-117"> ([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="90359-117"> ([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]).</span></span>  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="90359-118"> ([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="90359-118"> ([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]).</span></span>  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="90359-119"> ([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="90359-119"> ([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]).</span></span>  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="90359-120"> ([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="90359-120"> ([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90359-121">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no está disponible para plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="90359-121">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
 <span data-ttu-id="90359-122">Si no ya sabe cómo desea usar el adaptador de SQL en su empresa, se recomienda que primero debe explorar las características y funcionalidad del adaptador se describe en [comprender el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="90359-122">If you do not already know how you want to use the SQL adapter at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Understand BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90359-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="90359-123">In This Section</span></span>  
  
-   [<span data-ttu-id="90359-124">Comprender el adaptador de BizTalk para SQL Server</span><span class="sxs-lookup"><span data-stu-id="90359-124">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)  
  
-   [<span data-ttu-id="90359-125">Tutoriales del adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="90359-125">SQL Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)  
  
-   [<span data-ttu-id="90359-126">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="90359-126">Frequently Asked Questions</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-faqs.md)