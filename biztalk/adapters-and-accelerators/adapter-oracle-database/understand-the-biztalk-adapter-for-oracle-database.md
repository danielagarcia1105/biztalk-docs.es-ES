---
title: Comprender el adaptador de BizTalk para Oracle Database | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fda25d77571a3c0128317a557e5f9d15bbc472
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994621"
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="42761-102">Comprender el adaptador de BizTalk para Oracle Database</span><span class="sxs-lookup"><span data-stu-id="42761-102">Understand the BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="42761-103">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="42761-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="42761-104">Los adaptadores proporcionan las siguientes ventajas a los clientes:</span><span class="sxs-lookup"><span data-stu-id="42761-104">The adapters provide the following advantages to clients:</span></span>  
  
- <span data-ttu-id="42761-105">**Experiencia en tiempo de diseño coherente**.</span><span class="sxs-lookup"><span data-stu-id="42761-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="42761-106">Los adaptadores proporcionan una experiencia en tiempo de diseño comunes y fácil de usar para explorar, buscar y recuperar los metadatos de artefactos de LOB.</span><span class="sxs-lookup"><span data-stu-id="42761-106">The adapters provide a common and user-friendly design-time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
- <span data-ttu-id="42761-107">**Variar las opciones de programación**.</span><span class="sxs-lookup"><span data-stu-id="42761-107">**Varied programming options**.</span></span> <span data-ttu-id="42761-108">Los adaptadores proporcionan una elección del modelo de programación incluido el modelo de canal de Windows Communication Foundation (WCF), WCF del servicio servicios Web de model, ADO.NET, o modelos admitidos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="42761-108">The adapters provide a choice of programming model including the Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
- <span data-ttu-id="42761-109">**Uniforme de experiencia en LOB**.</span><span class="sxs-lookup"><span data-stu-id="42761-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="42761-110">Los adaptadores de estandarizan sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]y por lo tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.</span><span class="sxs-lookup"><span data-stu-id="42761-110">The adapters standardize on using WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
  <span data-ttu-id="42761-111">Como se mencionó, los adaptadores se crean sobre el SDK de adaptador LOB de WCF.</span><span class="sxs-lookup"><span data-stu-id="42761-111">As mentioned, the adapters are built on top of the WCF LOB Adapter SDK.</span></span> <span data-ttu-id="42761-112">El SDK de adaptador LOB de WCF proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones de cliente como el servidor BizTalk Server y Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="42761-112">The WCF LOB Adapter SDK provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="42761-113">El SDK de adaptador LOB de WCF se alinea a la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de los adaptadores de integración como canales de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="42761-113">The WCF LOB Adapter SDK aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="42761-114">Para obtener más información sobre el SDK de adaptador LOB de WCF, vea [documentación del SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span><span class="sxs-lookup"><span data-stu-id="42761-114">For more information about the WCF LOB Adapter SDK, see [WCF LOB Adapter SDK documentation](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span></span>
  
  <span data-ttu-id="42761-115">Para llevar a cabo operaciones en una base de datos de Oracle, los clientes del adaptador deben tener acceso a las tablas relevantes, funciones y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="42761-115">To perform operations on an Oracle database, adapter clients must have access to relevant tables, functions, and procedures.</span></span> <span data-ttu-id="42761-116">Las tablas de base de datos son la unidad básica de almacenamiento en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="42761-116">Database tables are the basic unit of storage in the Oracle database.</span></span> <span data-ttu-id="42761-117">Las aplicaciones externas se pueden agregar o quitar datos de una tabla mediante el uso de instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="42761-117">External applications can add or remove data from a table by using SQL statements.</span></span> <span data-ttu-id="42761-118">Las aplicaciones también pueden tener acceso a datos en las tablas mediante el uso de vistas, funciones y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="42761-118">Applications can also access data in the tables by using views, functions, and procedures.</span></span> <span data-ttu-id="42761-119">Con [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], los clientes del adaptador pueden examinar los artefactos, como tablas, procedimientos, paquetes, vistas y otros elementos de este tipo en una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="42761-119">With [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], adapter clients can browse the artifacts such as tables, procedures, packages, views, and other such items in an Oracle database.</span></span> <span data-ttu-id="42761-120">Los clientes del adaptador pueden seleccionar los artefactos que se requieren para su solución y recuperar metadatos para aquellos artefactos.</span><span class="sxs-lookup"><span data-stu-id="42761-120">Adapter clients can select the artifacts they require for their solution and retrieve metadata for those artifacts.</span></span> <span data-ttu-id="42761-121">Esto permite a los usuarios obtener acceso a ejecutar las operaciones en los artefactos en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="42761-121">This enables users to access and execute the operations on the artifacts in the Oracle database.</span></span>  
  
  <span data-ttu-id="42761-122">En esta sección se enumera las características de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42761-122">This section lists the features of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="42761-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="42761-123">In This Section</span></span>  
  
-   [<span data-ttu-id="42761-124">Información general sobre el adaptador de BizTalk para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="42761-124">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="42761-125">Características clave en el adaptador de BizTalk para Oracle Database</span><span class="sxs-lookup"><span data-stu-id="42761-125">Key Features in BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="42761-126">Limitaciones del adaptador de BizTalk para Oracle Database</span><span class="sxs-lookup"><span data-stu-id="42761-126">Limitations of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="42761-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="42761-127">See Also</span></span>  
[<span data-ttu-id="42761-128">Introducción a BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="42761-128">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)