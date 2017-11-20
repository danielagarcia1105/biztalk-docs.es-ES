---
title: Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite | Documentos de Microsoft
description: Estructura XML de mensajes y tipos de datos utilizado por el adaptador de mySAP para BizTalk Server
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75ea5c27-8297-47bf-bcfd-503870349189
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9db6ec6b0fbea7ce5c8f90158126d52cbc7530ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="4f4af-103">Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="4f4af-103">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>

## <a name="overview"></a><span data-ttu-id="4f4af-104">Información general</span><span class="sxs-lookup"><span data-stu-id="4f4af-104">Overview</span></span>
<span data-ttu-id="4f4af-105">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="4f4af-105">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="4f4af-106">Expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4f4af-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="4f4af-107">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="4f4af-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="4f4af-108">Si es necesario recibir una respuesta, se devuelve en un mensaje SOAP en el mismo canal.</span><span class="sxs-lookup"><span data-stu-id="4f4af-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="4f4af-109">Como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone metadatos para sus operaciones y tipos de datos mediante estándar [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mecanismos.</span><span class="sxs-lookup"><span data-stu-id="4f4af-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="4f4af-110">Las secciones de este tema describen la estructura XML de los mensajes y los tipos de datos que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza.</span><span class="sxs-lookup"><span data-stu-id="4f4af-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f4af-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4f4af-111">In This Section</span></span>  
  
-   [<span data-ttu-id="4f4af-112">Tipos de datos SAP básica</span><span class="sxs-lookup"><span data-stu-id="4f4af-112">Basic SAP Data Types</span></span>](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)  
  
-   [<span data-ttu-id="4f4af-113">Asignación de tipos de datos para las solicitudes de cambio personalizadas</span><span class="sxs-lookup"><span data-stu-id="4f4af-113">Data Type Mapping for Custom RFCs</span></span>](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)  
  
-   [<span data-ttu-id="4f4af-114">Esquemas de mensaje para las operaciones de IDOC</span><span class="sxs-lookup"><span data-stu-id="4f4af-114">Message Schemas for IDOC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)  
  
-   [<span data-ttu-id="4f4af-115">Propiedades de contexto de mensaje para recibir IDOC</span><span class="sxs-lookup"><span data-stu-id="4f4af-115">Message Context Properties for Receiving IDOCs</span></span>](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)  
  
-   [<span data-ttu-id="4f4af-116">Esquemas de mensaje para las operaciones de RFC</span><span class="sxs-lookup"><span data-stu-id="4f4af-116">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)  
  
-   [<span data-ttu-id="4f4af-117">Esquemas de mensaje para operaciones de tRFC</span><span class="sxs-lookup"><span data-stu-id="4f4af-117">Message Schemas for tRFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)  
  
-   [<span data-ttu-id="4f4af-118">Esquemas de mensaje para las operaciones de BAPI</span><span class="sxs-lookup"><span data-stu-id="4f4af-118">Message Schemas for BAPI Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)  
  
-   [<span data-ttu-id="4f4af-119">Operaciones especiales</span><span class="sxs-lookup"><span data-stu-id="4f4af-119">Special Operations</span></span>](../../adapters-and-accelerators/adapter-sap/special-operations.md)  
  
-   [<span data-ttu-id="4f4af-120">Compatibilidad de versiones de mensaje</span><span class="sxs-lookup"><span data-stu-id="4f4af-120">Message Versioning Support</span></span>](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)  
  
