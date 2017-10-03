---
title: "Configurar manualmente un enlace de puerto físico para el adaptador SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, sending messages to the SAP system
- physical port binding, manually configuring
- deploying, receiving messages from the SAP system
ms.assetid: c4f547aa-5514-4ca9-809b-d8d395de419c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 725a26eed4502e0a3d1eca8ed5f1429988590614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-sap-adapter"></a><span data-ttu-id="2f8a9-102">Configurar manualmente un enlace de puerto físico para el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="2f8a9-102">Manually configure a physical port binding to the SAP adapter</span></span>
<span data-ttu-id="2f8a9-103">Configurar la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como un enlace personalizado de WCF mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="2f8a9-103">Configure the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as a WCF custom binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> 

## <a name="port-overview"></a><span data-ttu-id="2f8a9-104">Información general de puerto</span><span class="sxs-lookup"><span data-stu-id="2f8a9-104">Port overview</span></span>
<span data-ttu-id="2f8a9-105">Después de implementar el adaptador, podrá enviar y recibir mensajes desde el sistema SAP mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="2f8a9-105">After deploying the adapter, you will be able to send and receive messages from the SAP system by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="2f8a9-106">Los pasos para implementar el adaptador varían en función de:</span><span class="sxs-lookup"><span data-stu-id="2f8a9-106">The steps for deploying the adapter vary depending on:</span></span>  
  
-   <span data-ttu-id="2f8a9-107">La dirección de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f8a9-107">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="2f8a9-108">Puede optar por configurar un envío, recepción, envío y recepción o un puerto de envío de recepción.</span><span class="sxs-lookup"><span data-stu-id="2f8a9-108">You may choose to configure a Send, Receive, Send-Receive, or a Receive-Send port.</span></span> <span data-ttu-id="2f8a9-109">Las opciones disponibles se resumen en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="2f8a9-109">Your choices are summarized in the following table:</span></span>  
  
    |<span data-ttu-id="2f8a9-110">Dirección de puerto</span><span class="sxs-lookup"><span data-stu-id="2f8a9-110">Port direction</span></span>|<span data-ttu-id="2f8a9-111">Patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="2f8a9-111">Communication pattern</span></span>|<span data-ttu-id="2f8a9-112">Dirección de comunicación para elegir</span><span class="sxs-lookup"><span data-stu-id="2f8a9-112">Direction of communication to choose from</span></span>|  
    |---|---|---|  
    |<span data-ttu-id="2f8a9-113">Send</span><span class="sxs-lookup"><span data-stu-id="2f8a9-113">Send</span></span>|<span data-ttu-id="2f8a9-114">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="2f8a9-114">One-way</span></span>|<span data-ttu-id="2f8a9-115">Siempre enviaré los mensajes en este puerto.</span><span class="sxs-lookup"><span data-stu-id="2f8a9-115">I will always be sending messages on this port.</span></span>|  
    |<span data-ttu-id="2f8a9-116">Receive</span><span class="sxs-lookup"><span data-stu-id="2f8a9-116">Receive</span></span>|<span data-ttu-id="2f8a9-117">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="2f8a9-117">One-way</span></span>|<span data-ttu-id="2f8a9-118">Siempre recibiré los mensajes en este puerto.</span><span class="sxs-lookup"><span data-stu-id="2f8a9-118">I will always be receiving messages on this port.</span></span>|  
    |<span data-ttu-id="2f8a9-119">Envío-Recepción</span><span class="sxs-lookup"><span data-stu-id="2f8a9-119">Send-Receive</span></span>|<span data-ttu-id="2f8a9-120">Solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="2f8a9-120">Request-response</span></span>|<span data-ttu-id="2f8a9-121">Enviar una solicitud y recibiré una respuesta.</span><span class="sxs-lookup"><span data-stu-id="2f8a9-121">I will be sending a request and receiving a response.</span></span>|  
    |<span data-ttu-id="2f8a9-122">Recepción-Envío</span><span class="sxs-lookup"><span data-stu-id="2f8a9-122">Receive-Send</span></span>|<span data-ttu-id="2f8a9-123">Petición-respuesta</span><span class="sxs-lookup"><span data-stu-id="2f8a9-123">Solicit-response</span></span>|<span data-ttu-id="2f8a9-124">Recibiré una solicitud y enviaré una respuesta.</span><span class="sxs-lookup"><span data-stu-id="2f8a9-124">I will be receiving a request and sending a response.</span></span>|  
  
     <span data-ttu-id="2f8a9-125">Para obtener más información, consulte [crear un puerto de envío](../../core/how-to-create-a-send-port2.md), o [crear un puerto de recepción](../../core/how-to-create-a-receive-port.md).</span><span class="sxs-lookup"><span data-stu-id="2f8a9-125">For more information, see [Create a Send Port](../../core/how-to-create-a-send-port2.md), or [Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span>
  
-   <span data-ttu-id="2f8a9-126">Si el adaptador envía mensajes al sistema SAP o recibe mensajes desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2f8a9-126">Whether the adapter sends messages to the SAP system or receives messages from the SAP system.</span></span> <span data-ttu-id="2f8a9-127">Dependiendo de si desea enviar o recibir mensajes, se crea un envío o puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="2f8a9-127">Depending on whether you want to send or receive messages, you will create a send or receive port.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f8a9-128">También puede configurar el envío o puertos de recepción mediante la importación de un archivo de configuración de enlace que se crea mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] como parte de la generación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2f8a9-128">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="2f8a9-129">Para obtener instrucciones acerca de cómo configurar los puertos que utilizan este archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).</span><span class="sxs-lookup"><span data-stu-id="2f8a9-129">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2f8a9-130">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2f8a9-130">In this section</span></span>  
  
-   [<span data-ttu-id="2f8a9-131">Configurar un puerto mediante el adaptador WCF-custom y el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="2f8a9-131">Configure a port using the WCF-custom adapter and Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="2f8a9-132">Configurar un puerto con un adaptador SAP de WCF</span><span class="sxs-lookup"><span data-stu-id="2f8a9-132">Configure a port using the WCF-SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/configure-a-port-using-the-wcf-sap-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f8a9-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f8a9-133">See Also</span></span>  
[<span data-ttu-id="2f8a9-134">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="2f8a9-134">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)