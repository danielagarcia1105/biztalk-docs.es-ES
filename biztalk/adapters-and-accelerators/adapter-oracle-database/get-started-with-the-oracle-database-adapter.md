---
title: Empezar a trabajar con el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, about
- data adapter
- LOB adapter
ms.assetid: ed5b3510-11c4-4b10-bf85-c4066f3f80df
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7aa93ae3f64f4f2f914a51508a3a8dee4e3be41
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-oracle-database-adapter"></a><span data-ttu-id="995d8-102">Empezar a trabajar con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="995d8-102">Get started with the Oracle Database adapter</span></span>
<span data-ttu-id="995d8-103">Esta sección proporciona información general sobre el adaptador, los requisitos previos y los temas para los usuarios que están familiarizados con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="995d8-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="995d8-104">Describe las características de [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] y las distintas operaciones que se pueden realizar en la base de datos de Oracle mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="995d8-104">It discusses the features of [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] and the different operations that can be performed on the Oracle database using the adapter.</span></span>  
  
 <span data-ttu-id="995d8-105">¿Qué es un adaptador?</span><span class="sxs-lookup"><span data-stu-id="995d8-105">What is an adapter?</span></span> <span data-ttu-id="995d8-106">Un adaptador es un componente de software que le permite enviar y recibir mensajes hacia y desde un sistema de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="995d8-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="995d8-107">El objetivo de diseño principal de adaptadores es facilitar el intercambio de documentos empresariales entre socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="995d8-107">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="995d8-108">Dado que cada sistema de negocio puede cumplir protocolos y formatos de documento específico, el adaptador utiliza un mecanismo de entrega que cumple con los estándares más habituales y protocolos.</span><span class="sxs-lookup"><span data-stu-id="995d8-108">Because each business system can adhere to specific document formats and protocols, the adapter uses a delivery mechanism that conforms to commonly recognized standards and protocols.</span></span>  
  
 <span data-ttu-id="995d8-109">Los adaptadores se pueden dividir en dos amplias categorías:</span><span class="sxs-lookup"><span data-stu-id="995d8-109">The adapters can be divided into two broad categories:</span></span>  
  
-   <span data-ttu-id="995d8-110">**Los adaptadores de LOB**.</span><span class="sxs-lookup"><span data-stu-id="995d8-110">**LOB adapters**.</span></span> <span data-ttu-id="995d8-111">Estos adaptadores proporcionan un modelo de programación orientada a los sistemas LOB de acceso — por ejemplo, los adaptadores de SAP o Siebel.</span><span class="sxs-lookup"><span data-stu-id="995d8-111">Such adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
-   <span data-ttu-id="995d8-112">**Adaptadores de datos de**.</span><span class="sxs-lookup"><span data-stu-id="995d8-112">**Data adapters**.</span></span> <span data-ttu-id="995d8-113">Estos adaptadores proporcionan un modelo de programación orientada a bases de datos de acceso, por ejemplo, un adaptador para la base de datos de Oracle o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="995d8-113">Such adapters provide a service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
 <span data-ttu-id="995d8-114">Hay cinco adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="995d8-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="995d8-115">(el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="995d8-115"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="995d8-116">(el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="995d8-116"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="995d8-117">(el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="995d8-117"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="995d8-118">(el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), incluido [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="995d8-118"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="995d8-119">(el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), incluido [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="995d8-119"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="995d8-120">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no está disponible para plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="995d8-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
 <span data-ttu-id="995d8-121">Si no ya sabe cómo desea usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en su empresa, se recomienda que primero debe explorar las características y funcionalidad del adaptador se describe en [descripción el adaptador de BizTalk de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="995d8-121">If you do not already know how you want to use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Understanding the BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md).</span></span>  
  
