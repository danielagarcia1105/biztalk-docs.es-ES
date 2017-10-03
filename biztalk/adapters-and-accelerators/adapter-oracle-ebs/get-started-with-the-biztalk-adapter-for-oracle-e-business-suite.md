---
title: Empezar a trabajar con el adaptador de BizTalk para Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 852d5855-c58a-4fa3-8efd-6afea9e527df
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84c149c18da6d08283d0969b89a4634581b0001a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="c8510-102">Empezar a trabajar con el adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="c8510-102">Get started with the BizTalk Adapter for Oracle E-Business Suite</span></span>
<span data-ttu-id="c8510-103">Información general de los temas para los usuarios que están familiarizados con Microsoft BizTalk Adapter Pack, los requisitos previos y adaptador.</span><span class="sxs-lookup"><span data-stu-id="c8510-103">Overview of the adapter, prerequisites, and topics for users who are new to Microsoft BizTalk Adapter Pack.</span></span> <span data-ttu-id="c8510-104">Se proporciona información acerca de las características de [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] y las distintas operaciones que se pueden realizar en la base de datos de Oracle mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="c8510-104">Information is provided about the features of [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] and the different operations that can be performed on the Oracle database by using the adapter.</span></span>  
  
## <a name="what-is-an-adapter"></a><span data-ttu-id="c8510-105">¿Qué es un adaptador?</span><span class="sxs-lookup"><span data-stu-id="c8510-105">What is an adapter?</span></span>  
  
 <span data-ttu-id="c8510-106">Un adaptador es un componente de software que le permite enviar y recibir mensajes hacia y desde un sistema de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="c8510-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="c8510-107">El objetivo principal de un adaptador es facilitar el intercambio de documentos empresariales entre socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="c8510-107">The primary goal of an adapter is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="c8510-108">Dado que cada sistema de negocio puede cumplir protocolos y formatos de documento específico, el adaptador debe usar un mecanismo de entrega que cumple con los estándares más habituales y protocolos para proporcionar una interfaz uniforme a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c8510-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="c8510-109">Los adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] puede dividirse en dos amplias categorías:</span><span class="sxs-lookup"><span data-stu-id="c8510-109">The adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] can be divided into two broad categories:</span></span>  
  
-   <span data-ttu-id="c8510-110">**Los adaptadores de LOB**: adaptadores LOB proporcionan un modelo de programación orientada a los sistemas LOB de acceso — por ejemplo, los adaptadores para aplicaciones de SAP o Siebel.</span><span class="sxs-lookup"><span data-stu-id="c8510-110">**LOB adapters**: LOB adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel applications.</span></span>  
  
-   <span data-ttu-id="c8510-111">**Adaptadores de datos de**: los adaptadores de datos proporcionan un modelo de programación orientada a bases de datos de acceso, por ejemplo, los adaptadores para la base de datos de Oracle o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c8510-111">**Data adapters**: Data adapters provide a service-oriented programming model to access databases — for example, adapters for the Oracle database or SQL Server.</span></span>  
  
 <span data-ttu-id="c8510-112">Hay cinco adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c8510-112">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="c8510-113"> ([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="c8510-113"> ([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="c8510-114"> ([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="c8510-114"> ([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="c8510-115"> ([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="c8510-115"> ([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="c8510-116"> ([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="c8510-116"> ([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="c8510-117"> ([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="c8510-117"> ([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c8510-118">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no está disponible para plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c8510-118">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
 <span data-ttu-id="c8510-119">Si está familiarizado con la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], le recomendamos comience por explorar las características y funcionalidad del adaptador se describe en [comprender el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="c8510-119">If you are new to the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], then we recommend you start by exploring the features and functionality of the adapter described in [Understand BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8510-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c8510-120">In this section</span></span>  
  
-   [<span data-ttu-id="c8510-121">Comprender el adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="c8510-121">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)  
  
-   [<span data-ttu-id="c8510-122">Tutorial: Presentar datos de Oracle E-Business Suite en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8510-122">Tutorial: Presenting data from Oracle E-Business Suite on a SharePoint Site</span></span>](Tutorial:%20Presenting%20Data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)
  
- [<span data-ttu-id="c8510-123">Solucionar problemas del adaptador de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="c8510-123">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)