---
title: Comprender el adaptador de BizTalk para base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF LOB Adapter SDK
- features of Oracle database adapter
- table
- adapter client
- service model
- WCF
- artifacts
- database tables
- adapters, features
- Windows Communication Foundation
- adapter features
- channel model
ms.assetid: a8691957-0430-4cba-83f8-b60c21a86849
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb2d3603bb6d7c64d355c88420167344f564ddd8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="6d137-102">Comprender el adaptador de BizTalk para base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="6d137-102">Understand the BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="6d137-103">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="6d137-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="6d137-104">Los adaptadores proporcionan las siguientes ventajas a los clientes:</span><span class="sxs-lookup"><span data-stu-id="6d137-104">The adapters provide the following advantages to clients:</span></span>  
  
-   <span data-ttu-id="6d137-105">**Experiencia en tiempo de diseño coherente**.</span><span class="sxs-lookup"><span data-stu-id="6d137-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="6d137-106">Los adaptadores proporcionan una experiencia en tiempo de diseño común y fácil de usar para la exploración, búsqueda y recuperación de metadatos de artefactos de LOB.</span><span class="sxs-lookup"><span data-stu-id="6d137-106">The adapters provide a common and user-friendly design-time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
-   <span data-ttu-id="6d137-107">**Opciones de programación de variados**.</span><span class="sxs-lookup"><span data-stu-id="6d137-107">**Varied programming options**.</span></span> <span data-ttu-id="6d137-108">Los adaptadores proporcionan servicios Web ADO.NET, modelo de servicio de una opción de modelo de programación incluido el modelo de canal de Windows Communication Foundation (WCF), WCF o BizTalk admite modelos.</span><span class="sxs-lookup"><span data-stu-id="6d137-108">The adapters provide a choice of programming model including the Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
-   <span data-ttu-id="6d137-109">**Uniformes experiencia a través de LOB**.</span><span class="sxs-lookup"><span data-stu-id="6d137-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="6d137-110">Los adaptadores estandarización sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]y por lo tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.</span><span class="sxs-lookup"><span data-stu-id="6d137-110">The adapters standardize on using WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
 <span data-ttu-id="6d137-111">Como se mencionó, los adaptadores se generan en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d137-111">As mentioned, the adapters are built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="6d137-112">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones cliente como el servidor BizTalk Server y Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="6d137-112">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="6d137-113">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Alinee la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de adaptadores de integración como canales de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6d137-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="6d137-114">Para obtener más información sobre la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], consulte el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación.</span><span class="sxs-lookup"><span data-stu-id="6d137-114">For more information about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], see the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentation.</span></span> <span data-ttu-id="6d137-115">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación está instalada junto con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], normalmente en \<unidad de instalación\>: \Program archivos\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.</span><span class="sxs-lookup"><span data-stu-id="6d137-115">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentation is installed along with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], typically under \<installation drive\>:\Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.</span></span>  
  
 <span data-ttu-id="6d137-116">Para llevar a cabo operaciones en una base de datos de Oracle, los clientes de adaptador deben tener acceso a tablas relevantes, funciones y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="6d137-116">To perform operations on an Oracle database, adapter clients must have access to relevant tables, functions, and procedures.</span></span> <span data-ttu-id="6d137-117">Tablas de base de datos son la unidad básica de almacenamiento en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="6d137-117">Database tables are the basic unit of storage in the Oracle database.</span></span> <span data-ttu-id="6d137-118">Las aplicaciones externas pueden agregar o quitar datos de una tabla mediante instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="6d137-118">External applications can add or remove data from a table by using SQL statements.</span></span> <span data-ttu-id="6d137-119">Las aplicaciones también pueden tener acceso a datos en las tablas mediante el uso de vistas, funciones y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="6d137-119">Applications can also access data in the tables by using views, functions, and procedures.</span></span> <span data-ttu-id="6d137-120">Con [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], los clientes de adaptador pueden examinar los artefactos, como tablas, procedimientos, paquetes, vistas y otros elementos de este tipo en una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="6d137-120">With [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], adapter clients can browse the artifacts such as tables, procedures, packages, views, and other such items in an Oracle database.</span></span> <span data-ttu-id="6d137-121">Los clientes de adaptador pueden seleccionar los artefactos que necesitan para su solución y recuperan metadatos para los artefactos.</span><span class="sxs-lookup"><span data-stu-id="6d137-121">Adapter clients can select the artifacts they require for their solution and retrieve metadata for those artifacts.</span></span> <span data-ttu-id="6d137-122">Esto permite a los usuarios tener acceso y ejecutar las operaciones en los artefactos en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="6d137-122">This enables users to access and execute the operations on the artifacts in the Oracle database.</span></span>  
  
 <span data-ttu-id="6d137-123">En esta sección se enumera las características de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d137-123">This section lists the features of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d137-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6d137-124">In This Section</span></span>  
  
-   [<span data-ttu-id="6d137-125">Información general sobre el adaptador de BizTalk para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="6d137-125">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="6d137-126">Características clave en el adaptador de BizTalk para base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="6d137-126">Key Features in BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="6d137-127">Limitaciones del adaptador de BizTalk para base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="6d137-127">Limitations of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="6d137-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d137-128">See Also</span></span>  
[<span data-ttu-id="6d137-129">Introducción a BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6d137-129">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)