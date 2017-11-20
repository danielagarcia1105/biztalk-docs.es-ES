---
title: Desarrollar aplicaciones de SAP mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF channel model, developing applications by using
ms.assetid: 1ce70c8b-5eeb-4585-97af-b0a7b4398dac
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13015cb042d26c946abfa3c99a4f67034b8d9708
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sap-applications-using-the-wcf-channel-model"></a><span data-ttu-id="2152a-102">Desarrollar aplicaciones de SAP mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="2152a-102">Develop SAP applications using the WCF Channel Model</span></span>
<span data-ttu-id="2152a-103">Puede usar el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo del canal para consumir el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] mediante el envío de mensajes XML directamente a través de una instancia del canal creado con el enlace de SAP.</span><span class="sxs-lookup"><span data-stu-id="2152a-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] by sending XML messages directly over a channel instance created with the SAP Binding.</span></span>  
  
 <span data-ttu-id="2152a-104">Una ventaja de usar el modelo de canal WCF con respecto a las clases fuertemente tipadas y los métodos que expone el modelo de servicio WCF es que el modelo del canal proporciona un control más minucioso sobre las operaciones que se realizan en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2152a-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the SAP system.</span></span> <span data-ttu-id="2152a-105">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="2152a-105">Why?</span></span> <span data-ttu-id="2152a-106">En el modelo del canal WCF controla directamente el contenido de los mensajes que envía a través del canal.</span><span class="sxs-lookup"><span data-stu-id="2152a-106">In the WCF channel model you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="2152a-107">Otra ventaja clave que proporciona el modelo de canal WCF en el modelo de servicio WCF es más completa compatible con transmisión por secuencias de datos.</span><span class="sxs-lookup"><span data-stu-id="2152a-107">Another key advantage that the WCF channel model provides over the WCF service model is more comprehensive support for data streaming.</span></span> <span data-ttu-id="2152a-108">Mediante el modelo de canal WCF puede realizar:</span><span class="sxs-lookup"><span data-stu-id="2152a-108">By using the WCF channel model you can perform:</span></span>  
  
-   <span data-ttu-id="2152a-109">Nodo de mensaje en todos los mensajes intercambiados entre el código y el adaptador de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="2152a-109">Message node streaming on all messages exchanged between your code and the adapter.</span></span>  
  
-   <span data-ttu-id="2152a-110">Nodo de mensaje-valor transmisión por secuencias en las operaciones de SendIdoc y ReceiveIdoc.</span><span class="sxs-lookup"><span data-stu-id="2152a-110">Message node-value streaming on the SendIdoc and ReceiveIdoc operations.</span></span>  
  
 <span data-ttu-id="2152a-111">Esto es porque en el modelo de canal WCF puede controlar directamente cómo proporcionar el cuerpo del mensaje en mensajes que se envían al adaptador y cómo consumir el cuerpo del mensaje en los mensajes que recibe el adaptador.</span><span class="sxs-lookup"><span data-stu-id="2152a-111">This is because in the WCF channel model you directly control how you provide the message body on messages that you send to the adapter and how you consume the message body on messages that you receive from the adapter.</span></span>  
  
 <span data-ttu-id="2152a-112">En cambio, el adaptador no proporciona compatibilidad con transmisión por secuencias en el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="2152a-112">In contrast, the adapter provides no support for streaming in the WCF service model.</span></span> <span data-ttu-id="2152a-113">Ya que, en el modelo de servicio WCF, el tiempo de ejecución WCF serializa y deserializa mensajes entre sus representaciones de objeto de código administrado y XML, se realiza una copia en memoria completa de cada mensaje que intercambia con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="2152a-113">Because, in the WCF service model, the WCF runtime serializes and deserializes messages between their XML and managed code object representations, a complete in-memory copy of each message that you exchange with the adapter is made.</span></span>  
  
 <span data-ttu-id="2152a-114">Las secciones en este tema explica cómo realizar operaciones en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="2152a-114">The sections in this topic explain how to perform operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2152a-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2152a-115">In This Section</span></span>  
  
-   [<span data-ttu-id="2152a-116">Información general sobre el modelo del canal de WCF con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="2152a-116">Overview of the WCF Channel Model with the SAP Adapter</span></span>](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-channel-model-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="2152a-117">Crear un canal con SAP</span><span class="sxs-lookup"><span data-stu-id="2152a-117">Create a channel using SAP</span></span>](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)  
  
-   [<span data-ttu-id="2152a-118">Invocar operaciones en el sistema SAP mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="2152a-118">Invoking Operations on the SAP System by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="2152a-119">Recepción de las operaciones de entrada desde el sistema SAP mediante el modelo del canal de WCF</span><span class="sxs-lookup"><span data-stu-id="2152a-119">Receiving Inbound Operations from the SAP System by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md) 
  
-   [<span data-ttu-id="2152a-120">Transmisión por secuencias IDOC de archivo plano en SAP mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="2152a-120">Streaming Flat-File IDOCs in SAP using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)