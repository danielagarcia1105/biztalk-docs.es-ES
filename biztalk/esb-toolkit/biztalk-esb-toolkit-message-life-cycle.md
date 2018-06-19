---
title: Ciclo de vida del mensaje del Kit de herramientas de ESB de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c72fdbda-b9ef-431a-8322-56dba98e9eab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cb15a4c87a497a5595327b65019ca95b3201664
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290356"
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a><span data-ttu-id="a776d-102">Ciclo de vida del mensaje del Kit de herramientas de ESB de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a776d-102">BizTalk ESB Toolkit Message Life Cycle</span></span>
<span data-ttu-id="a776d-103">A continuación se muestra el ciclo de vida de un mensaje que se origina en un sistema externo y recorre el ESB para alcanzar su destino final:</span><span class="sxs-lookup"><span data-stu-id="a776d-103">The following is the life cycle of a message that originates from an external system and traverses through the ESB to reach its final destination:</span></span>  
  
1.  <span data-ttu-id="a776d-104">En rampa recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a776d-104">An on-ramp receives the message.</span></span> <span data-ttu-id="a776d-105">Dependiendo de la entidad o el cliente enviando, el mensaje puede o no puede contener un itinerario que define las instrucciones de procesamiento para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a776d-105">Depending on the submitting party or client, the message may or may not contain an itinerary that defines the processing instructions for the message.</span></span>  
  
2.  <span data-ttu-id="a776d-106">Componentes de canalización ESB copiar el itinerario (si está presente en el encabezado SOAP) en el contexto del mensaje como propiedades promocionadas.</span><span class="sxs-lookup"><span data-stu-id="a776d-106">ESB pipeline components copy the itinerary (if present in the SOAP header) into the context of the message as promoted properties.</span></span> <span data-ttu-id="a776d-107">Si se recibe el mensaje sin un itinerario, un componente de canalización específica puede configurarse para seleccionar el itinerario adecuado de una base de datos, según el contenido del mensaje o un contexto y, a continuación, copie el itinerario en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a776d-107">If the message is received without an itinerary, a specific pipeline component can be configured to select the appropriate itinerary from a database, depending on message content or context, and then copy the itinerary into the context of the message.</span></span> <span data-ttu-id="a776d-108">Durante la duración de la duración del mensaje, el itinerario se mantiene en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a776d-108">For the duration of the lifetime of the message, the itinerary is maintained within the message context.</span></span>  
  
3.  <span data-ttu-id="a776d-109">Mientras se encuentra en la canalización, se evalúa el itinerario y servicios itinerarios basada en mensajes pueden procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a776d-109">While still in the pipeline, the itinerary is evaluated and message-based itinerary services can process the message.</span></span> <span data-ttu-id="a776d-110">Estos servicios itinerarios pueden transformar el mensaje o configuren extremos de enrutamientos.</span><span class="sxs-lookup"><span data-stu-id="a776d-110">These itinerary services may transform the message or configure routing endpoints.</span></span>  
  
4.  <span data-ttu-id="a776d-111">El mensaje se publica en la base de datos de cuadro de mensaje de Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a776d-111">The message is published to the Microsoft BizTalk Server Message Box database.</span></span>  
  
5.  <span data-ttu-id="a776d-112">BizTalk Server evalúa las propiedades promocionadas de las colas y mensajes en el mensaje para uno o más suscriptores.</span><span class="sxs-lookup"><span data-stu-id="a776d-112">BizTalk Server evaluates the promoted properties of the message and queues the message for one or more subscribers.</span></span>  
  
6.  <span data-ttu-id="a776d-113">Los suscriptores de procesan el mensaje mediante los mecanismos típicos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a776d-113">The subscriber(s) process the message using typical BizTalk Server mechanisms.</span></span> <span data-ttu-id="a776d-114">Un suscriptor puede ser cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a776d-114">A subscriber can be either of the following:</span></span>  
  
    -   <span data-ttu-id="a776d-115">Puerto de recepción de una orquestación de BizTalk Server con un filtro configurado en un enlace directo</span><span class="sxs-lookup"><span data-stu-id="a776d-115">A BizTalk Server orchestration with a filter configured on a direct-bound receive port</span></span>  
  
    -   <span data-ttu-id="a776d-116">Un servidor de BizTalk dinámico puerto de envío, que también se conoce como ESB fuera de rampa.</span><span class="sxs-lookup"><span data-stu-id="a776d-116">A dynamic BizTalk Server send port, which is also referred to as an ESB off-ramp.</span></span> <span data-ttu-id="a776d-117">El itinerario determina cómo se configurará el puerto para continuar procesando el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a776d-117">The itinerary determines how the port will be configured to continue processing the message.</span></span>  
  
 <span data-ttu-id="a776d-118">Como alternativa a un mensaje que llega a través de itinerario en rampa, orquestaciones de BizTalk Server también pueden publicar mensajes en el cuadro de mensaje para el procesamiento de ESB:</span><span class="sxs-lookup"><span data-stu-id="a776d-118">As an alternative to a message arriving through an itinerary on-ramp, BizTalk Server orchestrations can also publish messages to the Message Box for ESB processing:</span></span>  
  
1.  <span data-ttu-id="a776d-119">Se crea un mensaje dentro de una orquestación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a776d-119">A message is created within a BizTalk Server orchestration.</span></span>  
  
2.  <span data-ttu-id="a776d-120">Contexto del mensaje se rellena con el itinerario ESB.</span><span class="sxs-lookup"><span data-stu-id="a776d-120">The message's context is populated with the ESB itinerary.</span></span>  
  
3.  <span data-ttu-id="a776d-121">El mensaje se publica a través de un puerto de enlace directo a la base de datos de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a776d-121">The message is published through a direct-bound port to the Message Box database.</span></span>