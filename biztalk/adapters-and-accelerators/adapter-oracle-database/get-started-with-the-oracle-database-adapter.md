---
title: Empezar a trabajar con el adaptador de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, about
- data adapter
- LOB adapter
ms.assetid: ed5b3510-11c4-4b10-bf85-c4066f3f80df
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daead7b52c17fe5a045d6681a7aa957aaa23133c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966861"
---
# <a name="get-started-with-the-oracle-database-adapter"></a><span data-ttu-id="dcea9-102">Empezar a trabajar con el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="dcea9-102">Get started with the Oracle Database adapter</span></span>
<span data-ttu-id="dcea9-103">En esta sección proporciona información general del adaptador, los requisitos previos y los temas para los usuarios que trabajan con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcea9-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="dcea9-104">Describe las características de [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] y las distintas operaciones que se pueden realizar en la base de datos de Oracle mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="dcea9-104">It discusses the features of [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] and the different operations that can be performed on the Oracle database using the adapter.</span></span>  
  
 <span data-ttu-id="dcea9-105">¿Qué es un adaptador?</span><span class="sxs-lookup"><span data-stu-id="dcea9-105">What is an adapter?</span></span> <span data-ttu-id="dcea9-106">Un adaptador es un componente de software que le permite enviar y recibir mensajes hacia y desde un sistema de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="dcea9-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="dcea9-107">El objetivo principal de diseño de adaptadores es facilitar el intercambio de documentos empresariales entre socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="dcea9-107">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="dcea9-108">Dado que cada sistema de negocio puede respetar los protocolos y formatos de documento específico, el adaptador utiliza un mecanismo de entrega que se ajusta a protocolos y estándares comúnmente reconocidos.</span><span class="sxs-lookup"><span data-stu-id="dcea9-108">Because each business system can adhere to specific document formats and protocols, the adapter uses a delivery mechanism that conforms to commonly recognized standards and protocols.</span></span>  
  
 <span data-ttu-id="dcea9-109">Los adaptadores pueden dividirse en dos amplias categorías:</span><span class="sxs-lookup"><span data-stu-id="dcea9-109">The adapters can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="dcea9-110">**Adaptadores de LOB**.</span><span class="sxs-lookup"><span data-stu-id="dcea9-110">**LOB adapters**.</span></span> <span data-ttu-id="dcea9-111">Estos adaptadores proporcionan un modelo de programación orientada a los sistemas LOB de acceso — por ejemplo, los adaptadores de SAP o Siebel.</span><span class="sxs-lookup"><span data-stu-id="dcea9-111">Such adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
- <span data-ttu-id="dcea9-112">**Los adaptadores de datos**.</span><span class="sxs-lookup"><span data-stu-id="dcea9-112">**Data adapters**.</span></span> <span data-ttu-id="dcea9-113">Estos adaptadores proporcionan un modelo de programación orientada a las bases de datos de acceso — por ejemplo, un adaptador para la base de datos de Oracle o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dcea9-113">Such adapters provide a service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="dcea9-114">Hay cinco adaptadores en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="dcea9-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="dcea9-115"> (el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="dcea9-115"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="dcea9-116"> (el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="dcea9-116"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="dcea9-117"> (el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="dcea9-117"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="dcea9-118"> (el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), incluidos [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="dcea9-118"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="dcea9-119"> (el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), incluidos [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="dcea9-119"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="dcea9-120">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no está disponible para plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="dcea9-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="dcea9-121">Si no ya sabe cómo desea usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en su empresa, se recomienda que primero debe explorar las características y funcionalidad del adaptador se describe en [descripción del adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="dcea9-121">If you do not already know how you want to use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Understanding the BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md).</span></span>  
  
