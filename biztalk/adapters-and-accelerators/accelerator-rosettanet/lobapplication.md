---
title: LOBApplication | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trading partners, submitting actions
- LOBs, submitting actions
- LOBApplication utility
- trading partners, response messages
- LOBs, LOBApplication utility
- LOBs, response messages
ms.assetid: ad5986af-4175-49cd-806b-04e1fde63f55
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bacce1a64f59d61b5175b10fc14cde1ca862635
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855535"
---
# <a name="lobapplication"></a><span data-ttu-id="d0ba4-102">LOBApplication</span><span class="sxs-lookup"><span data-stu-id="d0ba4-102">LOBApplication</span></span>
<span data-ttu-id="d0ba4-103">Use la utilidad LOBApplication para enviar un mensaje de acción o respuesta a un socio comercial, simulando un programa de escritorio real de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="d0ba4-103">You use the LOBApplication utility to submit an action or response message to a trading partner, simulating an actual line-of-business (LOB) desktop program.</span></span>  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="d0ba4-104">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] incluye ejemplos de mensajes en el \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\LOBApplication\ Carpeta SampleInstances.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-104">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides sample messages in the \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="d0ba4-105">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="d0ba4-105">Location in SDK</span></span>  
 <span data-ttu-id="d0ba4-106">\<*unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\LOBApplication</span><span class="sxs-lookup"><span data-stu-id="d0ba4-106">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication</span></span>  
  
## <a name="running-lobapplication"></a><span data-ttu-id="d0ba4-107">Ejecutando LOBApplication</span><span class="sxs-lookup"><span data-stu-id="d0ba4-107">Running LOBApplication</span></span>  
  
#### <a name="to-run-lobapplication"></a><span data-ttu-id="d0ba4-108">Para ejecutar LOBApplication</span><span class="sxs-lookup"><span data-stu-id="d0ba4-108">To run LOBApplication</span></span>  
  
1.  <span data-ttu-id="d0ba4-109">En el Explorador de Windows, desplácese a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-109">In Windows Explorer, move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
2.  <span data-ttu-id="d0ba4-110">Haga doble clic en **LOBApplication.exe**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-110">Double-click **LOBApplication.exe**, and then press ENTER.</span></span>  
  
     <span data-ttu-id="d0ba4-111">Las páginas siguientes le solicitan ingresar la información necesaria para ejecutar la utilidad.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-111">The pages that follow prompt you for the information that is required to run the utility.</span></span>  
  
## <a name="syntax-for-lobapplication"></a><span data-ttu-id="d0ba4-112">Sintaxis de LOBApplication</span><span class="sxs-lookup"><span data-stu-id="d0ba4-112">Syntax for LOBApplication</span></span>  
 <span data-ttu-id="d0ba4-113">Use la **Proxy de aplicación de LOB** página para especificar propiedades de mensaje para el mensaje enviado por la utilidad LOBApplication, propiedades del proceso de interfaz de socio (PIP) y nombres de inicio y de los asociados.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-113">Use the **LOB Application Proxy** page to specify home and partner names, Partner Interface Process (PIP) properties, and message properties for the message sent by the LOBApplication utility.</span></span>  
  
 <span data-ttu-id="d0ba4-114">En la tabla siguiente describe cómo usar cada campo en el **Proxy de aplicación de LOB** página.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-114">The following table describes how to use each field on the **LOB Application Proxy** page.</span></span>  
  
