---
title: Configurar manualmente un enlace de puerto físico al adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3f0bb78-c85f-4629-9e2d-cce180ff78ae
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7a9fb7a1390a59c564063f889a86096d2989d55
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979973"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sql-adapter"></a><span data-ttu-id="9fcd5-102">Configurar manualmente un enlace de puerto físico al adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="9fcd5-102">Manually configure a physical port binding to the SQL adapter</span></span>
<span data-ttu-id="9fcd5-103">Esta sección proporciona información sobre cómo configurar el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] como un enlace personalizado de WCF o como un puerto de WCF-SQL mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="9fcd5-103">This section provides information about configuring the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] as a WCF custom binding or as a WCF-SQL port by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="9fcd5-104">Después de implementar el adaptador, podrá enviar y recibir mensajes de SQL Server mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="9fcd5-104">After deploying the adapter, you will be able to send and receive messages from SQL Server by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="9fcd5-105">Los pasos para implementar el adaptador varían en función de:</span><span class="sxs-lookup"><span data-stu-id="9fcd5-105">The steps for deploying the adapter vary depending on:</span></span>  
  
- <span data-ttu-id="9fcd5-106">La dirección de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fcd5-106">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="9fcd5-107">Puede optar por configurar un envío, recepción, o un puerto de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="9fcd5-107">You may choose to configure a send, receive, or a send-receive port.</span></span> <span data-ttu-id="9fcd5-108">En la tabla siguiente se resumen las opciones.</span><span class="sxs-lookup"><span data-stu-id="9fcd5-108">Your choices are summarized in the following table.</span></span>  
  
  |<span data-ttu-id="9fcd5-109">Dirección de puerto</span><span class="sxs-lookup"><span data-stu-id="9fcd5-109">Port direction</span></span>|<span data-ttu-id="9fcd5-110">Patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="9fcd5-110">Communication pattern</span></span>|<span data-ttu-id="9fcd5-111">Dirección de comunicación que elegir</span><span class="sxs-lookup"><span data-stu-id="9fcd5-111">Direction of communication to choose from</span></span>|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |<span data-ttu-id="9fcd5-112">Send</span><span class="sxs-lookup"><span data-stu-id="9fcd5-112">Send</span></span>|<span data-ttu-id="9fcd5-113">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="9fcd5-113">One-way</span></span>|<span data-ttu-id="9fcd5-114">Siempre enviaré los mensajes en este puerto.</span><span class="sxs-lookup"><span data-stu-id="9fcd5-114">I will always be sending messages on this port.</span></span>|  
  |<span data-ttu-id="9fcd5-115">Receive</span><span class="sxs-lookup"><span data-stu-id="9fcd5-115">Receive</span></span>|<span data-ttu-id="9fcd5-116">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="9fcd5-116">One-way</span></span>|<span data-ttu-id="9fcd5-117">Siempre recibiré los mensajes en este puerto.</span><span class="sxs-lookup"><span data-stu-id="9fcd5-117">I will always be receiving messages on this port.</span></span>|  
  |<span data-ttu-id="9fcd5-118">Envío y recepción</span><span class="sxs-lookup"><span data-stu-id="9fcd5-118">Send-receive</span></span>|<span data-ttu-id="9fcd5-119">Solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="9fcd5-119">Request-response</span></span>|<span data-ttu-id="9fcd5-120">Enviar una solicitud y recibiré una respuesta.</span><span class="sxs-lookup"><span data-stu-id="9fcd5-120">I will be sending a request and receiving a response.</span></span>|  
  
  > [!NOTE]
  >  <span data-ttu-id="9fcd5-121">Bidireccional recibir puertos no son compatibles con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fcd5-121">Two-way receive ports are not supported by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
   <span data-ttu-id="9fcd5-122">Para obtener más información, consulte [cómo crear un puerto de envío](../../core/how-to-create-a-send-port2.md), o [cómo crear un puerto de recepción](../../core/how-to-create-a-receive-port.md).</span><span class="sxs-lookup"><span data-stu-id="9fcd5-122">For more information, see [How to Create a Send Port](../../core/how-to-create-a-send-port2.md), or [How to Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span> 
  
- <span data-ttu-id="9fcd5-123">Si el adaptador envía mensajes a SQL Server (operaciones de salida) o recibe mensajes de SQL Server (operaciones de entrada).</span><span class="sxs-lookup"><span data-stu-id="9fcd5-123">Whether the adapter sends messages to the SQL Server (outbound operations) or receives messages from SQL Server (inbound operations).</span></span> <span data-ttu-id="9fcd5-124">Dependiendo de si desea enviar o recibir mensajes, creará un envío o puerto de recepción, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9fcd5-124">Depending on whether you want to send or receive messages, you will create a send or receive port, respectively.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9fcd5-125">También puede configurar el envío o los puertos de recepción mediante la importación de un archivo de configuración de enlace que se crea mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] como parte de la generación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9fcd5-125">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="9fcd5-126">Para obtener instrucciones sobre cómo configurar los puertos que usa este archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="9fcd5-126">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="9fcd5-127">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9fcd5-127">In This Section</span></span>  
  
-   [<span data-ttu-id="9fcd5-128">Configurar un puerto mediante el adaptador WCF-custom y el adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="9fcd5-128">Configure a port using the WCF-custom adapter and SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)  
  
-   [<span data-ttu-id="9fcd5-129">Configurar un puerto mediante el adaptador WCF de SQL</span><span class="sxs-lookup"><span data-stu-id="9fcd5-129">Configure a port using the WCF-SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-sql-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="9fcd5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fcd5-130">See Also</span></span>  
[<span data-ttu-id="9fcd5-131">Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="9fcd5-131">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)