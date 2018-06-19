---
title: Adaptador de HTTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, receive adapters
- HTTP adapters, send adapters
- HTTP adapters
- receive adapters, HTTP adapters
- send adapters, HTTP adapters
- HTTP adapters, about HTTP adapters
ms.assetid: a9423052-8392-4006-ab46-79834169c796
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d9be9fac6fdb65c4516c671b6c0e30096e83a27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256052"
---
# <a name="http-adapter"></a><span data-ttu-id="60844-102">Adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="60844-102">HTTP Adapter</span></span>
<span data-ttu-id="60844-103">El adaptador de HTTP se emplea para intercambiar información entre Microsoft BizTalk Server y una aplicación por medio del protocolo HTTP.</span><span class="sxs-lookup"><span data-stu-id="60844-103">You use the HTTP adapter to exchange information between Microsoft BizTalk Server and an application by means of the HTTP protocol.</span></span> <span data-ttu-id="60844-104">HTTP es el protocolo principal para el intercambio de mensajes entre empresas.</span><span class="sxs-lookup"><span data-stu-id="60844-104">HTTP is the primary protocol for interbusiness message exchange.</span></span> <span data-ttu-id="60844-105">Las aplicaciones pueden enviar mensajes a un servidor mediante el envío de solicitudes HTTP POST o HTTP GET a una dirección URL de HTTP concreta.</span><span class="sxs-lookup"><span data-stu-id="60844-105">Applications can send messages to a server by sending HTTP POST or HTTP GET requests to a specified HTTP URL.</span></span> <span data-ttu-id="60844-106">El adaptador HTTP recibe solicitudes HTTP y las envía al servidor BizTalk Server para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="60844-106">The HTTP adapter receives the HTTP requests and submits them to BizTalk Server for processing.</span></span> <span data-ttu-id="60844-107">Del mismo modo, BizTalk Server puede transmitir mensajes a aplicaciones remotas mediante el envío de solicitudes HTTP POST a una dirección URL de HTTP concreta.</span><span class="sxs-lookup"><span data-stu-id="60844-107">Similarly, BizTalk Server can transmit messages to remote applications by sending HTTP POST requests to a specified HTTP URL.</span></span>  
  
 <span data-ttu-id="60844-108">El adaptador HTTP se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="60844-108">The HTTP adapter consists of two adapters—a receive adapter and a send adapter.</span></span> <span data-ttu-id="60844-109">El adaptador de recepción HTTP es una extensión de la Interfaz de programación de aplicaciones para servidores de Internet (ISAPI) de los Servicios de Internet Information Server de Microsoft (IIS) que aloja el proceso IIS y controla las ubicaciones de recepción que utilizan el adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="60844-109">The HTTP receive adapter is a Microsoft Internet Information Services (IIS) Internet Server Application Programming Interface (ISAPI) extension that the IIS process hosts, and controls the receive locations that use the HTTP adapter.</span></span> <span data-ttu-id="60844-110">El adaptador de envío de HTTP controla los puertos de envío que utilizan el adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="60844-110">The HTTP send adapter controls the send ports that use the HTTP adapter.</span></span>  
  
 <span data-ttu-id="60844-111">En esta sección se explica la compatibilidad con el procesamiento por lotes y el flujo de trabajo de los adaptadores de envío y recepción de HTTP.</span><span class="sxs-lookup"><span data-stu-id="60844-111">This section discusses the workflow and batching support for both the HTTP receive adapter and the HTTP send adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60844-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="60844-112">In This Section</span></span>  
  
-   [<span data-ttu-id="60844-113">Adaptador de recepción HTTP</span><span class="sxs-lookup"><span data-stu-id="60844-113">HTTP Receive Adapter</span></span>](../core/http-receive-adapter.md)  
  
-   [<span data-ttu-id="60844-114">Adaptador de envío HTTP</span><span class="sxs-lookup"><span data-stu-id="60844-114">HTTP Send Adapter</span></span>](../core/http-send-adapter.md)  
  
-   [<span data-ttu-id="60844-115">Configurar el adaptador HTTP</span><span class="sxs-lookup"><span data-stu-id="60844-115">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)  
  
-   [<span data-ttu-id="60844-116">Recomendaciones de seguridad del adaptador HTTP</span><span class="sxs-lookup"><span data-stu-id="60844-116">HTTP Adapter Security Recommendations</span></span>](../core/http-adapter-security-recommendations.md)