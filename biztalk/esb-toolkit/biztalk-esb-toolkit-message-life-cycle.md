---
title: Ciclo de vida del mensaje del Kit de herramientas de ESB de BizTalk | Microsoft Docs
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
ms.openlocfilehash: 8f93a4ee2024fcb9cfaf65e7cf33922784a47030
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979141"
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a><span data-ttu-id="52197-102">Ciclo de vida del mensaje del Kit de herramientas de BizTalk ESB</span><span class="sxs-lookup"><span data-stu-id="52197-102">BizTalk ESB Toolkit Message Life Cycle</span></span>
<span data-ttu-id="52197-103">Este es el ciclo de vida de un mensaje que se origina en un sistema externo y recorre el ESB para llegar a su destino final:</span><span class="sxs-lookup"><span data-stu-id="52197-103">The following is the life cycle of a message that originates from an external system and traverses through the ESB to reach its final destination:</span></span>  

1. <span data-ttu-id="52197-104">Una rampa recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="52197-104">An on-ramp receives the message.</span></span> <span data-ttu-id="52197-105">Dependiendo de la entidad de envío o cliente, el mensaje puede o no puede contener un itinerario que define las instrucciones de procesamiento del mensaje.</span><span class="sxs-lookup"><span data-stu-id="52197-105">Depending on the submitting party or client, the message may or may not contain an itinerary that defines the processing instructions for the message.</span></span>  

2. <span data-ttu-id="52197-106">Los componentes de canalización ESB copie el itinerario (si está presente en el encabezado SOAP) en el contexto del mensaje como propiedades promocionadas.</span><span class="sxs-lookup"><span data-stu-id="52197-106">ESB pipeline components copy the itinerary (if present in the SOAP header) into the context of the message as promoted properties.</span></span> <span data-ttu-id="52197-107">Si el mensaje se recibe sin un itinerario, se puede configurar un componente de canalización específica para seleccionar el itinerario adecuado de una base de datos, según el contexto, o el contenido del mensaje y, a continuación, copie el itinerario en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="52197-107">If the message is received without an itinerary, a specific pipeline component can be configured to select the appropriate itinerary from a database, depending on message content or context, and then copy the itinerary into the context of the message.</span></span> <span data-ttu-id="52197-108">Durante la duración de la duración del mensaje, se mantiene el itinerario dentro del contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="52197-108">For the duration of the lifetime of the message, the itinerary is maintained within the message context.</span></span>  

3. <span data-ttu-id="52197-109">Mientras sigue en la canalización, se evalúa el itinerario y servicios de itinerario de mensaje pueden procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="52197-109">While still in the pipeline, the itinerary is evaluated and message-based itinerary services can process the message.</span></span> <span data-ttu-id="52197-110">Estos servicios de itinerario podrán transformar el mensaje o configuren extremos de enrutamientos.</span><span class="sxs-lookup"><span data-stu-id="52197-110">These itinerary services may transform the message or configure routing endpoints.</span></span>  

4. <span data-ttu-id="52197-111">El mensaje se publica en la base de datos de cuadro de mensaje de Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="52197-111">The message is published to the Microsoft BizTalk Server Message Box database.</span></span>  

5. <span data-ttu-id="52197-112">BizTalk Server evalúa las propiedades promocionadas del mensaje y las colas en el mensaje para uno o varios suscriptores.</span><span class="sxs-lookup"><span data-stu-id="52197-112">BizTalk Server evaluates the promoted properties of the message and queues the message for one or more subscribers.</span></span>  

6. <span data-ttu-id="52197-113">Los suscriptores de procesan el mensaje mediante los mecanismos típicos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="52197-113">The subscriber(s) process the message using typical BizTalk Server mechanisms.</span></span> <span data-ttu-id="52197-114">Un suscriptor puede ser cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="52197-114">A subscriber can be either of the following:</span></span>  

   -   <span data-ttu-id="52197-115">Puerto de recepción de una orquestación de BizTalk Server con un filtro configurado en un enlace directo</span><span class="sxs-lookup"><span data-stu-id="52197-115">A BizTalk Server orchestration with a filter configured on a direct-bound receive port</span></span>  

   -   <span data-ttu-id="52197-116">Un servidor BizTalk Server dinámica puerto de envío, que también se conoce como un ESB fuera de rampa.</span><span class="sxs-lookup"><span data-stu-id="52197-116">A dynamic BizTalk Server send port, which is also referred to as an ESB off-ramp.</span></span> <span data-ttu-id="52197-117">El itinerario determina cómo se configurará el puerto para continuar procesando el mensaje.</span><span class="sxs-lookup"><span data-stu-id="52197-117">The itinerary determines how the port will be configured to continue processing the message.</span></span>  

   <span data-ttu-id="52197-118">Como alternativa a un mensaje que llega a través de una rampa de itinerario, orquestaciones de BizTalk Server también pueden publicar mensajes en el cuadro de mensaje para el procesamiento de ESB:</span><span class="sxs-lookup"><span data-stu-id="52197-118">As an alternative to a message arriving through an itinerary on-ramp, BizTalk Server orchestrations can also publish messages to the Message Box for ESB processing:</span></span>  

7. <span data-ttu-id="52197-119">Se crea un mensaje dentro de una orquestación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="52197-119">A message is created within a BizTalk Server orchestration.</span></span>  

8. <span data-ttu-id="52197-120">Contexto del mensaje se rellena con los itinerarios ESB.</span><span class="sxs-lookup"><span data-stu-id="52197-120">The message's context is populated with the ESB itinerary.</span></span>  

9. <span data-ttu-id="52197-121">El mensaje se publica a través de un puerto de enlace directo a la base de datos de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="52197-121">The message is published through a direct-bound port to the Message Box database.</span></span>
