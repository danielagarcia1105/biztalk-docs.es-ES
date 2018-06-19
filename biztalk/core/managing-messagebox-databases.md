---
title: Administrar bases de datos de cuadro de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [MessageBox database], about managing MessageBox database
- managing [MessageBox database]
- MessageBox database, managing
ms.assetid: 9675b5d5-7a69-468d-be42-34a72cd6e5c2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e854ad0f7014de8241f8a7b6af6addd49cb4da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262148"
---
# <a name="managing-messagebox-databases"></a><span data-ttu-id="1c74d-102">Administrar bases de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="1c74d-102">Managing MessageBox Databases</span></span>
<span data-ttu-id="1c74d-103">La base de datos de cuadro de mensajes tiene tres funciones básicas.</span><span class="sxs-lookup"><span data-stu-id="1c74d-103">The MessageBox database has three essential functions.</span></span> <span data-ttu-id="1c74d-104">Almacena suscripciones e información de seguimiento, y entrega los mensajes a los servicios que coinciden con las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="1c74d-104">It stores subscriptions and tracking information and it delivers the messages to the services that match the subscriptions.</span></span> <span data-ttu-id="1c74d-105">La base de datos de cuadro de mensajes es una plataforma de host que almacena las colas y tablas de estado de cada host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1c74d-105">The MessageBox database is a host platform that stores the queues and state tables for each BizTalk Host.</span></span> <span data-ttu-id="1c74d-106">La base de datos de cuadro de mensajes almacena también mensajes y propiedades.</span><span class="sxs-lookup"><span data-stu-id="1c74d-106">The MessageBox database also stores messages and message properties.</span></span>  
  
 <span data-ttu-id="1c74d-107">Si las bases de datos de cuadro de mensajes son un activo con una exposición de alto riesgo en su entorno, se recomienda usar el protocolo de seguridad de Internet (IPSec) o Capa de sockets seguros (SSL) para restringir y proteger la comunicación con las bases de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1c74d-107">If the MessageBox databases are an asset with high-risk exposure in your environment, we recommend that you use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to restrict and secure communication to and from the MessageBox databases.</span></span>  
  
 <span data-ttu-id="1c74d-108">Si utiliza Windows Server 2003, debe habilitar el Coordinador de transacciones distribuidas (DTC) en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1c74d-108">If you use Windows Server 2003, you must enable the distributed transaction coordinator (DTC) on the MessageBox database.</span></span> <span data-ttu-id="1c74d-109">También debe habilitar los clientes de red para implementaciones de varios equipos.</span><span class="sxs-lookup"><span data-stu-id="1c74d-109">You must also enable network clients for multicomputer deployments.</span></span> <span data-ttu-id="1c74d-110">Para obtener más información, consulte [puertos para el servidor de administración](../core/ports-for-the-administration-server.md).</span><span class="sxs-lookup"><span data-stu-id="1c74d-110">For more information, see [Ports for the Administration Server](../core/ports-for-the-administration-server.md).</span></span>  
  
 <span data-ttu-id="1c74d-111">Esta sección contiene información de procedimientos para administrar las bases de datos de cuadro de mensajes en su entorno.</span><span class="sxs-lookup"><span data-stu-id="1c74d-111">This section contains procedural information about managing MessageBox databases in your environment.</span></span> <span data-ttu-id="1c74d-112">Para obtener información conceptual acerca de las bases de datos de cuadro de mensajes y la suscripción del modelo de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza para procesar mensajes, vea [la base de datos de cuadro de mensajes](../core/the-messagebox-database.md).</span><span class="sxs-lookup"><span data-stu-id="1c74d-112">For conceptual information about MessageBox databases and the subscription model Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses to process messages, see [The MessageBox Database](../core/the-messagebox-database.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c74d-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1c74d-113">In This Section</span></span>  
  
-   [<span data-ttu-id="1c74d-114">Cómo agregar una nueva base de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="1c74d-114">How to Add a New MessageBox Database</span></span>](../core/how-to-add-a-new-messagebox-database.md)  
  
-   [<span data-ttu-id="1c74d-115">Cómo deshabilitar la publicación de mensajes nuevos</span><span class="sxs-lookup"><span data-stu-id="1c74d-115">How to Disable New Message Publication</span></span>](../core/how-to-disable-new-message-publication.md)  
  
-   [<span data-ttu-id="1c74d-116">Cómo eliminar una base de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="1c74d-116">How to Delete a MessageBox Database</span></span>](../core/how-to-delete-a-messagebox-database.md)