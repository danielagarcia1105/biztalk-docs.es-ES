---
title: Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite | Documentos de Microsoft
description: Estructura XML de mensajes y tipos de datos utilizado por el adaptador de Oracle EBS para BizTalk Server
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4434b4d4-fbe0-4692-81a5-9883c9a77cf6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9069e5bf83f323726da7c8b08b9f5cc7ca6ccd85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="2a25d-103">Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="2a25d-103">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>

## <a name="overview"></a><span data-ttu-id="2a25d-104">Información general</span><span class="sxs-lookup"><span data-stu-id="2a25d-104">Overview</span></span>
<span data-ttu-id="2a25d-105">El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="2a25d-105">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="2a25d-106">Expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2a25d-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="2a25d-107">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="2a25d-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="2a25d-108">Si es necesario recibir una respuesta, se devuelve en un mensaje SOAP en el mismo canal.</span><span class="sxs-lookup"><span data-stu-id="2a25d-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="2a25d-109">Como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone metadatos para sus operaciones y tipos de datos mediante estándar [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mecanismos.</span><span class="sxs-lookup"><span data-stu-id="2a25d-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="2a25d-110">Las secciones de este tema describen la estructura XML de los mensajes y los tipos de datos que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] utiliza.</span><span class="sxs-lookup"><span data-stu-id="2a25d-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a25d-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2a25d-111">In This Section</span></span>  
  
-   [<span data-ttu-id="2a25d-112">Tipos de datos de Oracle básica</span><span class="sxs-lookup"><span data-stu-id="2a25d-112">Basic Oracle Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/basic-oracle-data-types2.md)  
  
-   [<span data-ttu-id="2a25d-113">Esquemas de mensaje para insertar, actualizar, eliminar y seleccionar operaciones</span><span class="sxs-lookup"><span data-stu-id="2a25d-113">Message Schemas for Insert, Update, Delete, and Select Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)  
  
-   [<span data-ttu-id="2a25d-114">Esquemas de mensaje para los procedimientos almacenados, funciones y las API de PL/SQL</span><span class="sxs-lookup"><span data-stu-id="2a25d-114">Message Schemas for Stored Procedures, Functions, and PL/SQL APIs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-stored-procedures-functions-and-pl-sql-apis.md)  
  
-   [<span data-ttu-id="2a25d-115">Esquemas de mensaje para programas simultáneos</span><span class="sxs-lookup"><span data-stu-id="2a25d-115">Message Schemas for Concurrent Programs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)  
  
-   [<span data-ttu-id="2a25d-116">Esquemas de mensaje para conjuntos de solicitudes</span><span class="sxs-lookup"><span data-stu-id="2a25d-116">Message Schemas for Request Sets</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)  
  
-   [<span data-ttu-id="2a25d-117">Esquemas de mensaje para operaciones especiales de LOB</span><span class="sxs-lookup"><span data-stu-id="2a25d-117">Message Schemas for Special LOB Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)  
  
-   [<span data-ttu-id="2a25d-118">Esquemas de mensaje para las operaciones de sondeo</span><span class="sxs-lookup"><span data-stu-id="2a25d-118">Message Schemas for the Polling Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md)  
  
-   [<span data-ttu-id="2a25d-119">Esquemas de mensaje para la operación de notificación</span><span class="sxs-lookup"><span data-stu-id="2a25d-119">Message Schemas for the Notification Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-notification-operation2.md)  
  
-   [<span data-ttu-id="2a25d-120">Esquemas de mensaje para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="2a25d-120">Message Schemas for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/executenonquery-executereader-and-executescalar-message-schemas.md)  
  
-   [<span data-ttu-id="2a25d-121">Esquemas de mensaje para la operación de composición</span><span class="sxs-lookup"><span data-stu-id="2a25d-121">Message Schemas for the Composite Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)  
  