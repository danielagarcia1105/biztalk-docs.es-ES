---
title: Desarrollar aplicaciones de BizTalk con el adaptador SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
ms.assetid: 4aa10897-a08e-4fc3-9c1f-40485d204273
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75e70a52f12227b1bde3a43f9330c6fe373ac5a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-sap-adapter"></a><span data-ttu-id="6b27c-102">Desarrollar aplicaciones de BizTalk con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="6b27c-102">Develop BizTalk applications using the SAP adapter</span></span>
<span data-ttu-id="6b27c-103">Desarrollo de aplicaciones de BizTalk implica la creación de un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y el uso de la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="6b27c-103">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate XML schema.</span></span> <span data-ttu-id="6b27c-104">Una vez que haya generado el esquema, puede usar enrutamiento por contenidos (CBR) o crear orquestaciones de BizTalk para enviar y recibir mensajes que cumplen el esquema generado.</span><span class="sxs-lookup"><span data-stu-id="6b27c-104">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to the generated schema.</span></span>  
  
 <span data-ttu-id="6b27c-105">CBR puede utilizarse en escenarios donde los mensajes que se envían al sistema SAP no requieren ningún procesamiento intensivo.</span><span class="sxs-lookup"><span data-stu-id="6b27c-105">CBR can be used in scenarios where the messages being sent to the SAP system do not require any intensive processing.</span></span> <span data-ttu-id="6b27c-106">Por ejemplo, si sabe que el puerto de recepción va a recibir mensajes sólo de un tipo determinado, puede agregar un filtro al puerto de envío para enrutar los mensajes que coinciden con la expresión de filtro para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="6b27c-106">For example, if you know that the receive port will be receiving messages only of a certain type, you can add a filter to the send port to route the messages matching the filter expression to the send port.</span></span>  
  
 <span data-ttu-id="6b27c-107">En las orquestaciones de BizTalk, creará el envío y puertos de recepción para enviar y recibir mensajes desde y hacia el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que a su vez envía los mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b27c-107">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6b27c-108">Esta sección proporciona información sobre el uso de las orquestaciones de BizTalk para realizar operaciones en el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b27c-108">This section provides information about using BizTalk orchestrations to perform operations on the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="6b27c-109">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a su vez usa la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] adaptador que puede interactuar con un enlace de WCF.</span><span class="sxs-lookup"><span data-stu-id="6b27c-109">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] adapter that can interact with a WCF binding.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b27c-110">Para usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre se debe establecer el **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**.</span><span class="sxs-lookup"><span data-stu-id="6b27c-110">To use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="6b27c-111">Para obtener información sobre cómo establecer propiedades de enlace, vea [configurar las propiedades de enlace para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="6b27c-111">For information about how to set binding properties, see [Configure the binding properties for the SAP adapter](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b27c-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6b27c-112">In This Section</span></span>  
  
-   [<span data-ttu-id="6b27c-113">Requisitos previos para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="6b27c-113">Prerequisites to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
-   [<span data-ttu-id="6b27c-114">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="6b27c-114">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)
  
-   [<span data-ttu-id="6b27c-115">Invocar RFC en SAP mediante BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6b27c-115">Invoke RFCs in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="6b27c-116">Recibir llamadas de RFC de entrada de SAP con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6b27c-116">Receive Inbound RFC Calls from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="6b27c-117">Invocar tRFCs en SAP mediante BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6b27c-117">Invoke tRFCs in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="6b27c-118">Recibir llamadas de tRFC entrada de SAP con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6b27c-118">Receive Inbound tRFC Calls from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="6b27c-119">Ejecutar BAPI transacciones en SAP mediante BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6b27c-119">Run BAPI Transactions in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="6b27c-120">Enviar los IDOC a SAP mediante BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6b27c-120">Send IDOCs to SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="6b27c-121">Recibir IDOC desde SAP mediante BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6b27c-121">Receive IDOCs from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="6b27c-122">Recibir IDOC de SAP en un contexto transaccional usando el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6b27c-122">Receive IDOCs from SAP in a Transactional Context using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="6b27c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b27c-123">See Also</span></span>  
[<span data-ttu-id="6b27c-124">Desarrollar las aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="6b27c-124">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)