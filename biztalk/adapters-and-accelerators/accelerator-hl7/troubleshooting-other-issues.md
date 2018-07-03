---
title: Otros problemas de solución de problemas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 1f115f64-45ce-445d-ab18-092f4a6a232c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2753d85050506d5b8ca05ca3b3438bb767a26322
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009501"
---
# <a name="troubleshooting-other-issues"></a><span data-ttu-id="95593-102">Solucionar otros problemas</span><span class="sxs-lookup"><span data-stu-id="95593-102">Troubleshooting Other Issues</span></span>
<span data-ttu-id="95593-103">Direcciones de otros problemas relacionados con Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95593-103">Addresses other issues related to Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  
  
## <a name="message-rejected-by-the-btahl7-engine"></a><span data-ttu-id="95593-104">Mensajes rechazados por el motor de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="95593-104">Message rejected by the BTAHL7 engine</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="95593-105">Síntoma</span><span class="sxs-lookup"><span data-stu-id="95593-105">Symptom</span></span>  
 <span data-ttu-id="95593-106">Los mensajes se rechazan aleatoriamente por el motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="95593-106">Messages are randomly rejected by the message engine.</span></span>  
  
<span data-ttu-id="95593-107">**Causa posible** : según el estándar HL7, enumeración los valores de tabla 0338 contiene el valor "L & me".</span><span class="sxs-lookup"><span data-stu-id="95593-107">**Possible Cause** : According to the HL7 standard, enumeration values for table 0338 contains the "L&I" value.</span></span> <span data-ttu-id="95593-108">6 de campo del segmento PRA puede contener este valor.</span><span class="sxs-lookup"><span data-stu-id="95593-108">Field 6 of the PRA segment may contain this value.</span></span> <span data-ttu-id="95593-109">Puesto que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el carácter "&" se trata como un delimitador, se rechaza el mensaje.</span><span class="sxs-lookup"><span data-stu-id="95593-109">Since [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] treats the "&" character as a delimiter, the message is rejected.</span></span>  
  
<span data-ttu-id="95593-110">**Resolución** : existen tres posibles soluciones para resolver este problema:</span><span class="sxs-lookup"><span data-stu-id="95593-110">**Resolution** : There are three potential resolutions for this issue:</span></span>  
  
1.  <span data-ttu-id="95593-111">En la instancia de mensaje, controlar el carácter "&" a través de una secuencia de escape, como el uso de la combinación de caracteres L\T\I.</span><span class="sxs-lookup"><span data-stu-id="95593-111">In the message instance, handle the "&" character through an escape sequence, such as using the character combination L\T\I.</span></span>  
  
2.  <span data-ttu-id="95593-112">Agregar un valor de enumeración de "LI" en PRA 6 en el esquema y use este valor en su lugar en la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="95593-112">Add an enumeration value of "LI" at PRA 6 in the schema and use this value instead in the message instance.</span></span>  
  
3.  <span data-ttu-id="95593-113">Utilizar un separador de subcomponente completamente diferente en MSH2; Sin embargo, esta solución concreto puede no resultar práctica de función de su entorno.</span><span class="sxs-lookup"><span data-stu-id="95593-113">Use a completely different subcomponent separator in MSH2; however, this particular solution may not be practical depending upon your environment.</span></span>  
  
## <a name="cannot-edit-the-hl7-schema-using-visual-studio"></a><span data-ttu-id="95593-114">No se puede editar el esquema HL7 con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="95593-114">Cannot edit the HL7 schema using Visual Studio</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="95593-115">Síntoma</span><span class="sxs-lookup"><span data-stu-id="95593-115">Symptom</span></span>  
 <span data-ttu-id="95593-116">No se puede editar el esquema de HL7 mediante Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95593-116">Cannot edit the HL7 schema using Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
<span data-ttu-id="95593-117">**Causa posible** : [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] no admite algunos esquemas de HL7.</span><span class="sxs-lookup"><span data-stu-id="95593-117">**Possible Cause** : [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] does not support some HL7 schemas.</span></span>  
  
<span data-ttu-id="95593-118">**Resolución** : Use otros editores, como Microsoft Notepad, para editar esquemas de HL7.</span><span class="sxs-lookup"><span data-stu-id="95593-118">**Resolution** : Use other editors, such as Microsoft Notepad, to edit HL7 schemas.</span></span>  
  
## <a name="message-handling-fails-with-no-errors-logged"></a><span data-ttu-id="95593-119">Se produce un error en el control de mensajes sin errores registrados</span><span class="sxs-lookup"><span data-stu-id="95593-119">Message handling fails with no errors logged</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="95593-120">Síntoma</span><span class="sxs-lookup"><span data-stu-id="95593-120">Symptom</span></span>  
 <span data-ttu-id="95593-121">El sistema procesa los mensajes sin registrar los mensajes de error o colocar los mensajes en la cola de mensajes suspendidos.</span><span class="sxs-lookup"><span data-stu-id="95593-121">The system processes messages without logging error messages or placing messages in the suspended message queue.</span></span>  
  
