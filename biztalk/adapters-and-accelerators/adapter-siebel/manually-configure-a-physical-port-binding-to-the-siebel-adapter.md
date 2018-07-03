---
title: Configurar manualmente un enlace de puerto físico para el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- physical port binding, manually configuring
- how to, manually configure adapters for sending messages to a Siebel system
ms.assetid: a1445b8a-440f-45e8-96e9-a13142ca87c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25afdeaf544cddb67440d050690ca8ca08df4547
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020036"
---
# <a name="manually-configure-a-physical-port-binding-to-the-siebel-adapter"></a><span data-ttu-id="ac565-102">Configurar manualmente un enlace de puerto físico para el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="ac565-102">Manually configure a physical port binding to the Siebel adapter</span></span>
<span data-ttu-id="ac565-103">Esta sección proporciona información sobre cómo configurar el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] como un enlace personalizado de WCF mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ac565-103">This section provides information about configuring the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] as a WCF custom binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ac565-104">Después de implementar el adaptador, podrá enviar y recibir mensajes desde el sistema Siebel mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ac565-104">After deploying the adapter, you will be able to send and receive messages from the Siebel system by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="ac565-105">Los pasos para implementar el adaptador varían según la dirección de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac565-105">The steps for deploying the adapter vary depending on the direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="ac565-106">Puede configurar un envío o un puerto de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="ac565-106">You may choose to configure a Send or a Send-Receive port.</span></span> <span data-ttu-id="ac565-107">Las opciones disponibles se resumen en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="ac565-107">Your choices are summarized in the following table:</span></span>  
  
|<span data-ttu-id="ac565-108">Dirección de puerto</span><span class="sxs-lookup"><span data-stu-id="ac565-108">Port direction</span></span>|<span data-ttu-id="ac565-109">Patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="ac565-109">Communication pattern</span></span>|<span data-ttu-id="ac565-110">Dirección de comunicación que elegir</span><span class="sxs-lookup"><span data-stu-id="ac565-110">Direction of communication to choose from</span></span>|  
|---|---|---|  
|<span data-ttu-id="ac565-111">Send</span><span class="sxs-lookup"><span data-stu-id="ac565-111">Send</span></span>|<span data-ttu-id="ac565-112">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="ac565-112">One-way</span></span>|<span data-ttu-id="ac565-113">Siempre enviaré los mensajes en este puerto.</span><span class="sxs-lookup"><span data-stu-id="ac565-113">I will always be sending messages on this port.</span></span>|  
|<span data-ttu-id="ac565-114">Envío-Recepción</span><span class="sxs-lookup"><span data-stu-id="ac565-114">Send-Receive</span></span>|<span data-ttu-id="ac565-115">Solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="ac565-115">Request-response</span></span>|<span data-ttu-id="ac565-116">Enviar una solicitud y recibiré una respuesta.</span><span class="sxs-lookup"><span data-stu-id="ac565-116">I will be sending a request and receiving a response.</span></span>|  
  
 <span data-ttu-id="ac565-117">Para obtener más información, consulte [crear y configurar puertos de envío](../../core/creating-and-configuring-send-ports.md).</span><span class="sxs-lookup"><span data-stu-id="ac565-117">For more information, see [Creating and Configuring Send Ports](../../core/creating-and-configuring-send-ports.md).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ac565-118">Recibir los puertos no se admiten porque el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no permite operaciones de entrada en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="ac565-118">Receive ports are not supported because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not enable inbound operations from the Siebel system.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="ac565-119">También puede configurar los puertos de envío WCF-Custom mediante la importación de un archivo de configuración de enlace que se crea mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] como parte de la generación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="ac565-119">You can also configure the WCF-Custom send ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="ac565-120">Para obtener instrucciones sobre cómo configurar los puertos que usa este archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).</span><span class="sxs-lookup"><span data-stu-id="ac565-120">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).</span></span>
  
 
  
## <a name="see-also"></a><span data-ttu-id="ac565-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac565-121">See Also</span></span>  
[<span data-ttu-id="ac565-122">Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="ac565-122">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)