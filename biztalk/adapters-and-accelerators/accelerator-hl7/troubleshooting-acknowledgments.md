---
title: "Solución de problemas de confirmaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, troubleshooting
- troubleshooting, acknowledgements
ms.assetid: faed356e-f5fc-4920-a9f9-82eca0ad7d67
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecbbb22498cfd3d451c0b8c75c8e6f4502c2364d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-acknowledgments"></a><span data-ttu-id="6d4e2-102">Solución de problemas de confirmaciones</span><span class="sxs-lookup"><span data-stu-id="6d4e2-102">Troubleshooting Acknowledgments</span></span>
<span data-ttu-id="6d4e2-103">Soluciona problemas relacionados con [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-103">Addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] acknowledgments.</span></span>  
  
## <a name="acknowledgments-are-not-generated"></a><span data-ttu-id="6d4e2-104">No se generan confirmaciones</span><span class="sxs-lookup"><span data-stu-id="6d4e2-104">Acknowledgments are not generated</span></span>  
 <span data-ttu-id="6d4e2-105">Hay varias causas posibles para las confirmaciones (ACK) no se genera o reciban.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-105">There are several potential causes for acknowledgments (ACKs) not being generated or received.</span></span> <span data-ttu-id="6d4e2-106">Revise la siguiente lista de posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-106">Review the following list of potential problems.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d4e2-107">Síntoma</span><span class="sxs-lookup"><span data-stu-id="6d4e2-107">Symptom</span></span>  
 <span data-ttu-id="6d4e2-108">No se generan cuando se actualiza la información de entidad [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración para generar confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-108">Acknowledgments are not generated when you update party information in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer to generate acknowledgments.</span></span>  
  
<span data-ttu-id="6d4e2-109">**Causa posible** : [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] almacena en caché y actualiza la información de configuración de entidad cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-109">**Possible cause** : [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] caches and refreshes party configuration information every 15 minutes.</span></span>  
  
<span data-ttu-id="6d4e2-110">**Resolución** : espere al menos 15 minutos para la memoria caché actualizar o reiniciar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para cambios surtan efecto inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-110">**Resolution** : Wait for at least 15 minutes for the cache to refresh, or restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for changes to take effect immediately.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d4e2-111">Síntoma</span><span class="sxs-lookup"><span data-stu-id="6d4e2-111">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6d4e2-112">no generar confirmaciones y los errores de eventos aparecen en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-112"> does not generate ACKs and event errors appear in the event log.</span></span>  
  
<span data-ttu-id="6d4e2-113">**Causa posible** : no se puede generar una confirmación cuando un lote en / lote mensaje contiene un campo FHS11 vacío.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-113">**Possible cause** : An ACK cannot be generated when a batch in/batch out message contains an empty FHS11 field.</span></span>  
  
<span data-ttu-id="6d4e2-114">**Resolución** : asegúrese de que los mensajes tienen un campo de FHS11 correctamente formateado y rellenado.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-114">**Resolution** : Ensure that your messages have a correctly formatted and populated FHS11 field.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d4e2-115">Síntoma</span><span class="sxs-lookup"><span data-stu-id="6d4e2-115">Symptom</span></span>  
 <span data-ttu-id="6d4e2-116">La aplicación no puede generar o recibir una confirmación.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-116">Your application cannot generate or receive an ACK.</span></span>  
  
<span data-ttu-id="6d4e2-117">**Causa posible** : impide que la información incorrecta en el campo MSH3 del mensaje [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] de enviar el mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-117">**Possible cause** : Incorrect information in the MSH3 field of your message prevents [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] from sending the message ACKs.</span></span>  
  
<span data-ttu-id="6d4e2-118">**Resolución** : asegúrese de que los mensajes tienen un campo de MSH3 correctamente formateado y rellenado.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-118">**Resolution** : Ensure that your messages have a correctly formatted and populated MSH3 field.</span></span>  
  
## <a name="acknowledgments-are-suspended-or-not-routed-to-the-send-party"></a><span data-ttu-id="6d4e2-119">Confirmaciones se suspende o no se enrute a la entidad de envío</span><span class="sxs-lookup"><span data-stu-id="6d4e2-119">Acknowledgments are suspended or not routed to the send party</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d4e2-120">Síntoma</span><span class="sxs-lookup"><span data-stu-id="6d4e2-120">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6d4e2-121">envía mensajes a un adaptador bidireccional sin generar confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-121"> sends messages to a two-way adapter without generating acknowledgments.</span></span>  
  
<span data-ttu-id="6d4e2-122">**Causa posible** : la suscripción de mensaje no está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-122">**Possible cause** : The message subscription is not configured correctly.</span></span>  
  
<span data-ttu-id="6d4e2-123">**Resolución** : asegúrese de que las suscripciones de mensaje están presente y configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-123">**Resolution** : Ensure that message subscriptions are present and configured correctly.</span></span>  
  
## <a name="suspended-acknowledgments"></a><span data-ttu-id="6d4e2-124">Confirmaciones suspendidas</span><span class="sxs-lookup"><span data-stu-id="6d4e2-124">Suspended acknowledgments</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d4e2-125">Síntoma</span><span class="sxs-lookup"><span data-stu-id="6d4e2-125">Symptom</span></span>  
 <span data-ttu-id="6d4e2-126">Confirmaciones se suspenden con el mensaje de error "Se encontró en el campo el delimitador" cuando se ha configurado la entidad para que la codificación de caracteres que contiene caracteres delimitadores como @-! $.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-126">Acknowledgments are suspended with the error message "Delimiter found in the field" when you have configured the party to have encoding characters containing delimiter characters such as @-!$.</span></span>  
  
<span data-ttu-id="6d4e2-127">**Causa posible** : el mensaje contiene caracteres como un punto (.) o un guión (-).</span><span class="sxs-lookup"><span data-stu-id="6d4e2-127">**Possible cause** : The message contains characters such as a period (.) or a hyphen (-).</span></span> <span data-ttu-id="6d4e2-128">Al generar las confirmaciones, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] incluye "." y "-" para el valor de marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-128">When generating the ACKs, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] includes "." and "-" for the timestamp value.</span></span>  
  
<span data-ttu-id="6d4e2-129">**Resolución** : deshabilitar la validación en la canalización de envío para evitar estos errores.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-129">**Resolution** : Disable validation in the send pipeline to avoid these errors.</span></span>  
  
## <a name="biztalk-server-generates-an-error-about-missing-ack-when-using-2-way-mllp-adapter"></a><span data-ttu-id="6d4e2-130">BizTalk Server genera un error acerca de la falta de confirmación cuando se usa el adaptador MLLP de 2 vías</span><span class="sxs-lookup"><span data-stu-id="6d4e2-130">BizTalk Server generates an error about missing ACK when using 2-way MLLP adapter</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d4e2-131">Síntoma</span><span class="sxs-lookup"><span data-stu-id="6d4e2-131">Symptom</span></span>  
 <span data-ttu-id="6d4e2-132">Obtiene el error siguiente o uno similar en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="6d4e2-132">You get the following or similar error in the Event Log:</span></span>  
  
 <span data-ttu-id="6d4e2-133">"No se pueden recibir la confirmación de red debido al error" excepción de HRESULT: 0xC0C01662 ""</span><span class="sxs-lookup"><span data-stu-id="6d4e2-133">"Unable to receive ACK from network due to error "Exception from HRESULT: 0xC0C01662""</span></span>  
  
<span data-ttu-id="6d4e2-134">**Causa posible** : utilizas 1-modo de recepción y el puerto de envío de 2 vías, por lo que BizTalk no tiene un puerto de recepción correspondiente para devolver el mensaje recibido desde el puerto de envío de 2 vías.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-134">**Possible cause** : You are using 1-way receive and 2-way send port, so BizTalk does not have a corresponding Receive port to return the message received from the 2-way Send port.</span></span>  
  
<span data-ttu-id="6d4e2-135">**Resolución** : Esto es así por diseño, y puede pasar por alto el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="6d4e2-135">**Resolution** : This is by design, and you can ignore the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4e2-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d4e2-136">See Also</span></span>  
[<span data-ttu-id="6d4e2-137">Solución de problemas y problemas conocidos de HL7</span><span class="sxs-lookup"><span data-stu-id="6d4e2-137">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)