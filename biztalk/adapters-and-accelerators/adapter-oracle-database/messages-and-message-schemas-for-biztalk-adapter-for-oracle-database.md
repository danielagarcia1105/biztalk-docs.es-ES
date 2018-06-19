---
title: Mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle | Documentos de Microsoft
description: Estructura XML de mensajes y tipos de datos utilizado por el adaptador de la base de datos de Oracle para que BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fee0a531-b1e6-4b99-bb79-45368c401395
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bda5ed06470e051dc1f0bdf4595a1539aab6e6bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214308"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="d33bc-103">Mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="d33bc-103">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>

## <a name="overview"></a><span data-ttu-id="d33bc-104">Información general</span><span class="sxs-lookup"><span data-stu-id="d33bc-104">Overview</span></span>
<span data-ttu-id="d33bc-105">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="d33bc-105">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="d33bc-106">Expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d33bc-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="d33bc-107">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="d33bc-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="d33bc-108">Si es necesario recibir una respuesta, se devuelve en un mensaje SOAP en el mismo canal.</span><span class="sxs-lookup"><span data-stu-id="d33bc-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="d33bc-109">Como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone metadatos para sus operaciones y tipos de datos mediante estándar [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mecanismos.</span><span class="sxs-lookup"><span data-stu-id="d33bc-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="d33bc-110">Las secciones de este tema describen la estructura XML de los mensajes y los tipos de datos que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] utiliza.</span><span class="sxs-lookup"><span data-stu-id="d33bc-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d33bc-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d33bc-111">In This Section</span></span>  
  
-   [<span data-ttu-id="d33bc-112">Tipos de datos de Oracle básica</span><span class="sxs-lookup"><span data-stu-id="d33bc-112">Basic Oracle Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-database/basic-oracle-data-types1.md)  
  
-   [<span data-ttu-id="d33bc-113">Esquemas de mensaje para la inserción básico, actualizar, eliminar y seleccione las operaciones en tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="d33bc-113">Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [<span data-ttu-id="d33bc-114">Esquemas de mensaje para operaciones especiales de LOB</span><span class="sxs-lookup"><span data-stu-id="d33bc-114">Message Schemas for Special LOB Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)  
  
-   [<span data-ttu-id="d33bc-115">Esquemas de mensaje para funciones y procedimientos</span><span class="sxs-lookup"><span data-stu-id="d33bc-115">Message Schemas for Functions and Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)  
  
-   [<span data-ttu-id="d33bc-116">Esquemas de mensaje para los cursores REF cursor</span><span class="sxs-lookup"><span data-stu-id="d33bc-116">Message Schemas for REF CURSORS</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)  
  
-   [<span data-ttu-id="d33bc-117">Esquemas de mensaje para tipos de registro</span><span class="sxs-lookup"><span data-stu-id="d33bc-117">Message Schemas for RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)  
  
-   [<span data-ttu-id="d33bc-118">Esquemas de mensaje para la operación SQLEXECUTE</span><span class="sxs-lookup"><span data-stu-id="d33bc-118">Message Schemas for the SQLEXECUTE Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)  
  
-   [<span data-ttu-id="d33bc-119">Esquemas de mensaje para las operaciones de sondeo</span><span class="sxs-lookup"><span data-stu-id="d33bc-119">Message Schemas for the Polling Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)  
  
-   [<span data-ttu-id="d33bc-120">Esquemas de mensaje para la operación de composición</span><span class="sxs-lookup"><span data-stu-id="d33bc-120">Message Schemas for the Composite Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)  
  
-   [<span data-ttu-id="d33bc-121">Esquemas de mensaje para la operación de notificación</span><span class="sxs-lookup"><span data-stu-id="d33bc-121">Message Schemas for the Notification Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)  
  
