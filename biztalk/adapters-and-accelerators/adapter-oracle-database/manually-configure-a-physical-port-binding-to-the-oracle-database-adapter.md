---
title: Configurar manualmente un enlace de puerto físico para el adaptador de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, sending to an Oracle database
- messages, receiving from an Oracle database
- physical port binding, manually configuring
ms.assetid: 6b118236-e9eb-494e-96b2-969c7064943d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79e002762175eb847385617e2efd570d342b1c3a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976207"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-database-adapter"></a><span data-ttu-id="2420e-102">Configurar manualmente un enlace de puerto físico para el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="2420e-102">Manually configure a physical port binding to the Oracle Database Adapter</span></span>
<span data-ttu-id="2420e-103">Esta sección proporciona información sobre cómo configurar el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] como un enlace WCF-Custom o WCF-OracleDB enlace mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="2420e-103">This section provides information about configuring the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] as a WCF-Custom binding or WCF-OracleDB binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="2420e-104">Después de implementar el adaptador, podrá enviar y recibir mensajes de la base de datos de Oracle mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="2420e-104">After deploying the adapter, you will be able to send and receive messages from the Oracle database by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="2420e-105">Los pasos para implementar el adaptador varían en función de:</span><span class="sxs-lookup"><span data-stu-id="2420e-105">The steps for deploying the adapter vary depending on:</span></span>  
  
- <span data-ttu-id="2420e-106">La dirección de comunicación entre el servidor BizTalk Server y [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2420e-106">The direction of communication between BizTalk Server and [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="2420e-107">Puede configurar un envío, recepción, envío y recepción o un puerto de envío de recepción.</span><span class="sxs-lookup"><span data-stu-id="2420e-107">You may choose to configure a send, receive, send-receive, or a receive-send port.</span></span> <span data-ttu-id="2420e-108">En la tabla siguiente se resumen las opciones.</span><span class="sxs-lookup"><span data-stu-id="2420e-108">Your choices are summarized in the following table.</span></span>  
  
  |<span data-ttu-id="2420e-109">Dirección de puerto</span><span class="sxs-lookup"><span data-stu-id="2420e-109">Port direction</span></span>|<span data-ttu-id="2420e-110">Patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="2420e-110">Communication pattern</span></span>|<span data-ttu-id="2420e-111">Dirección de comunicación que elegir</span><span class="sxs-lookup"><span data-stu-id="2420e-111">Direction of communication to choose from</span></span>|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |<span data-ttu-id="2420e-112">Send</span><span class="sxs-lookup"><span data-stu-id="2420e-112">Send</span></span>|<span data-ttu-id="2420e-113">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="2420e-113">One-way</span></span>|<span data-ttu-id="2420e-114">Siempre enviaré los mensajes en este puerto.</span><span class="sxs-lookup"><span data-stu-id="2420e-114">I will always be sending messages on this port.</span></span>|  
  |<span data-ttu-id="2420e-115">Receive</span><span class="sxs-lookup"><span data-stu-id="2420e-115">Receive</span></span>|<span data-ttu-id="2420e-116">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="2420e-116">One-way</span></span>|<span data-ttu-id="2420e-117">Siempre recibiré los mensajes en este puerto.</span><span class="sxs-lookup"><span data-stu-id="2420e-117">I will always be receiving messages on this port.</span></span>|  
  |<span data-ttu-id="2420e-118">Envío y recepción</span><span class="sxs-lookup"><span data-stu-id="2420e-118">Send-receive</span></span>|<span data-ttu-id="2420e-119">Solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="2420e-119">Request-response</span></span>|<span data-ttu-id="2420e-120">Enviar una solicitud y recibiré una respuesta.</span><span class="sxs-lookup"><span data-stu-id="2420e-120">I will be sending a request and receiving a response.</span></span>|  
  |<span data-ttu-id="2420e-121">Envío de recepción</span><span class="sxs-lookup"><span data-stu-id="2420e-121">Receive-send</span></span>|<span data-ttu-id="2420e-122">Petición-respuesta</span><span class="sxs-lookup"><span data-stu-id="2420e-122">Solicit-response</span></span>|<span data-ttu-id="2420e-123">Recibiré una solicitud y enviaré una respuesta.</span><span class="sxs-lookup"><span data-stu-id="2420e-123">I will be receiving a request and sending a response.</span></span>|  
  
   <span data-ttu-id="2420e-124">Para obtener más información, consulte [crear un puerto de envío](../../core/how-to-create-a-send-port2.md), o [crear un puerto de recepción](../../core/how-to-create-a-receive-port.md).</span><span class="sxs-lookup"><span data-stu-id="2420e-124">For more information, see [Create a Send Port](../../core/how-to-create-a-send-port2.md), or [Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span> 
  
- <span data-ttu-id="2420e-125">Si el adaptador envía mensajes a la base de datos de Oracle o recibe mensajes de la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="2420e-125">Whether the adapter sends messages to the Oracle database or receives messages from the Oracle database.</span></span> <span data-ttu-id="2420e-126">Dependiendo de si desea enviar o recibir mensajes, creará un envío o puerto de recepción, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2420e-126">Depending on whether you want to send or receive messages, you will create a send or receive port, respectively.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="2420e-127">También puede configurar el envío o los puertos de recepción mediante la importación de un archivo de configuración de enlace que se crea mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] como parte de la generación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2420e-127">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="2420e-128">Para obtener instrucciones sobre cómo configurar los puertos que usa este archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="2420e-128">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="2420e-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="2420e-129">See Also</span></span>  
[<span data-ttu-id="2420e-130">Desarrollar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2420e-130">Develop your BizTalk applications</span></span>](../../core/develop-your-biztalk-applications.md)