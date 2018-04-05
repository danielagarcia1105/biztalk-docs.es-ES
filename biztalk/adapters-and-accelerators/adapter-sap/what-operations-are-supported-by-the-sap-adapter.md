---
title: Las operaciones que son compatibles con el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, performing operations
ms.assetid: 4b676336-526d-42b9-9ff2-1a4f27df1a78
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee217572e0bf56e7a4f7e4810421befeb08bfc3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-sap-adapter"></a><span data-ttu-id="e9e2a-102">Las operaciones que son compatibles con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="e9e2a-102">What operations are supported by the SAP adapter</span></span>
<span data-ttu-id="e9e2a-103">Los clientes de adaptador pueden realizar operaciones en el sistema SAP mediante la creación de proyectos de BizTalk, mediante el modelo de canal WCF o mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-103">Adapter clients can perform operations on the SAP system by creating BizTalk projects, by using the WCF channel model, or by using the WCF service model.</span></span> <span data-ttu-id="e9e2a-104">La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-104">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="e9e2a-105">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-105">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="e9e2a-106">Si es necesario recibir una respuesta, se devuelve en un mensaje SOAP en el mismo canal.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-106">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="e9e2a-107">Para obtener información sobre la estructura del mensaje y la acción de SOAP asociada a cada operación, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-107">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>  
  
 <span data-ttu-id="e9e2a-108">Esta sección proporciona información acerca de las operaciones admitidas en el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9e2a-108">This section provides information about the operations supported on the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9e2a-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e9e2a-109">In This Section</span></span>  
  
-   [<span data-ttu-id="e9e2a-110">Operaciones en RFC en SAP</span><span class="sxs-lookup"><span data-stu-id="e9e2a-110">Operations on RFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)  
  
-   [<span data-ttu-id="e9e2a-111">Operaciones en tRFCs en SAP</span><span class="sxs-lookup"><span data-stu-id="e9e2a-111">Operations on tRFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)  
  
-   [<span data-ttu-id="e9e2a-112">Operaciones de BAPI en SAP</span><span class="sxs-lookup"><span data-stu-id="e9e2a-112">Operations on BAPIs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)  
  
-   [<span data-ttu-id="e9e2a-113">Operaciones en IDOC en SAP</span><span class="sxs-lookup"><span data-stu-id="e9e2a-113">Operations on IDOCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)