<span data-ttu-id="95593-122">**Causa posible** : el **HeaderSpecType** y **DocumentSpecType** los valores de propiedad distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="95593-122">**Possible Cause** : The **HeaderSpecType** and **DocumentSpecType** property values are case-sensitive.</span></span> <span data-ttu-id="95593-123">Al implementar las canalizaciones, un error tipográfico en estos nombres pueden que los mensajes se maneja y colocar sin errores registrados.</span><span class="sxs-lookup"><span data-stu-id="95593-123">When you deploy your pipelines, a typographical error in these names can cause messages to be mishandled and dropped with no errors logged.</span></span>  
  
<span data-ttu-id="95593-124">**Resolución** : Observe a minúsculas cuando se usa el **HeaderSpecType** y **DocumentSpecType** los nombres de valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="95593-124">**Resolution** : Observe case-sensitivity when using the **HeaderSpecType** and **DocumentSpecType** property value names.</span></span>  
  
## <a name="message-header-fields-are-not-validated-correctly"></a><span data-ttu-id="95593-125">Campos de encabezado de mensaje no se ha validado correctamente</span><span class="sxs-lookup"><span data-stu-id="95593-125">Message header fields are not validated correctly</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="95593-126">Síntoma</span><span class="sxs-lookup"><span data-stu-id="95593-126">Symptom</span></span>  
 <span data-ttu-id="95593-127">Error al validar un campo de encabezado.</span><span class="sxs-lookup"><span data-stu-id="95593-127">Validation of a header field failed.</span></span>  
  
 <span data-ttu-id="95593-128">Motivo: El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador valida una propiedad promocionada, no la propiedad de contexto de campo de encabezado real.</span><span class="sxs-lookup"><span data-stu-id="95593-128">Reason: The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer validated a promoted property, not the actual header-field context property.</span></span>  
  
<span data-ttu-id="95593-129">**Causa posible** : se ha producido un cambio a la propiedad promocionada correspondiente al encabezado a través de una orquestación o un mapa.</span><span class="sxs-lookup"><span data-stu-id="95593-129">**Possible Cause** : A change occurred to the promoted property corresponding to the header through an orchestration or a map.</span></span>  
  
<span data-ttu-id="95593-130">**Resolución** : las propiedades de contexto de encabezados de mensaje MSH1 MSH2 y MSH5{1-3} deben actualizarse para que estén en la sincronización con los datos.</span><span class="sxs-lookup"><span data-stu-id="95593-130">**Resolution** : The context properties of message headers MSH1, MSH2, and MSH5{1-3} need to be updated so that they are in synchronization with the data.</span></span>  
  
## <a name="the-mllp-adapter-is-not-removed-during-uninstall"></a><span data-ttu-id="95593-131">No se quita el adaptador MLLP durante la desinstalación</span><span class="sxs-lookup"><span data-stu-id="95593-131">The MLLP adapter is not removed during uninstall</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="95593-132">Síntoma</span><span class="sxs-lookup"><span data-stu-id="95593-132">Symptom</span></span>  
 <span data-ttu-id="95593-133">El programa de instalación de BTAHL7 no quitó el adaptador MLLP durante la desinstalación de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="95593-133">The BTAHL7 setup program did not remove the MLLP adapter during uninstallation of BTAHL7.</span></span>  
  
<span data-ttu-id="95593-134">**Causa posible** : se ha producido un puerto de envío o ubicación de recepción con un tipo de transporte de MLLP.</span><span class="sxs-lookup"><span data-stu-id="95593-134">**Possible Cause** : There was a receive location or send port with a transport type of MLLP.</span></span> <span data-ttu-id="95593-135">El programa de instalación de BTAHL7 no puede quitar el adaptador MLLP si es que se hace referencia en cualquiera de los proyectos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="95593-135">BTAHL7 setup cannot remove the MLLP adapter if it is being referenced in any of the BizTalk Server projects.</span></span>  
  
<span data-ttu-id="95593-136">**Resolución** : una vez completada la desinstalación de BTAHL7, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95593-136">**Resolution** : After uninstallation of BTAHL7 has completed, do the following:</span></span>  
  
1.  <span data-ttu-id="95593-137">En la consola de administración de BizTalk Server, quite todas las ubicaciones de recepción y puertos de envío que tienen un tipo de transporte de MLLP, o cambiar el tipo de transporte de las ubicaciones de recepción o puertos de envío a otro tipo.</span><span class="sxs-lookup"><span data-stu-id="95593-137">In the BizTalk Server Administration Console, remove all receive locations and send ports that have a transport type of MLLP, or change the transport type of the receive locations or send ports to another type.</span></span>  
  
2.  <span data-ttu-id="95593-138">En la consola de administración, elimine el adaptador de MLLP.</span><span class="sxs-lookup"><span data-stu-id="95593-138">In the Administration Console, delete the MLLP adapter.</span></span>  
  
3.  <span data-ttu-id="95593-139">Reinicie la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="95593-139">Restart the host instance.</span></span>  
  
