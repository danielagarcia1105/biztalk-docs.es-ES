---
title: Las operaciones que son compatibles con el adaptador de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64cd124a-5e7f-4ee8-85d3-f9540b25d766
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07ad676d737fffc45898c31f68d0895fc6919b63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984053"
---
# <a name="what-operations-are-supported-by-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="b7f5a-102">Las operaciones que son compatibles con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="b7f5a-102">What operations are supported by the Oracle E-Business Suite adapter</span></span>
## <a name="overview"></a><span data-ttu-id="b7f5a-103">Información general</span><span class="sxs-lookup"><span data-stu-id="b7f5a-103">Overview</span></span>
<span data-ttu-id="b7f5a-104">Los clientes del adaptador pueden realizar operaciones en Oracle E-Business Suite por:</span><span class="sxs-lookup"><span data-stu-id="b7f5a-104">Adapter clients can perform operations in Oracle E-Business Suite by:</span></span>  
  
- <span data-ttu-id="b7f5a-105">Crear proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b7f5a-105">Creating BizTalk projects</span></span>  
  
- <span data-ttu-id="b7f5a-106">Mediante el modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="b7f5a-106">Using the WCF channel model</span></span>  
  
- <span data-ttu-id="b7f5a-107">Mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="b7f5a-107">Using the WCF service model</span></span>  
  
  <span data-ttu-id="b7f5a-108">La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b7f5a-108">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="b7f5a-109">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="b7f5a-109">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="b7f5a-110">Si se requiere una respuesta, se devuelve en un mensaje SOAP a través del canal mismo.</span><span class="sxs-lookup"><span data-stu-id="b7f5a-110">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="b7f5a-111">Para obtener información acerca de la estructura del mensaje y la acción de SOAP asociada con cada operación, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="b7f5a-111">For information about the message structure and the SOAP action associated with each operation, see [messages and message schemas for BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
  <span data-ttu-id="b7f5a-112">Esta sección proporciona información acerca de las operaciones admitidas en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7f5a-112">This section provides information about the operations supported in Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7f5a-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b7f5a-113">In this section</span></span>  
  
-   [<span data-ttu-id="b7f5a-114">Establecer el contexto de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b7f5a-114">Set Application Context</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)  
  
-   [<span data-ttu-id="b7f5a-115">Operaciones en tablas y vistas de interfaz</span><span class="sxs-lookup"><span data-stu-id="b7f5a-115">Operations on Interface Tables and Interface Views</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)  
  
-   [<span data-ttu-id="b7f5a-116">Operaciones en las API de PL/SQL</span><span class="sxs-lookup"><span data-stu-id="b7f5a-116">Operations on PL/SQL APIs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-pl-sql-apis.md)  
  
-   [<span data-ttu-id="b7f5a-117">Operaciones en programas simultáneos</span><span class="sxs-lookup"><span data-stu-id="b7f5a-117">Operations on Concurrent Programs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)  
  
-   [<span data-ttu-id="b7f5a-118">Operaciones en conjuntos de solicitud</span><span class="sxs-lookup"><span data-stu-id="b7f5a-118">Operations on Request Sets</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)  
  
-   [<span data-ttu-id="b7f5a-119">Operaciones en tablas y vistas de interfaz, tablas y vistas que contienen datos de LOB</span><span class="sxs-lookup"><span data-stu-id="b7f5a-119">Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)  
  
-   [<span data-ttu-id="b7f5a-120">Operaciones en tablas que contienen tipos de datos BFILE</span><span class="sxs-lookup"><span data-stu-id="b7f5a-120">Operations on Tables That Contain BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="b7f5a-121">Operaciones en funciones y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="b7f5a-121">Operations on Functions and Stored Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)  
  
-   [<span data-ttu-id="b7f5a-122">Operaciones en funciones y procedimientos con parámetros de REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="b7f5a-122">Operations on Functions and Procedures with REF CURSOR Parameters</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)  
  
-   [<span data-ttu-id="b7f5a-123">Operaciones en funciones y procedimientos con tipos RECORD</span><span class="sxs-lookup"><span data-stu-id="b7f5a-123">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
-   [<span data-ttu-id="b7f5a-124">Operaciones en sinónimos</span><span class="sxs-lookup"><span data-stu-id="b7f5a-124">Operations on Synonyms</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-synonyms2.md)  
  
-   [<span data-ttu-id="b7f5a-125">Consideración para recibir notificaciones de cambio de base de datos</span><span class="sxs-lookup"><span data-stu-id="b7f5a-125">Consideration for Receiving Database Change Notifications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="b7f5a-126">Compatibilidad para las llamadas entrantes mediante sondeo</span><span class="sxs-lookup"><span data-stu-id="b7f5a-126">Support for Inbound Calls Using Polling</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)  
  
-   [<span data-ttu-id="b7f5a-127">Compatibilidad para las operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="b7f5a-127">Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)  
  
-   [<span data-ttu-id="b7f5a-128">Compatibilidad con las operaciones compuestas</span><span class="sxs-lookup"><span data-stu-id="b7f5a-128">Support for Composite Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)  
  
-   [<span data-ttu-id="b7f5a-129">Compatibilidad con tipos definidos por el usuario de Oracle</span><span class="sxs-lookup"><span data-stu-id="b7f5a-129">Support for Oracle User-Defined Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-oracle-user-defined-types2.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7f5a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7f5a-130">See Also</span></span>  
[<span data-ttu-id="b7f5a-131">El adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="b7f5a-131">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)