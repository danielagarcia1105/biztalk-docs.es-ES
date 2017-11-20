---
title: Las operaciones que son compatibles con el adaptador de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64cd124a-5e7f-4ee8-85d3-f9540b25d766
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7236c21f1e298f2ccd4cbb97db481cbd3626d186
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="d862f-102">Las operaciones que son compatibles con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="d862f-102">What operations are supported by the Oracle E-Business Suite adapter</span></span>
## <a name="overview"></a><span data-ttu-id="d862f-103">Información general</span><span class="sxs-lookup"><span data-stu-id="d862f-103">Overview</span></span>
<span data-ttu-id="d862f-104">Los clientes de adaptador pueden realizar operaciones en Oracle E-Business Suite por:</span><span class="sxs-lookup"><span data-stu-id="d862f-104">Adapter clients can perform operations in Oracle E-Business Suite by:</span></span>  
  
-   <span data-ttu-id="d862f-105">Crear proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d862f-105">Creating BizTalk projects</span></span>  
  
-   <span data-ttu-id="d862f-106">Mediante el modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="d862f-106">Using the WCF channel model</span></span>  
  
-   <span data-ttu-id="d862f-107">Mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="d862f-107">Using the WCF service model</span></span>  
  
 <span data-ttu-id="d862f-108">La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d862f-108">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="d862f-109">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="d862f-109">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="d862f-110">Si es necesario recibir una respuesta, se devuelve en un mensaje SOAP en el mismo canal.</span><span class="sxs-lookup"><span data-stu-id="d862f-110">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="d862f-111">Para obtener información sobre la estructura del mensaje y la acción de SOAP asociada a cada operación, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="d862f-111">For information about the message structure and the SOAP action associated with each operation, see [messages and message schemas for BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
 <span data-ttu-id="d862f-112">Esta sección proporciona información acerca de las operaciones admitidas en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d862f-112">This section provides information about the operations supported in Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d862f-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d862f-113">In this section</span></span>  
  
-   [<span data-ttu-id="d862f-114">Establecer el contexto de la aplicación</span><span class="sxs-lookup"><span data-stu-id="d862f-114">Set Application Context</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)  
  
-   [<span data-ttu-id="d862f-115">Operaciones en tablas de interfaz y vistas de interfaz</span><span class="sxs-lookup"><span data-stu-id="d862f-115">Operations on Interface Tables and Interface Views</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)  
  
-   [<span data-ttu-id="d862f-116">Operaciones en las API de PL/SQL</span><span class="sxs-lookup"><span data-stu-id="d862f-116">Operations on PL/SQL APIs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-pl-sql-apis.md)  
  
-   [<span data-ttu-id="d862f-117">Operaciones en programas simultáneos</span><span class="sxs-lookup"><span data-stu-id="d862f-117">Operations on Concurrent Programs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)  
  
-   [<span data-ttu-id="d862f-118">Operaciones con conjuntos de solicitud</span><span class="sxs-lookup"><span data-stu-id="d862f-118">Operations on Request Sets</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)  
  
-   [<span data-ttu-id="d862f-119">Operaciones en tablas de interfaz, vistas de interfaz, tablas y vistas que contienen datos LOB</span><span class="sxs-lookup"><span data-stu-id="d862f-119">Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)  
  
-   [<span data-ttu-id="d862f-120">Operaciones en tablas que contienen tipos de datos BFILE</span><span class="sxs-lookup"><span data-stu-id="d862f-120">Operations on Tables That Contain BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="d862f-121">Operaciones en funciones y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="d862f-121">Operations on Functions and Stored Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)  
  
-   [<span data-ttu-id="d862f-122">Operaciones en funciones y procedimientos con parámetros REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="d862f-122">Operations on Functions and Procedures with REF CURSOR Parameters</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)  
  
-   [<span data-ttu-id="d862f-123">Operaciones en funciones y procedimientos con tipos de registro</span><span class="sxs-lookup"><span data-stu-id="d862f-123">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
-   [<span data-ttu-id="d862f-124">Operaciones en sinónimos</span><span class="sxs-lookup"><span data-stu-id="d862f-124">Operations on Synonyms</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-synonyms2.md)  
  
-   [<span data-ttu-id="d862f-125">Tiene en cuenta para recibir notificaciones de cambio de base de datos</span><span class="sxs-lookup"><span data-stu-id="d862f-125">Consideration for Receiving Database Change Notifications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="d862f-126">Compatibilidad para las llamadas entrantes mediante sondeo</span><span class="sxs-lookup"><span data-stu-id="d862f-126">Support for Inbound Calls Using Polling</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)  
  
-   [<span data-ttu-id="d862f-127">Compatibilidad con ExecuteNonQuery y ExecuteReader, ExecuteScalar operaciones</span><span class="sxs-lookup"><span data-stu-id="d862f-127">Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)  
  
-   [<span data-ttu-id="d862f-128">Compatibilidad con operaciones compuestas</span><span class="sxs-lookup"><span data-stu-id="d862f-128">Support for Composite Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)  
  
-   [<span data-ttu-id="d862f-129">Compatibilidad con tipos definidos por el usuario de Oracle</span><span class="sxs-lookup"><span data-stu-id="d862f-129">Support for Oracle User-Defined Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-oracle-user-defined-types2.md)  
  
## <a name="see-also"></a><span data-ttu-id="d862f-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d862f-130">See Also</span></span>  
[<span data-ttu-id="d862f-131">Comprender el adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="d862f-131">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)