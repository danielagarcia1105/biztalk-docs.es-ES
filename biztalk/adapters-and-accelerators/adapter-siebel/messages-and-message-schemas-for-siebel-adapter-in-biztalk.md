---
title: Mensajes y esquemas de mensaje para el adaptador de BizTalk para aplicaciones Siebel eBusiness | Documentos de Microsoft
description: "Estructura XML de mensajes y tipos de datos utilizado por el adaptador de Siebel en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b4da884-89b0-4ab1-a728-c5569088a993
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 294662793fc8103813b582d1b0d84db4447b0e7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="5ac70-103">Mensajes y esquemas de mensaje para el adaptador de BizTalk para Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="5ac70-103">Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications</span></span>

## <a name="overview"></a><span data-ttu-id="5ac70-104">Información general</span><span class="sxs-lookup"><span data-stu-id="5ac70-104">Overview</span></span>
<span data-ttu-id="5ac70-105">El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="5ac70-105">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="5ac70-106">Expone las operaciones que las aplicaciones pueden invocar en un sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="5ac70-106">It exposes operations that applications can invoke on a Siebel system.</span></span> <span data-ttu-id="5ac70-107">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="5ac70-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="5ac70-108">Si es necesario recibir una respuesta, se devuelve en un mensaje SOAP en el mismo canal.</span><span class="sxs-lookup"><span data-stu-id="5ac70-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="5ac70-109">Como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone metadatos para sus operaciones y tipos de datos mediante estándar [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mecanismos.</span><span class="sxs-lookup"><span data-stu-id="5ac70-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="5ac70-110">Las secciones de este tema describen la estructura XML de los mensajes y los tipos de datos que el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] utiliza.</span><span class="sxs-lookup"><span data-stu-id="5ac70-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ac70-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5ac70-111">In This Section</span></span>  
  
-   [<span data-ttu-id="5ac70-112">Tipos de datos básicos de Siebel</span><span class="sxs-lookup"><span data-stu-id="5ac70-112">Basic Siebel Data Types</span></span>](basic-siebel-data-types.md)  
  
-   [<span data-ttu-id="5ac70-113">Esquemas de mensaje para las operaciones de componentes empresariales</span><span class="sxs-lookup"><span data-stu-id="5ac70-113">Message Schemas for Business Component Operations</span></span>](message-schemas-for-business-component-operations.md)  
  
-   [<span data-ttu-id="5ac70-114">Esquemas de mensaje para las operaciones de servicio de negocios</span><span class="sxs-lookup"><span data-stu-id="5ac70-114">Message Schemas for Business Service Operations</span></span>](message-schemas-for-business-service-operations.md)  
  
-   [<span data-ttu-id="5ac70-115">Esquema de mensaje para las operaciones de lista de selección</span><span class="sxs-lookup"><span data-stu-id="5ac70-115">Message Schema for Picklist Operations</span></span>](message-schema-for-picklist-operations.md)  
  
-   [<span data-ttu-id="5ac70-116">Compatibilidad de versiones de mensaje</span><span class="sxs-lookup"><span data-stu-id="5ac70-116">Message Versioning Support</span></span>](message-versioning-support2.md)  
  