|<span data-ttu-id="d0ba4-115">Use</span><span class="sxs-lookup"><span data-stu-id="d0ba4-115">Use this</span></span>|<span data-ttu-id="d0ba4-116">Para</span><span class="sxs-lookup"><span data-stu-id="d0ba4-116">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="d0ba4-117">**Nombre del perfil de inicio**</span><span class="sxs-lookup"><span data-stu-id="d0ba4-117">**Home Profile Name**</span></span>|<span data-ttu-id="d0ba4-118">Escriba el nombre de la organización principal (entidad de origen).</span><span class="sxs-lookup"><span data-stu-id="d0ba4-118">Type the name of the home organization (source party).</span></span>|  
|<span data-ttu-id="d0ba4-119">**Nombre del socio comercial**</span><span class="sxs-lookup"><span data-stu-id="d0ba4-119">**Trading Partner Name**</span></span>|<span data-ttu-id="d0ba4-120">Escriba el nombre del socio comercial (entidad de destino).</span><span class="sxs-lookup"><span data-stu-id="d0ba4-120">Type the name of the trading partner (destination party).</span></span>|  
|<span data-ttu-id="d0ba4-121">**Nombre del PIP**</span><span class="sxs-lookup"><span data-stu-id="d0ba4-121">**PIP Name**</span></span>|<span data-ttu-id="d0ba4-122">Escriba el código para mostrar del PIP, por ejemplo, tipo **3A2**.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-122">Type the display code of the PIP, for example, type **3A2**.</span></span> <span data-ttu-id="d0ba4-123">Este valor distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-123">This value is case-sensitive.</span></span>|  
|<span data-ttu-id="d0ba4-124">**Versión PIP**</span><span class="sxs-lookup"><span data-stu-id="d0ba4-124">**PIP Version**</span></span>|<span data-ttu-id="d0ba4-125">Escriba el número de versión del PIP, por ejemplo, tipo **V02.00**.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-125">Type the version of the PIP, for example, type **V02.00**.</span></span> <span data-ttu-id="d0ba4-126">Este valor distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-126">This value is case-sensitive.</span></span>|  
|<span data-ttu-id="d0ba4-127">**Id. de instancia PIP** (opcional)</span><span class="sxs-lookup"><span data-stu-id="d0ba4-127">**PIP Instance ID** (optional)</span></span>|<span data-ttu-id="d0ba4-128">Por ejemplo, escriba un identificador de instancia alfanumérico para el PIP, escriba **STD_3A2_V02.02**.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-128">Type an alphanumeric instance ID for the PIP, for example, type **STD_3A2_V02.02**.</span></span> <span data-ttu-id="d0ba4-129">Evite los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-129">Avoid special characters.</span></span> <span data-ttu-id="d0ba4-130">El identificador debe ser único por socio comercial y por código PIP.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-130">The ID should be unique per partner and per PIP code.</span></span> <span data-ttu-id="d0ba4-131">Para los mensajes que están marcados como mensajes de acción, si el identificador de instancia está vacío, la utilidad LOBApplication utiliza el valor HUID generado para el identificador de instancia de PIP.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-131">For messages that are marked as action messages, if the Instance ID is empty, the LOBApplication utility uses a generated HUID value for the PIP Instance ID.</span></span> <span data-ttu-id="d0ba4-132">**Nota:** cuando selecciona **respuesta** en el **categoría del mensaje**, debe escribir el identificador de instancia PIP en este campo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-132">**Note:**  When you select **Response** in the **Message Category**, you must type the PIP Instance ID in this field.</span></span>|  
|<span data-ttu-id="d0ba4-133">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="d0ba4-133">**File Name**</span></span>|<span data-ttu-id="d0ba4-134">Haga clic en el botón de puntos suspensivos (...), vaya a la carpeta que contiene el archivo de instancia PIP y, a continuación, haga clic en el archivo de instancia PIP.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-134">Click the ellipsis button (...), go to the folder that contains the PIP instance file, and then click the PIP instance file.</span></span>|  
|<span data-ttu-id="d0ba4-135">**Categoría de mensaje**</span><span class="sxs-lookup"><span data-stu-id="d0ba4-135">**Message Category**</span></span>|<span data-ttu-id="d0ba4-136">Seleccione el tipo de mensaje (**acción** o **respuesta**).</span><span class="sxs-lookup"><span data-stu-id="d0ba4-136">Select the type of message (**Action** or **Response**).</span></span>|  
|<span data-ttu-id="d0ba4-137">**Datos adjuntos**</span><span class="sxs-lookup"><span data-stu-id="d0ba4-137">**Attachments**</span></span>|<span data-ttu-id="d0ba4-138">Haga clic en **agregar**, desplácese a la carpeta que contiene el archivo de datos adjuntos y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-138">Click **Add**, move to the folder that contains the attachment file, and then click **Open**.</span></span>|  
|<span data-ttu-id="d0ba4-139">**Enviar mensaje**</span><span class="sxs-lookup"><span data-stu-id="d0ba4-139">**Submit Message**</span></span>|<span data-ttu-id="d0ba4-140">Haga clic aquí para enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-140">Click to send the message.</span></span>|  
|<span data-ttu-id="d0ba4-141">**Estado**</span><span class="sxs-lookup"><span data-stu-id="d0ba4-141">**Status**</span></span>|<span data-ttu-id="d0ba4-142">Leer el estado de la acción en este campo.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-142">Read the status of the action in this field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0ba4-143">Notas</span><span class="sxs-lookup"><span data-stu-id="d0ba4-143">Remarks</span></span>  
 <span data-ttu-id="d0ba4-144">La utilidad LOBApplication crea un mensaje con las propiedades especificadas y lo envía al socio comercial.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-144">The LOBApplication utility creates a message with the properties specified, and sends it to the trading partner.</span></span> <span data-ttu-id="d0ba4-145">Esta utilidad escribe los datos de contenido del servicio en el mensaje en la base de datos BTARNDATA, en la tabla MessageFromLOB.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-145">This utility writes the service content data in the message to the BTARNDATA database, in the MessageFromLOB table.</span></span> <span data-ttu-id="d0ba4-146">Esta utilidad simula el envío de un mensaje de acción.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-146">This utility simulates sending an action message.</span></span>  
  
 <span data-ttu-id="d0ba4-147">Los mensajes de ejemplo en la carpeta SampleInstances en la carpeta LOBApplication en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK están preconfigurados para supone los siguientes identificadores globales de negocio (GBIs): 123456789 para la organización principal y 987654321 para el socio comercial organización.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-147">The sample messages in the SampleInstances folder under the LOBApplication folder in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK are preconfigured to assume the following Global Business Identifiers (GBIs): 123456789 for the home organization and 987654321 for the partner organization.</span></span> <span data-ttu-id="d0ba4-148">Debe cambiar los mensajes de ejemplo en un editor de texto para usar otros GBIs.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-148">You must change the sample messages in a text editor to use other GBIs.</span></span>  
  
 <span data-ttu-id="d0ba4-149">Use la utilidad LOBApplication para simular un programa de escritorio de línea de negocio enviando un mensaje.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-149">You use the LOBApplication utility to simulate a line-of-business desktop program submitting a message.</span></span> <span data-ttu-id="d0ba4-150">Use la utilidad LOBWebApplication para simular una aplicación Web de línea de negocio enviando un mensaje.</span><span class="sxs-lookup"><span data-stu-id="d0ba4-150">You use the LOBWebApplication utility to simulate a line-of-business Web application submitting a message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ba4-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0ba4-151">See Also</span></span>  
 <span data-ttu-id="d0ba4-152">[Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="d0ba4-152">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="d0ba4-153">LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="d0ba4-153">LOBWebApplication</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)
