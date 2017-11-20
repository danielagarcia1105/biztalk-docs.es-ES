---
title: Las operaciones que son compatibles con el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP
- operations, performing
ms.assetid: d78dbeb8-9dab-4a71-982e-f7ada51472e8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 014b0fc6158c151d510152550c0093f6ffa9031b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-oracle-database-adapter"></a><span data-ttu-id="ccf17-102">Las operaciones que son compatibles con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-102">What operations are supported by the Oracle Database adapter</span></span>
<span data-ttu-id="ccf17-103">Los clientes de adaptador pueden realizar operaciones en la base de datos de Oracle mediante la creación de proyectos de BizTalk, mediante el modelo de canal WCF o mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ccf17-103">Adapter clients can perform operations on the Oracle database by creating BizTalk projects, by using the WCF channel model, or by using the WCF service model.</span></span> <span data-ttu-id="ccf17-104">La [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ccf17-104">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="ccf17-105">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="ccf17-105">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="ccf17-106">Si es necesario recibir una respuesta, se devuelve en un mensaje SOAP en el mismo canal.</span><span class="sxs-lookup"><span data-stu-id="ccf17-106">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="ccf17-107">Para obtener información sobre la estructura del mensaje y la acción de SOAP asociada a cada operación, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="ccf17-107">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="ccf17-108">Esta sección proporciona información acerca de las operaciones admitidas en la base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccf17-108">This section provides information about the operations supported on the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccf17-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ccf17-109">In This Section</span></span>  
  
-   [<span data-ttu-id="ccf17-110">Realizar básicas Insert, Update, Delete y las operaciones Select en las tablas de Oracle y vistas</span><span class="sxs-lookup"><span data-stu-id="ccf17-110">Performing Basic Insert, Update, Delete, and Select Operations on Oracle Tables and Views</span></span>](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)  
  
-   [<span data-ttu-id="ccf17-111">Operaciones en tablas y vistas que contienen datos LOB</span><span class="sxs-lookup"><span data-stu-id="ccf17-111">Operations on Tables and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)  
  
-   [<span data-ttu-id="ccf17-112">Operaciones en funciones y procedimientos almacenados en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-112">Operations on Functions and Stored Procedures in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-stored-procedures-in-oracle-database.md)  
  
-   [<span data-ttu-id="ccf17-113">Operaciones en funciones y procedimientos con parámetros REF CURSOR en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-113">Operations on Functions and Procedures with REF CURSOR Parameters in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/ref-cursor-parameters-in-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="ccf17-114">Operaciones en funciones y procedimientos con tipos de registros de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-114">Operations on Functions and Procedures with RECORD Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md)  
  
-   [<span data-ttu-id="ccf17-115">Operaciones en tablas con tipos de datos BFILE</span><span class="sxs-lookup"><span data-stu-id="ccf17-115">Operations on Tables With BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="ccf17-116">Operaciones en sinónimos en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-116">Operations on Synonyms in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)  
  
-   [<span data-ttu-id="ccf17-117">Operación SQLEXECUTE en base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-117">SQLEXECUTE Operation in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)  
  
-   [<span data-ttu-id="ccf17-118">Realizar operaciones compuestas en base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-118">Performing Composite Operations in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)  
  
-   [<span data-ttu-id="ccf17-119">Soporte para recibir mensajes de cambio de datos basados en el sondeo en base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-119">Support for Receiving Polling-based Data-changed Messages in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)  
  
-   [<span data-ttu-id="ccf17-120">Consideraciones para la recepción de base de datos modificados notificaciones mediante el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-120">Considerations for Receiving Database Change Notifications Using the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="ccf17-121">Compatibilidad con tipos definidos por el usuario de Oracle en base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-121">Support for Oracle User-Defined Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="ccf17-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccf17-122">See Also</span></span>  
 [<span data-ttu-id="ccf17-123">Información general sobre el adaptador de BizTalk para base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ccf17-123">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)