## <a name="btahl7-cannot-be-uninstalled-if-biztalk-server-has-already-been-uninstalled"></a><span data-ttu-id="95593-140">No se puede desinstalar BTAHL7 si ya se ha desinstalado el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="95593-140">BTAHL7 cannot be uninstalled if BizTalk Server has already been uninstalled</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="95593-141">Síntoma</span><span class="sxs-lookup"><span data-stu-id="95593-141">Symptom</span></span>  
 <span data-ttu-id="95593-142">Desinstalar [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] da como resultado el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="95593-142">Uninstalling [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] results in the following error:</span></span>  
  
`A network error while attempting to read from file C:\Windows\Installer\Microsoft BizTalk <version\> Accelerator for HL7.msi`
  
<span data-ttu-id="95593-143">**Causa posible** : [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] se desinstaló antes de la desinstalación de [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] se ha intentado.</span><span class="sxs-lookup"><span data-stu-id="95593-143">**Possible Cause** : [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] was uninstalled before uninstallation of [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] was attempted.</span></span> <span data-ttu-id="95593-144">Debe desinstalar [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] antes de desinstalar [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95593-144">You must uninstall [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] before uninstalling [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
<span data-ttu-id="95593-145">**Resolución** : reinstalar [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], a continuación, desinstale [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]y, a continuación, desinstale [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95593-145">**Resolution** : Reinstall [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], then uninstall [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)], and then uninstall [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="messages-are-still-sent-after-the-applicable-mllp-send-port-has-been-stopped"></a><span data-ttu-id="95593-146">Todavía se envían los mensajes una vez detenido el puerto de envío MLLP aplicable</span><span class="sxs-lookup"><span data-stu-id="95593-146">Messages are still sent after the applicable MLLP send port has been stopped</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="95593-147">Síntoma</span><span class="sxs-lookup"><span data-stu-id="95593-147">Symptom</span></span>  
 <span data-ttu-id="95593-148">Después de detener un MLLP puerto de envío, los mensajes que se envían a través de ese puerto de envío no detiene, pero seguirán enviándose.</span><span class="sxs-lookup"><span data-stu-id="95593-148">After you stop an MLLP send port, the messages that are sent through that send port do not stop, but continue to be sent.</span></span>  
  
<span data-ttu-id="95593-149">**Causa posible** : cuando se detiene un puerto de envío, la conexión permanece establecida hasta que se quita al detener el host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="95593-149">**Possible Cause** : When you stop a send port, the connection remains established until it is removed by stopping the BizTalk host.</span></span> <span data-ttu-id="95593-150">Como resultado, los mensajes se siguen enviando una vez detenido el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="95593-150">As a result, messages are still sent after the send port has been stopped.</span></span> <span data-ttu-id="95593-151">Esto ocurre porque Biztalk Server no llama a en el adaptador MLLP durante el inicio o detención del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="95593-151">This occurs because Biztalk Server does not call into the MLLP adapter during start or stop of the send port.</span></span> <span data-ttu-id="95593-152">BizTalk Server llama al adaptador de MLLP solo durante el inicio y detención del servicio de host.</span><span class="sxs-lookup"><span data-stu-id="95593-152">BizTalk Server calls into the MLLP adapter only during the start and stop of the host service.</span></span>  
  
<span data-ttu-id="95593-153">**Resolución** : puede quitar la conexión y detener transmisión de mensajes, detenga la instancia de host es el controlador de envío para el puerto de envío que ha detenido.</span><span class="sxs-lookup"><span data-stu-id="95593-153">**Resolution** : You can remove the connection and stop transmission of messages by stopping the host instance that is the send handler for the send port that you stopped.</span></span> <span data-ttu-id="95593-154">Sin embargo, la detención de dicha instancia de host puede afectar a otros mensajes que no desea detener.</span><span class="sxs-lookup"><span data-stu-id="95593-154">However, stopping that host instance might affect other messages that you do not want to stop.</span></span> <span data-ttu-id="95593-155">Si sabe que este es el caso, debe configurar el puerto de envío de forma diferente al crearla.</span><span class="sxs-lookup"><span data-stu-id="95593-155">If you know that this is the case, you should configure the send port differently when you create it.</span></span> <span data-ttu-id="95593-156">Debe crear otra instancia de host para que actúe como controlador de envío sólo este puerto de envío MLLP (o un subconjunto de los puertos de envío).</span><span class="sxs-lookup"><span data-stu-id="95593-156">You should create another host instance to serve as the send handler for only this MLLP send port (or a subset of your send ports).</span></span> <span data-ttu-id="95593-157">A continuación, puede detener transmisión de mensajes desde este puerto de envío deteniendo esta instancia de host.</span><span class="sxs-lookup"><span data-stu-id="95593-157">You can then stop transmission of messages from this send port by stopping this host instance.</span></span> <span data-ttu-id="95593-158">Esto, a continuación, no afectará a la transmisión de mensajes en otros puertos de envío que usan otros controladores de envío.</span><span class="sxs-lookup"><span data-stu-id="95593-158">This will then not affect transmission of other messages on other send ports that use other send handlers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95593-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="95593-159">See Also</span></span>  
 [<span data-ttu-id="95593-160">Solución de problemas y problemas conocidos en HL7</span><span class="sxs-lookup"><span data-stu-id="95593-160">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)