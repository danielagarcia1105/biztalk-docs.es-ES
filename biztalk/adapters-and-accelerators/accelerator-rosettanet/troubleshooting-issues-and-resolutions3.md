---
title: "Solución de problemas: Problemas y Resolutions3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: 40f59f54-183e-43db-afb5-0a45b437697f
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed990dd60ab65c7b85284a9eeadd4b27de3136f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-issues-and-resolutions"></a><span data-ttu-id="4e33b-102">Solución de problemas: Problemas y soluciones</span><span class="sxs-lookup"><span data-stu-id="4e33b-102">Troubleshooting: Issues and Resolutions</span></span>
<span data-ttu-id="4e33b-103">Este tema tratan los problemas relacionados con la ejecución [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e33b-103">This topic addresses issues related to running [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="4e33b-104">La persona emite detalle un síntoma específico, una posible causa y una solución.</span><span class="sxs-lookup"><span data-stu-id="4e33b-104">The individual issues detail a specific symptom, a possible cause, and a solution.</span></span>  
  
## <a name="error-publishing-a-batch-of-n-messages"></a><span data-ttu-id="4e33b-105">Error al publicar un lote de mensajes "n"</span><span class="sxs-lookup"><span data-stu-id="4e33b-105">Error publishing a batch of "n" messages</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-106">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-106">Symptom</span></span>  
 <span data-ttu-id="4e33b-107">Recibe el error siguiente o uno similar en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="4e33b-107">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="4e33b-108">El motor de mensajería detectó un error al publicar un lote de mensajes "n" en la base de datos de cuadro de mensaje para el adaptador de transporte "Receptor HTTP de BizTalk".</span><span class="sxs-lookup"><span data-stu-id="4e33b-108">The Messaging Engine encountered an error publishing a batch of "n" messages to the Message Box database for the transport adapter "BizTalk HTTP Receiver".</span></span> <span data-ttu-id="4e33b-109">Consulte herramienta de seguimiento de estado y actividad para obtener más información sobre este error y compruebe que los enlaces de extremo están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e33b-109">Please refer to Health and Activity Tracking tool for more detailed information on this failure and check the endpoint bindings are correctly configured.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-110">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-110">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-111">Este error podría deberse a uno de los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="4e33b-111">This error could be caused by one of the following reasons:</span></span>  
  
-   <span data-ttu-id="4e33b-112">Falta el certificado de descifrado</span><span class="sxs-lookup"><span data-stu-id="4e33b-112">Missing decryption certificate</span></span>  
  
-   <span data-ttu-id="4e33b-113">Mensaje cifrado incorrectamente</span><span class="sxs-lookup"><span data-stu-id="4e33b-113">Incorrectly encrypted message</span></span>  
  
-   <span data-ttu-id="4e33b-114">Mensaje no autorizado (origen no se reconoce como un socio válido)</span><span class="sxs-lookup"><span data-stu-id="4e33b-114">Unauthorized message (source not recognized as a valid partner)</span></span>  
  
-   <span data-ttu-id="4e33b-115">Errores de validación de cualquier parte del encabezado de mensaje: preámbulo, encabezado de entrega o encabezado de servicio.</span><span class="sxs-lookup"><span data-stu-id="4e33b-115">Message failing validation of any header part: preamble, delivery header, or service header.</span></span>  
  
 <span data-ttu-id="4e33b-116">Este mensaje puede ir precedido de otro mensaje de error que detalla a la causa.</span><span class="sxs-lookup"><span data-stu-id="4e33b-116">This message may be preceded by another error message that details the cause.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-117">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-117">Solution</span></span>  
 <span data-ttu-id="4e33b-118">Revise los detalles proporcionados con el mensaje de error para obtener ayuda adicional.</span><span class="sxs-lookup"><span data-stu-id="4e33b-118">Review the details provided with the error message for additional help.</span></span> <span data-ttu-id="4e33b-119">Reiniciar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™ puede resolver este problema.</span><span class="sxs-lookup"><span data-stu-id="4e33b-119">Restarting [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™ may resolve this issue.</span></span>  
  
## <a name="you-cannot-unenlist-all-artifacts"></a><span data-ttu-id="4e33b-120">No se puede dar de baja todos los artefactos</span><span class="sxs-lookup"><span data-stu-id="4e33b-120">You cannot unenlist all artifacts</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-121">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-121">Symptom</span></span>  
 <span data-ttu-id="4e33b-122">Ejecuta el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]utilidad limpia no dar de baja todos los artefactos.</span><span class="sxs-lookup"><span data-stu-id="4e33b-122">Running the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Clean utility does not unenlist all artifacts.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-123">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-123">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-124">Si ejecuta el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]limpiar utilidad antes de eliminar acuerdos y socios de la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Management Console (MMC), la utilidad BtarnClean no podrá dar de baja todos los artefactos porque todavía se usan.</span><span class="sxs-lookup"><span data-stu-id="4e33b-124">If you run the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Clean utility before deleting agreements and partners from the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Management Console (MMC), the BtarnClean utility will not be able to unenlist all artifacts because they are still used.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-125">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-125">Solution</span></span>  
  
##### <a name="to-remove-artifacts-using-the-loopback-utility"></a><span data-ttu-id="4e33b-126">Para quitar artefactos mediante la utilidad de bucle invertido</span><span class="sxs-lookup"><span data-stu-id="4e33b-126">To remove artifacts using the Loopback utility</span></span>  
  
1.  <span data-ttu-id="4e33b-127">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="4e33b-127">At the command prompt, type:</span></span>  
  
    ```  
    lookback.exe /disable <home org or partner>  
    ```  
  
2.  <span data-ttu-id="4e33b-128">Ejecute el archivo BtarnClean.exe.</span><span class="sxs-lookup"><span data-stu-id="4e33b-128">Run the BtarnClean.exe file.</span></span>  
  
3.  <span data-ttu-id="4e33b-129">En el Explorador de BizTalk, elimine las partes.</span><span class="sxs-lookup"><span data-stu-id="4e33b-129">In BizTalk Explorer, delete the parties.</span></span>  
  
## <a name="installing-btarn-on-a-computer-without-biztalk-server-causes-missing-files"></a><span data-ttu-id="4e33b-130">Instalación de BTARN en un equipo sin BizTalk Server hace que los archivos que faltan</span><span class="sxs-lookup"><span data-stu-id="4e33b-130">Installing BTARN on a computer without BizTalk Server causes missing files</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-131">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-131">Symptom</span></span>  
 <span data-ttu-id="4e33b-132">Ejecutar el archivo ConfigFramework.exe no produce ningún resultado en un equipo que no tiene [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] o [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] instalado.</span><span class="sxs-lookup"><span data-stu-id="4e33b-132">Running the ConfigFramework.exe file yields no results on a computer that does not have [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] or [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed.</span></span> <span data-ttu-id="4e33b-133">Sólo se puede utilizar esto [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuración como un cliente HTTP.</span><span class="sxs-lookup"><span data-stu-id="4e33b-133">You can only use this [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration as an HTTP client.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-134">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-134">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-135">Faltan dos archivos DLL de la instalación.</span><span class="sxs-lookup"><span data-stu-id="4e33b-135">Two DLL files are missing from the installation.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-136">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-136">Solution</span></span>  
 <span data-ttu-id="4e33b-137">Instale SQLXML en el equipo y, a continuación, copie manualmente los archivos Msxml4.dll y Atl71.dll a la carpeta del sistema.</span><span class="sxs-lookup"><span data-stu-id="4e33b-137">Install SQLXML on the computer, and then manually copy the Msxml4.dll and Atl71.dll files to the System folder.</span></span>  
  
## <a name="you-receive-an-access-error-when-attempting-to-change-the-btarn-configuration"></a><span data-ttu-id="4e33b-138">Recibirá un error de acceso al intentar cambiar la configuración de BTARN</span><span class="sxs-lookup"><span data-stu-id="4e33b-138">You receive an access error when attempting to change the BTARN configuration</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-139">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-139">Symptom</span></span>  
 <span data-ttu-id="4e33b-140">Recibirá el siguiente mensaje de error al importar un archivo de configuración mediante el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración:</span><span class="sxs-lookup"><span data-stu-id="4e33b-140">You receive the following error message when you import a configuration file using the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console:</span></span>  
  
 <span data-ttu-id="4e33b-141">No se pudo almacenar datos de tipo de transporte para principal transporte del puerto de envío ' RNSTT. Async' para el almacén de configuración.</span><span class="sxs-lookup"><span data-stu-id="4e33b-141">Could not store transport type data for Primary Transport of Send Port 'RNSTT.Async' to config store.</span></span> <span data-ttu-id="4e33b-142">Acceso denegado.</span><span class="sxs-lookup"><span data-stu-id="4e33b-142">Access is denied.</span></span>  
  
 <span data-ttu-id="4e33b-143">También puede recibir este error al intentar cambiar la configuración, por ejemplo, mediante la creación de un asociado de nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e33b-143">You can also receive this error when you try to change the configuration, such as by creating a new partner.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-144">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-144">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-145">El usuario actual no es un miembro del grupo Administradores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4e33b-145">The current user is not a member of the BizTalk Administrators group.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-146">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-146">Solution</span></span>  
 <span data-ttu-id="4e33b-147">Asegúrese de que el usuario actual es un miembro del grupo Administradores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4e33b-147">Make sure that the current user is a member of the BizTalk Administrators group.</span></span>  
  
## <a name="you-receive-bam-errors"></a><span data-ttu-id="4e33b-148">Recibe errores BAM</span><span class="sxs-lookup"><span data-stu-id="4e33b-148">You receive BAM errors</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-149">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-149">Symptom</span></span>  
 <span data-ttu-id="4e33b-150">Recibir los mensajes de error siguientes en el Visor de eventos:</span><span class="sxs-lookup"><span data-stu-id="4e33b-150">You receive the following error messages in the Event Viewer:</span></span>  
  
 <span data-ttu-id="4e33b-151">Se produjo un error en el seguimiento de la actividad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="4e33b-151">Error happened in tracking Message activity.</span></span> <span data-ttu-id="4e33b-152">Mensaje de error es almacenado no existe el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4e33b-152">Error message is Stored Procedure Does Not Exist.</span></span>  
  
 <span data-ttu-id="4e33b-153">-O bien-</span><span class="sxs-lookup"><span data-stu-id="4e33b-153">-or-</span></span>  
  
 <span data-ttu-id="4e33b-154">Error al terminar la actividad de BAM de mensajes con el identificador  *\<número de Id. >*.</span><span class="sxs-lookup"><span data-stu-id="4e33b-154">Error in terminating BAM message activity with id *\<ID number>*.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-155">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-155">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-156">La herramienta de seguimiento de supervisión de la actividad económica (BAM) no está instalada.</span><span class="sxs-lookup"><span data-stu-id="4e33b-156">The Business Activity Monitoring (BAM) tracking tool is not installed.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-157">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-157">Solution</span></span>  
 <span data-ttu-id="4e33b-158">Instalar la herramienta uso de seguimiento de BAM el **instalación personalizada** opción.</span><span class="sxs-lookup"><span data-stu-id="4e33b-158">Install the BAM tracking tool using the **Custom Installation** option.</span></span> <span data-ttu-id="4e33b-159">Si no necesita funcionalidad BAM, puede omitir estos mensajes o deshabilitar el seguimiento mediante la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="4e33b-159">If you do not need BAM functionality, you can ignore these messages or disable tracking using the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="4e33b-160">Después de deshabilitar el seguimiento, debe reiniciar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y en Internet y en Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="4e33b-160">After you disable tracking, you must restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and Internet and Information Services (IIS).</span></span>  
  
## <a name="your-xsd-schema-does-not-display-properly-in-biztalk-editor"></a><span data-ttu-id="4e33b-161">El esquema XSD no se muestren correctamente en el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4e33b-161">Your XSD Schema does not display properly in BizTalk Editor</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-162">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-162">Symptom</span></span>  
 <span data-ttu-id="4e33b-163">No se puede ver el contenido de un esquema correctamente en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4e33b-163">You cannot view the content of a schema properly in BizTalk Editor.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-164">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-164">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-165">El esquema es falta el `displayroot_reference` de atributo para el `schemaInfo` elemento.</span><span class="sxs-lookup"><span data-stu-id="4e33b-165">The schema is missing the `displayroot_reference` attribute for the `schemaInfo` element.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-166">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-166">Solution</span></span>  
 <span data-ttu-id="4e33b-167">Abra el esquema en el Bloc de notas u otro editor de texto y agregue el `displayroot_reference` atribuir a la `schemaInfo` elemento.</span><span class="sxs-lookup"><span data-stu-id="4e33b-167">Open the schema in Notepad or another text editor and add the `displayroot_reference` attribute to the `schemaInfo` element.</span></span> <span data-ttu-id="4e33b-168">El valor de la `displayroot_reference` atributo debe ser el mismo que el `root_reference` atributo.</span><span class="sxs-lookup"><span data-stu-id="4e33b-168">The value of the `displayroot_reference` attribute should be the same as the `root_reference` attribute.</span></span>  
  
 <span data-ttu-id="4e33b-169">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4e33b-169">For example:</span></span>  
  
 <span data-ttu-id="4e33b-170">\<schemaInfo document_type = "4A1" version = "V02_00" xmlns = "http://schemas.microsoft.com/BizTalk/2003" *displayroot_reference = "Pip4A1StrategicForecastNotification"* root_reference = " Pip4A1StrategicForecastNotification"/ ></span><span class="sxs-lookup"><span data-stu-id="4e33b-170">\<schemaInfo document_type="4A1" version="V02_00" xmlns="http://schemas.microsoft.com/BizTalk/2003" *displayroot_reference="Pip4A1StrategicForecastNotification"* root_reference="Pip4A1StrategicForecastNotification" /></span></span>  
  
## <a name="404-not-found-error-when-sending-a-http-request"></a><span data-ttu-id="4e33b-171">404 no encontrado errores al enviar una solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="4e33b-171">404 Not found error when sending a HTTP request</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-172">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-172">Symptom</span></span>  
 <span data-ttu-id="4e33b-173">Recibir los errores siguientes o similares al enviar una solicitud HTTP:</span><span class="sxs-lookup"><span data-stu-id="4e33b-173">You receive the following or similar errors when sending a HTTP request:</span></span>  
  
 <span data-ttu-id="4e33b-174">El servidor remoto devolvió un error: (404) no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4e33b-174">The remote server returned an error: (404) Not Found.</span></span>  
  
 <span data-ttu-id="4e33b-175">No se puede enviar el mensaje a... / BTSHttpReceive.dll.</span><span class="sxs-lookup"><span data-stu-id="4e33b-175">Message cannot be sent to ../BTSHttpReceive.dll.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-176">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-176">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-177">El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (BTSHttpReceive.dll) de la DLL de extensión de Internet Server API (ISAPI) no se ha configurado en Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="4e33b-177">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Internet Server API (ISAPI) extension DLL (BTSHttpReceive.dll) has not been configured in Internet Information Services (IIS).</span></span> <span data-ttu-id="4e33b-178">Esto ocurre si no se configura la extensión de servicio web de HwsMessages HttpReceive y si esta extensión de servicio web está configurada, pero no permitida.</span><span class="sxs-lookup"><span data-stu-id="4e33b-178">This occurs if the HwsMessages HttpReceive web service extension is not configured and if this web service extension is configured, but not allowed.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-179">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-179">Solution</span></span>  
 <span data-ttu-id="4e33b-180">Para determinar si se configura la extensión de servicio web de HwsMessages HttpReceive, y si lo no está configurado, para permitirlo, realice el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="4e33b-180">To determine whether the HwsMessages HttpReceive web service extension is configured, and if it is not configured, to allow it, perform the following procedure.</span></span>  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a><span data-ttu-id="4e33b-181">Para configurar el archivo DLL de extensión ISAPI de BizTalk en IIS</span><span class="sxs-lookup"><span data-stu-id="4e33b-181">To configure the BizTalk ISAPI extension DLL in IIS</span></span>  
  
1.  <span data-ttu-id="4e33b-182">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-182">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="4e33b-183">Expanda  **\<nombre_equipo > (equipo local)**y, a continuación, haga clic en **extensiones de servicio Web**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-183">Expand **\<computer name> (local computer)**, and then click **Web Service Extensions**.</span></span>  
  
3.  <span data-ttu-id="4e33b-184">En el **extensión de servicio Web** panel, compruebe que se permite el estado de HwsMessages HttpReceive.</span><span class="sxs-lookup"><span data-stu-id="4e33b-184">In the **Web Service Extension** pane, verify that the status for HwsMessages HttpReceive is Allowed.</span></span> <span data-ttu-id="4e33b-185">Si no es así, haga clic en **HwsMessages HttpReceive**y, a continuación, haga clic en **permitir**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-185">If not, right-click **HwsMessages HttpReceive**, and then click **Allow**.</span></span>  
  
 <span data-ttu-id="4e33b-186">Si no se configura la extensión de servicio web de HwsMessages HttpReceive (no se incluye en la lista de extensiones de servicio Web en el Administrador de IIS), realice el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="4e33b-186">If the HwsMessages HttpReceive web service extension is not configured (it is not included in the Web Service Extensions list in IIS Manager), perform the following procedure.</span></span>  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a><span data-ttu-id="4e33b-187">Para configurar el archivo DLL de extensión ISAPI de BizTalk en IIS</span><span class="sxs-lookup"><span data-stu-id="4e33b-187">To configure the BizTalk ISAPI extension DLL in IIS</span></span>  
  
1.  <span data-ttu-id="4e33b-188">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-188">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="4e33b-189">Expanda  **\<nombre_equipo > (equipo local)**, haga clic en **extensiones de servicio Web**y, a continuación, haga clic en **agregar una nueva extensión de servicio Web**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-189">Expand **\<computer name> (local computer)**, right-click **Web Service Extensions**, and then click **Add a new Web service extension**.</span></span>  
  
3.  <span data-ttu-id="4e33b-190">En el **nueva extensión de servicio Web** cuadro de diálogo, en la **nombre de la extensión** , escriba **extensión de ISAPI de BizTalk**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-190">In the **New Web Service Extension** dialog box, in the **Extension Name** box, type **BizTalk ISAPI Extension**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="4e33b-191">En el **Add File** cuadro de diálogo, en la **ruta de acceso al archivo** , escriba  **\<unidad >: \Program BizTalk Server \<versión > \HttpReceive\ BTSHttpReceive.dll**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-191">In the **Add File** dialog box, in the **Path to file** box, type **\<drive>:\Program Files\Microsoft BizTalk Server \<version>\HttpReceive\BTSHttpReceive.dll**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="4e33b-192">En el **nueva extensión de servicio Web** cuadro de diálogo, seleccione **establecer el estado de extensión a permitido**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-192">In the **New Web Service Extension** dialog box, select **Set extension status to Allowed**, and then click **OK**.</span></span>  
  
## <a name="an-access-violation-occurs-when-running-the-configuration-wizard"></a><span data-ttu-id="4e33b-193">Se produce una infracción de acceso cuando se ejecuta al Asistente para configuración</span><span class="sxs-lookup"><span data-stu-id="4e33b-193">An access violation occurs when running the Configuration Wizard</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-194">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-194">Symptom</span></span>  
 <span data-ttu-id="4e33b-195">Recibe el error siguiente o uno similar en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="4e33b-195">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="4e33b-196">Una instancia de host aislado de BizTalk configurada con la cuenta de usuario '\HostSvc' no se estaba ejecutando o no existe en este equipo.</span><span class="sxs-lookup"><span data-stu-id="4e33b-196">A BizTalk isolated host instance configured with the user account '\HostSvc' was either not running or does not exist on this computer.</span></span> <span data-ttu-id="4e33b-197">Utilice la consola de administración de BizTalk para crear un nuevo host aislado o volver a configurar una existente para ejecutarse como '\hostsvc'.</span><span class="sxs-lookup"><span data-stu-id="4e33b-197">Use the BizTalk Administration Console to create a new isolated host or reconfigure an existing to run as '\hostsvc'.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-198">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-198">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-199">Para ejecutar el Asistente para configuración, el usuario debe estar configurado como\<*nombre de la máquina*> \hostsvc', no '\hostsvc'.</span><span class="sxs-lookup"><span data-stu-id="4e33b-199">To run the Configuration Wizard, the user should be configured as '\<*machine name*>\hostsvc', not '\hostsvc'.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-200">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-200">Solution</span></span>  
 <span data-ttu-id="4e33b-201">Abra la consola de administración de BizTalk y cambiar los hosts que se ejecutan en la cuenta '\hostsvc', por lo que se ejecutan en la cuenta '\<*nombre de la máquina*> \hostsvc'.</span><span class="sxs-lookup"><span data-stu-id="4e33b-201">Open the BizTalk Administration Console, and change hosts that are running under the account '\hostsvc', so that they run under the account '\<*machine name*>\hostsvc'.</span></span>  
  
## <a name="you-receive-an-error-when-importing-and-compiling-a-rosettanet-next-generation-pip-schema"></a><span data-ttu-id="4e33b-202">Recibirá un error al importar y compilar un esquema de PIP de RosettaNet siguiente generación</span><span class="sxs-lookup"><span data-stu-id="4e33b-202">You receive an error when importing and compiling a RosettaNet Next Generation PIP schema</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-203">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-203">Symptom</span></span>  
 <span data-ttu-id="4e33b-204">Recibe el error siguiente o uno similar en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="4e33b-204">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="4e33b-205">Error del CS0234: el nombre de tipo o espacio de nombres 'SerializableAttribute' no existe en la clase o espacio de nombres 'RosettaNet.Schemas.System' (¿falta una referencia de ensamblado?).</span><span class="sxs-lookup"><span data-stu-id="4e33b-205">error CS0234: The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'RosettaNet.Schemas.System' (are you missing an assembly reference?).</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-206">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-206">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-207">Uno de los esquemas, por ejemplo, StandardDocumentHeader.xsd, tiene un [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] espacio de nombres de RosettaNet.Schemas.System.</span><span class="sxs-lookup"><span data-stu-id="4e33b-207">One of your schemas, for example, StandardDocumentHeader.xsd, has a [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] namespace of RosettaNet.Schemas.System.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-208">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-208">Solution</span></span>  
 <span data-ttu-id="4e33b-209">Quitar el "sistema" de la [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] espacio de nombres para el esquema, por lo que el espacio de nombres es RosettaNet.Schemas.</span><span class="sxs-lookup"><span data-stu-id="4e33b-209">Remove the "System" from the [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] namespace for the schema, so that the namespace is RosettaNet.Schemas.</span></span>  
  
## <a name="you-receive-an-error-when-trying-to-manually-deploy-the-bam-package"></a><span data-ttu-id="4e33b-210">Recibe un error al intentar implementar manualmente el paquete de BAM</span><span class="sxs-lookup"><span data-stu-id="4e33b-210">You receive an error when trying to manually deploy the BAM Package</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-211">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-211">Symptom</span></span>  
 <span data-ttu-id="4e33b-212">Cuando manualmente intenta implementar el paquete BAM para [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], recibirá un error que indica que no se puede implementar el paquete.</span><span class="sxs-lookup"><span data-stu-id="4e33b-212">When you manually try to deploy the BAM package for [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], you receive an error indicating that you cannot deploy the package.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-213">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-213">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-214">Los paquetes DTS BAM_DM_Process y BAM_DM_Message están instalados en el sistema, evitar la implementación del paquete BAM.</span><span class="sxs-lookup"><span data-stu-id="4e33b-214">The DTS packages BAM_DM_Process and BAM_DM_Message are installed on your system, preventing deployment of the BAM package.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-215">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-215">Solution</span></span>  
  
##### <a name="to-recover-from-the-error-condition-and-deploy-the-bam-package"></a><span data-ttu-id="4e33b-216">Para recuperarse de la condición de error e implementar el paquete BAM</span><span class="sxs-lookup"><span data-stu-id="4e33b-216">To recover from the error condition and deploy the BAM package</span></span>  
  
1.  <span data-ttu-id="4e33b-217">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server**y, a continuación, haga clic en **Enterprise Manager**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-217">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **Enterprise Manager**.</span></span>  
  
2.  <span data-ttu-id="4e33b-218">En el Administrador corporativo, expanda **servidores Microsoft SQL Server**, **grupo de SQL Server**, **(local) (Windows NT)**, y **Data Transformation Services**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-218">In Enterprise Manager, expand **Microsoft SQL Servers**, **SQL Server Group**, **(local) (Windows NT)**, and **Data Transformation Services**.</span></span>  
  
3.  <span data-ttu-id="4e33b-219">Haga clic en **paquetes locales**, haga clic en **BAM_DM_Message**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-219">Click **Local Packages**, right-click **BAM_DM_Message**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="4e33b-220">Haga clic en **BAM_DM_Process**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-220">Right-click **BAM_DM_Process**, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="4e33b-221">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-221">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="4e33b-222">En el símbolo del sistema, escriba el código siguiente para implementar el archivo de seguimiento y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-222">At the command prompt, type the following code to deploy the tracking file, and then click **OK**.</span></span>  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server <version>\Tracking  
    bm deploy all  "%ProgramFiles%\Microsoft BizTalk <version> Accelerator for RosettaNet\BAMTracking\tracking.xml"  
    ```  
  
## <a name="you-receive-an-error-when-adding-a-new-pip"></a><span data-ttu-id="4e33b-223">Recibe un error al agregar un nuevo PIP</span><span class="sxs-lookup"><span data-stu-id="4e33b-223">You receive an error when adding a new PIP</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-224">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-224">Symptom</span></span>  
 <span data-ttu-id="4e33b-225">Recibe el error siguiente o uno similar en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="4e33b-225">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="4e33b-226">UNP. SCON. VALERR: Se produjo un error al validar el contenido del servicio.</span><span class="sxs-lookup"><span data-stu-id="4e33b-226">UNP.SCON.VALERR: A failure occurred while validating the service content.</span></span>  
  
 <span data-ttu-id="4e33b-227">Detalles: Encontrar la especificación de documento por tipo de mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="4e33b-227">Details: Finding document specification by message type failed.</span></span> <span data-ttu-id="4e33b-228">Compruebe que el esquema se implementa correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e33b-228">Verify that the schema is deployed properly.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-229">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-229">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-230">El espacio de nombres del documento o la propiedad de nodo raíz del esquema implementado para la instancia Pip4A5NotifyofForecastReply es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="4e33b-230">Either the document namespace or the root node property the deployed schema for the instance Pip4A5NotifyofForecastReply is incorrect.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-231">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-231">Solution</span></span>  
 <span data-ttu-id="4e33b-232">Compruebe que el espacio de nombres de documento y la propiedad de nodo raíz para el esquema implementado para la instancia Pip4A5NotifyofForecastReply es correcta.</span><span class="sxs-lookup"><span data-stu-id="4e33b-232">Verify that the document namespace and the root node property for the deployed schema for instance Pip4A5NotifyofForecastReply is correct.</span></span>  
  
## <a name="error-during-the-configuration-of-btarn-at-installation-time-caused-by-presumed-network-connectivity-issues"></a><span data-ttu-id="4e33b-233">Error durante la configuración de BTARN en el momento de la instalación causada por supone que problemas de conectividad de red</span><span class="sxs-lookup"><span data-stu-id="4e33b-233">Error during the configuration of BTARN at installation time, caused by presumed network connectivity issues</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-234">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-234">Symptom</span></span>  
 <span data-ttu-id="4e33b-235">Durante el proceso de configuración, recibirá un error en el cuadro de diálogo de error que indica que el equipo no está conectado correctamente a la red, cuando en realidad es.</span><span class="sxs-lookup"><span data-stu-id="4e33b-235">During the configuration process, you receive an error in the error dialog box indicating that the computer is not properly connected to the network, when in fact it is.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-236">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-236">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-237">Este error puede deberse a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] malinterpreten IP el programa de configuración de direcciones.</span><span class="sxs-lookup"><span data-stu-id="4e33b-237">This error may be caused by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration program misinterpreting IP addresses.</span></span> <span data-ttu-id="4e33b-238">El archivo de hosts en C:\Windows\system32\drivers\etc contiene una entrada que asigna el nombre de host del host local a la dirección IP 127.0.0.1.</span><span class="sxs-lookup"><span data-stu-id="4e33b-238">The hosts file in C:\Windows\system32\drivers\etc contains an entry mapping the localhost host name to the IP address 127.0.0.1.</span></span> <span data-ttu-id="4e33b-239">El programa de configuración puede confundir este valor con la dirección de bucle invertido y se supone que el equipo no está conectado correctamente a la red.</span><span class="sxs-lookup"><span data-stu-id="4e33b-239">The configuration program may confuse this value with the loopback address, and assume that the computer is not connected properly to the network.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-240">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-240">Solution</span></span>  
  
##### <a name="to-avoid-this-error-and-complete-the-configuration-process"></a><span data-ttu-id="4e33b-241">Para evitar este error y completar el proceso de configuración</span><span class="sxs-lookup"><span data-stu-id="4e33b-241">To avoid this error and complete the configuration process</span></span>  
  
1.  <span data-ttu-id="4e33b-242">En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, mover a C:\Windows\system32\drivers\etc y abra el archivo de hosts con el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="4e33b-242">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to C:\Windows\system32\drivers\etc, and open the hosts file using Notepad.</span></span>  
  
2.  <span data-ttu-id="4e33b-243">Convierta en comentario la línea "127.0.0.1 localhost" colocando "#" al principio de la línea.</span><span class="sxs-lookup"><span data-stu-id="4e33b-243">Comment out the line "127.0.0.1        localhost" by placing "# " at the start of the line.</span></span> <span data-ttu-id="4e33b-244">Guarde el archivo de hosts modificada.</span><span class="sxs-lookup"><span data-stu-id="4e33b-244">Save the changed hosts file.</span></span>  
  
3.  <span data-ttu-id="4e33b-245">Haga clic en **vuelva a intentar** en el cuadro de diálogo de error.</span><span class="sxs-lookup"><span data-stu-id="4e33b-245">Click **Retry** in the error dialog box.</span></span>  
  
4.  <span data-ttu-id="4e33b-246">Después de configuración se completó correctamente, vuelva a abrir el archivo de hosts en el Bloc de notas, quite la marca de comentario al principio del host local de asignación de línea y, a continuación, guarde el archivo de hosts.</span><span class="sxs-lookup"><span data-stu-id="4e33b-246">After configuration has completed successfully, re-open the hosts file in Notepad, remove the comment mark at the start of the line mapping localhost, and then save the hosts file.</span></span>  
  
## <a name="you-receive-an-error-regarding-incorrect-signature-length"></a><span data-ttu-id="4e33b-247">Recibirá un error relacionado con la longitud de la firma incorrecta</span><span class="sxs-lookup"><span data-stu-id="4e33b-247">You receive an error regarding incorrect signature length</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-248">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-248">Symptom</span></span>  
 <span data-ttu-id="4e33b-249">Recibe el error siguiente o uno similar en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="4e33b-249">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="4e33b-250">Se produjo un error al ejecutar la canalización de recepción: "Microsoft.Solutions.BTARN.Pipelines.Receive" origen: "Descodificador de MIME/SMIME" ubicación de recepción: "/ BTARNHttpReceive/BTSHTTPReceive.dll?xRNResponseType=async" motivo: longitud de firma incorrecta valor = 1935897193.</span><span class="sxs-lookup"><span data-stu-id="4e33b-250">There was a failure executing the receive pipeline: "Microsoft.Solutions.BTARN.Pipelines.Receive" Source: "MIME/SMIME decoder" Receive Location: "/BTARNHttpReceive/BTSHTTPReceive.dll?xRNResponseType=async" Reason: Incorrect signature length, value = 1935897193.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-251">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-251">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-252">Este mensaje de error indica que la longitud de la firma es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="4e33b-252">This error message indicates that the signature length is incorrect.</span></span> <span data-ttu-id="4e33b-253">Además de la causa de la anterior, este error también podría debido a la longitud del contenido de encabezado incorrecto o incompleto que hace que los bytes incorrectos de lectura en la longitud de la firma.</span><span class="sxs-lookup"><span data-stu-id="4e33b-253">In addition to the above cause, this error could also due to the incorrect or incomplete header content length which leads to the wrong bytes read on the signature length.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-254">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-254">Solution</span></span>  
 <span data-ttu-id="4e33b-255">Compruebe que tanto de la longitud de la firma y la longitud de contenido de encabezado es correcto.</span><span class="sxs-lookup"><span data-stu-id="4e33b-255">Verify that both of the signature length and header content length is correct.</span></span>  
  
## <a name="you-receive-503-service-unavailable-from-internet-explorer-on-64-bit-machine"></a><span data-ttu-id="4e33b-256">Recibirá "503: servicio no disponible" de Internet Explorer en el equipo de 64 bits</span><span class="sxs-lookup"><span data-stu-id="4e33b-256">You receive "503: Service Unavailable" from Internet Explorer on 64-bit machine</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-257">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-257">Symptom</span></span>  
 <span data-ttu-id="4e33b-258">Después de [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] se completa la configuración, cuando se intenta acceder a [http://localhost](http://localhost/) o [http://localhost/BtarnApp/RnifSend.aspx](http://localhost/BtarnApp/RnifSend.aspx), recibirá el error siguiente o uno similar:</span><span class="sxs-lookup"><span data-stu-id="4e33b-258">After [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] configuration is completed, when you try to access [http://localhost](http://localhost/) or [http://localhost/BtarnApp/RnifSend.aspx](http://localhost/BtarnApp/RnifSend.aspx), you may receive the following or similar error:</span></span>  
  
 <span data-ttu-id="4e33b-259">503: servicio no disponible</span><span class="sxs-lookup"><span data-stu-id="4e33b-259">503: Service Unavailable</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-260">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-260">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-261">Este error puede deberse al filtro ISAPI que se encuentran en C:\windows\system32\rpcproxy\rpcproxy.dll que se va a establecer en sitios Web de IIS.</span><span class="sxs-lookup"><span data-stu-id="4e33b-261">This error may be caused by the ISAPI filter found under C:\windows\system32\rpcproxy\rpcproxy.dll being set on IIS Web Sites.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-262">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-262">Solution</span></span>  
  
##### <a name="to-remove-rpcproxy-filter-entry-in-iis"></a><span data-ttu-id="4e33b-263">Para quitar la entrada de filtro de RpcProxy en IIS</span><span class="sxs-lookup"><span data-stu-id="4e33b-263">To remove RpcProxy filter entry in IIS</span></span>  
  
1.  <span data-ttu-id="4e33b-264">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-264">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="4e33b-265">Expanda  **\<nombre_equipo > (equipo local)**, haga clic en **sitios Web**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-265">Expand **\<computer name> (local computer)**, right-click **Web Sites**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="4e33b-266">Seleccione **filtros ISAPI** ficha.</span><span class="sxs-lookup"><span data-stu-id="4e33b-266">Select **ISAPI Filters** tab.</span></span>  
  
4.  <span data-ttu-id="4e33b-267">Seleccione **RpcProxy filtro**y haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-267">Select **RpcProxy filter**, and click **Remove**.</span></span>  
  
5.  <span data-ttu-id="4e33b-268">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-268">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="4e33b-269">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4e33b-269">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="4e33b-270">En el símbolo del sistema, escriba el código siguiente para restablecer IIS.</span><span class="sxs-lookup"><span data-stu-id="4e33b-270">At the command prompt, type the following code to reset IIS.</span></span>  
  
    ```  
    iisreset  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="4e33b-271">Si se intenta tener acceso a http://localhost o http://localhost/BtarnApp/RnifSend.aspx nuevo después de realizar los pasos anteriores, recibirá el mensaje de HTTP 400 desde Internet Explorer, lo que significa que IIS funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e33b-271">If you try to access http://localhost or http://localhost/BtarnApp/RnifSend.aspx again after performing the above steps, you will receive HTTP 400 message back from the Internet Explorer which means that IIS is now functioning properly.</span></span>  
  
## <a name="the-hubscenario-sample-will-not-be-installed-correctly-if-the-assembly-key-files-are-not-entered-for-the-projects"></a><span data-ttu-id="4e33b-272">El ejemplo de HubScenario no se instalará correctamente si no se especifican los archivos de clave de ensamblado para los proyectos</span><span class="sxs-lookup"><span data-stu-id="4e33b-272">The HubScenario sample will not be installed correctly if the assembly key files are not entered for the projects</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-273">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-273">Symptom</span></span>  
 <span data-ttu-id="4e33b-274">Cuando ejecute el archivo setup.bat  *\<unidad >*: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK\HubScenario configurar el ejemplo de HubScenario, el se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="4e33b-274">When you run setup.bat in *\<drive>*:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\HubScenario to set up the HubScenario sample, the operation fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-275">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-275">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-276">Los ensamblados HubScenario y HubHelper no se implementaron correctamente porque los archivos de clave de ensamblado no se establecieron en los proyectos.</span><span class="sxs-lookup"><span data-stu-id="4e33b-276">The HubScenario and HubHelper assemblies were not deployed correctly because the assembly key files were not set in the projects.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-277">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-277">Solution</span></span>  
 <span data-ttu-id="4e33b-278">Establece los archivos de clave de ensamblado para los proyectos HubScenario y HubHelper.</span><span class="sxs-lookup"><span data-stu-id="4e33b-278">Set the assembly key files for the HubScenario and HubHelper projects.</span></span> <span data-ttu-id="4e33b-279">Para obtener más información, consulte [ejemplo de HubScenario](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md).</span><span class="sxs-lookup"><span data-stu-id="4e33b-279">For more information, see [HubScenario Sample](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md).</span></span>  
  
## <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample-on-sql-server-2008-r22008-sp1"></a><span data-ttu-id="4e33b-280">Ejecutar setupx64.bat para configurar el ejemplo de orquestación de PIPAutomation de doble acción en SQL Server 2008 R2 o 2008 SP1</span><span class="sxs-lookup"><span data-stu-id="4e33b-280">Run setupx64.bat to set up the Double Action PIPAutomation Orchestration sample on SQL Server 2008 R2/2008 SP1</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4e33b-281">Síntoma</span><span class="sxs-lookup"><span data-stu-id="4e33b-281">Symptom</span></span>  
 <span data-ttu-id="4e33b-282">Cuando ejecute setup.bat para crear e inicializar el ejemplo de orquestación de PIPAutomation de doble acción, procedimiento el PipAutomationGetAction almacenado en el BTARNData no se crea la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4e33b-282">When you run setup.bat to build and initialize the Double Action PIPAutomation Orchestration sample, the PipAutomationGetAction stored procedure in the BTARNData database is not created.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4e33b-283">Causa posible</span><span class="sxs-lookup"><span data-stu-id="4e33b-283">Possible Cause</span></span>  
 <span data-ttu-id="4e33b-284">La ejecución de setup.bat en un equipo de 64 bits o en un [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] instalación que se ejecuta en SQL Server 2008 R2 o 2008 SP1.</span><span class="sxs-lookup"><span data-stu-id="4e33b-284">You ran setup.bat on a 64-bit computer or on a [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] installation that is running on SQL Server 2008 R2/2008 SP1.</span></span> <span data-ttu-id="4e33b-285">Ambas instancias deberá ejecutar setupx64.bat.</span><span class="sxs-lookup"><span data-stu-id="4e33b-285">Both of these instances require you to run setupx64.bat.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4e33b-286">Solución</span><span class="sxs-lookup"><span data-stu-id="4e33b-286">Solution</span></span>  
 <span data-ttu-id="4e33b-287">Ejecutar setupx64.bat para crear el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="4e33b-287">Run setupx64.bat to create the stored procedure.</span></span> <span data-ttu-id="4e33b-288">Para obtener más información, consulte [orquestación de PIPAutomation de doble acción](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="4e33b-288">For more information, see [Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md).</span></span>  
  
## <a name="enable-the-btarn-application-pools-for-32-bit-on-windows-server-2008-64-bit-windows-operating-system-os"></a><span data-ttu-id="4e33b-289">Habilitar los grupos de aplicaciones de BTARN de 32 bits en Windows Server 2008, sistema operativo de Windows de 64 bits (SO)</span><span class="sxs-lookup"><span data-stu-id="4e33b-289">Enable the BTARN Application Pools for 32 bit on Windows Server 2008, 64-bit Windows Operating System (OS)</span></span>  
 <span data-ttu-id="4e33b-290">Para ejecutar el escenario de extremo a extremo BTARN en Windows Server 2008,64 bits Windows sistema operativo (SO), Internet Information Services Manager 7.5 o 7.0.</span><span class="sxs-lookup"><span data-stu-id="4e33b-290">To run the BTARN End to End scenario on Windows Server 2008,64-bit Windows Operating System (OS), Internet Information Services Manager 7.5/7.0.</span></span>  
  
 1. <span data-ttu-id="4e33b-291">Habilitar los grupos de aplicaciones de BTARN de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="4e33b-291">Enable the BTARN Application Pools for 32 bit.</span></span>  
  
 2. <span data-ttu-id="4e33b-292">Agregue un controlador HTTP para referencia *.dll los filtros IsapiModule.</span><span class="sxs-lookup"><span data-stu-id="4e33b-292">Add a HTTP Handler for *.dll refering the IsapiModule Filters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e33b-293">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e33b-293">See Also</span></span>  
 <span data-ttu-id="4e33b-294">[BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md) </span><span class="sxs-lookup"><span data-stu-id="4e33b-294">[BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md) </span></span>  
 [<span data-ttu-id="4e33b-295">Bucle invertido</span><span class="sxs-lookup"><span data-stu-id="4e33b-295">Loopback</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)