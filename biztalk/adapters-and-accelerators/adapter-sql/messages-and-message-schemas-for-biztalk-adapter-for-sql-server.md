---
title: Mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server | Documentos de Microsoft
description: Estructura XML de mensajes y tipos de datos utilizado por el adaptador de SQL Server para que BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e95c6342-5420-4fb8-9b41-7c87d27b5b68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b1e45f0a20500253e2ca831138a21efa24df3c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222380"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-sql-server"></a><span data-ttu-id="50e34-103">Mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server</span><span class="sxs-lookup"><span data-stu-id="50e34-103">Messages and Message Schemas for BizTalk Adapter for SQL Server</span></span>

## <a name="overview"></a><span data-ttu-id="50e34-104">Información general</span><span class="sxs-lookup"><span data-stu-id="50e34-104">Overview</span></span>
<span data-ttu-id="50e34-105">El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="50e34-105">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="50e34-106">Expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="50e34-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="50e34-107">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="50e34-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="50e34-108">Si es necesario recibir una respuesta, se devuelve en un mensaje SOAP en el mismo canal.</span><span class="sxs-lookup"><span data-stu-id="50e34-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="50e34-109">Como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone metadatos para sus operaciones y tipos de datos mediante estándar [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mecanismos.</span><span class="sxs-lookup"><span data-stu-id="50e34-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="50e34-110">Las secciones de este tema describen la estructura XML de los mensajes y los tipos de datos que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utiliza.</span><span class="sxs-lookup"><span data-stu-id="50e34-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50e34-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="50e34-111">In This Section</span></span>  
  
-   [<span data-ttu-id="50e34-112">Tipos de datos básicos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="50e34-112">Basic SQL Server Data Types</span></span>](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)  
  
-   [<span data-ttu-id="50e34-113">Esquemas de mensaje para insertar, actualizar, eliminar y seleccione las operaciones en tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="50e34-113">Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [<span data-ttu-id="50e34-114">Esquemas de mensaje para los procedimientos y funciones</span><span class="sxs-lookup"><span data-stu-id="50e34-114">Message Schemas for Procedures and Functions</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)  
  
-   [<span data-ttu-id="50e34-115">Esquemas de mensaje para las operaciones de TypedPolling y sondeo</span><span class="sxs-lookup"><span data-stu-id="50e34-115">Message Schemas for the Polling and TypedPolling Operations</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)  
  
-   [<span data-ttu-id="50e34-116">Esquemas de mensaje de notificación de consulta</span><span class="sxs-lookup"><span data-stu-id="50e34-116">Message Schemas for Query Notification</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)  
  
-   [<span data-ttu-id="50e34-117">Esquemas de mensaje para operaciones compuestas</span><span class="sxs-lookup"><span data-stu-id="50e34-117">Message Schemas for Composite Operations</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)  
  
-   [<span data-ttu-id="50e34-118">Esquemas de mensaje para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="50e34-118">Message Schemas for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-sql/executenonquery-executereader-and-executescalar-message-schemas-in-sql.md)  
  
