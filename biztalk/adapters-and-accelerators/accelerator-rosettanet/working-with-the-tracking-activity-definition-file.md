---
title: Trabajar con el archivo de definición de actividad de seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking, activity definition file
- activity definition file
- activity definition file, about activity definition file
- tracking, managing views
- activity definition file, activity fields
ms.assetid: 0592a844-aad7-4054-b1e7-344f1086f0b1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0be795daa7e08707c113d8230dc8d324bc71f951
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991917"
---
# <a name="working-with-the-tracking-activity-definition-file"></a><span data-ttu-id="ecf29-102">Trabajar con el archivo de definición de actividad de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ecf29-102">Working with the Tracking Activity Definition File</span></span>
<span data-ttu-id="ecf29-103">El archivo de definición de actividad contiene información sobre el seguimiento de las actividades de proceso y el mensaje en Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecf29-103">The activity definition file contains information about the tracking process and message activities in Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ecf29-104"> Este archivo se usa para administrar los datos de seguimiento de BizTalk actividad de supervisión económica (BAM).</span><span class="sxs-lookup"><span data-stu-id="ecf29-104"> uses this file to manage data tracking in BizTalk Business Activity Monitoring (BAM).</span></span> <span data-ttu-id="ecf29-105">El archivo de definición es un archivo XML (Tracking.xml) que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala en el \< *unidad*\>: \Program Files\Microsoft Acelerador de BizTalk 2013 para RosettaNet \BAMTracking carpeta.</span><span class="sxs-lookup"><span data-stu-id="ecf29-105">The definition file is an XML file (Tracking.xml) that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] setup installs in the \<*drive*\>:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAMTracking folder.</span></span> <span data-ttu-id="ecf29-106">Las actividades definidas en Tracking.xml pueden ser suficientes para sus fines.</span><span class="sxs-lookup"><span data-stu-id="ecf29-106">The activities defined in Tracking.xml may be sufficient for your purposes.</span></span>  
  
 <span data-ttu-id="ecf29-107">Para obtener más información sobre el seguimiento de actividades, vistas y tablas, consulte [mejorada de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md).</span><span class="sxs-lookup"><span data-stu-id="ecf29-107">For more information about the tracking activities, views, and tables, see [Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md).</span></span> <span data-ttu-id="ecf29-108">Para obtener más información acerca de SAE, vea "actividad de supervisión económica (BAM)" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ecf29-108">For more information about BAM, see "Business Activity Monitoring (BAM)" in BizTalk Server Help.</span></span>  
  
## <a name="managing-tracking-views"></a><span data-ttu-id="ecf29-109">Administrar vistas de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ecf29-109">Managing Tracking Views</span></span>  
 <span data-ttu-id="ecf29-110">No utilice el Editor de perfiles de seguimiento de BizTalk con [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ecf29-110">You do not use the BizTalk Tracking Profile Editor with [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] tracking.</span></span> <span data-ttu-id="ecf29-111">Los puntos de seguimiento no son personalizables; No cambie las definiciones de actividad.</span><span class="sxs-lookup"><span data-stu-id="ecf29-111">The tracking points are not customizable; do not change activity definitions.</span></span> <span data-ttu-id="ecf29-112">Sin embargo, puede administrar la implementación y las vistas BAM.</span><span class="sxs-lookup"><span data-stu-id="ecf29-112">However, you can manage BAM views and deployment.</span></span> <span data-ttu-id="ecf29-113">Para ello, modifica un [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] (Tracking.xls) de la hoja de cálculo que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala en el \< *unidad*\>: \Program Files\Microsoft BizTalk 2013 Accelerator for menú Carpeta BAMTracking.</span><span class="sxs-lookup"><span data-stu-id="ecf29-113">To do so, you modify an [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet (Tracking.xls) that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] setup installs in the \<*drive*\>:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking folder.</span></span> <span data-ttu-id="ecf29-114">Para obtener más información, consulte "Administración de seguimiento vistas" a continuación.</span><span class="sxs-lookup"><span data-stu-id="ecf29-114">For more information, see "Managing Tracking Views" below.</span></span>  
  
 <span data-ttu-id="ecf29-115">Si las vistas definidas en Tracking.xml no son suficientes para satisfacer sus necesidades, puede definir vistas diferentes de la información de seguimiento en BAM, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="ecf29-115">If the views defined in Tracking.xml are not sufficient for your needs, you can define different views of the information tracked in BAM as follows.</span></span>  
  
#### <a name="to-create-different-tracking-views"></a><span data-ttu-id="ecf29-116">Para crear vistas de seguimiento diferente</span><span class="sxs-lookup"><span data-stu-id="ecf29-116">To create different tracking views</span></span>  
  
1. <span data-ttu-id="ecf29-117">Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ecf29-117">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="ecf29-118">Escriba **cmd** en el cuadro de texto Abrir del cuadro de diálogo Ejecutar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ecf29-118">Enter **cmd** in the Open text box of the Run dialog box, and then click **OK**.</span></span> <span data-ttu-id="ecf29-119">En el cuadro de diálogo de línea de comandos, escriba el código siguiente para anular la implementación de tracking.xml, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="ecf29-119">In the command line dialog box, enter the following code to undeploy tracking.xml, then click **OK**:</span></span>  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm remove-all  -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
2. <span data-ttu-id="ecf29-120">En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, desplácese a  *\<unidad\>*: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAM de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ecf29-120">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to *\<drive\>*:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAM Tracking.</span></span> <span data-ttu-id="ecf29-121">Haga doble clic en Tracking.xls.</span><span class="sxs-lookup"><span data-stu-id="ecf29-121">Double-click Tracking.xls.</span></span>  
  
3. <span data-ttu-id="ecf29-122">Crear una nueva vista en la actividad económica.</span><span class="sxs-lookup"><span data-stu-id="ecf29-122">Create a new view in Business Activity Monitoring.</span></span> <span data-ttu-id="ecf29-123">Para obtener información acerca de cómo hacerlo, consulte "Administración de la actividad económica" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ecf29-123">For information about how to do so, see "Managing Business Activity Monitoring" in BizTalk Server Help.</span></span>  
  
4. <span data-ttu-id="ecf29-124">Haga clic en **BAM**y, a continuación, haga clic en **exportar XML**.</span><span class="sxs-lookup"><span data-stu-id="ecf29-124">Click **BAM**, and then click **Export XML**.</span></span> <span data-ttu-id="ecf29-125">Mover a la ubicación deseada, escriba un nombre de archivo (que no sea Tracking.xml) y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="ecf29-125">Move to the desired location, enter a file name (other than Tracking.xml), and then click **Save**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="ecf29-126">Al definir nuevas vistas de seguimiento en un archivo XLS de seguimiento y exportar un archivo XML desde el archivo XLS de seguimiento, algunos de los nuevos nombres de campo pueden modificarse ligeramente.</span><span class="sxs-lookup"><span data-stu-id="ecf29-126">When you define new tracking views in a tracking XLS file, and export an XML file from the tracking XLS file, some of the new field names may be slightly modified.</span></span> <span data-ttu-id="ecf29-127">Corregir este problema mediante la comprobación de los campos en su personalizados de seguimiento de archivos XML en el campo tracking.xml estándar instalado el programa de instalación de BTARN.</span><span class="sxs-lookup"><span data-stu-id="ecf29-127">Correct this by verifying the fields in your customized tracking XML file against the standard tracking.xml field installed by BTARN setup.</span></span>  
  
5. <span data-ttu-id="ecf29-128">Implementar el nuevo archivo XML de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ecf29-128">Deploy the new tracking XML file.</span></span> <span data-ttu-id="ecf29-129">Para ello, haga clic en **iniciar**y, a continuación, haga clic en **ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ecf29-129">To do so, click **Start**, and then click **Run**.</span></span> <span data-ttu-id="ecf29-130">Escriba **cmd** en el cuadro de texto Abrir del cuadro de diálogo Ejecutar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ecf29-130">Enter **cmd** in the Open text box of the Run dialog box, and then click **OK**.</span></span> <span data-ttu-id="ecf29-131">En el cuadro de diálogo de línea de comandos, escriba el código siguiente para implementar el nuevo archivo de seguimiento, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ecf29-131">In the command line dialog box, enter the following code to deploy your new tracking file, then click **OK**.</span></span> <span data-ttu-id="ecf29-132">Se recomienda cambiar el nombre del archivo XML de seguimiento para que no sobrescriba el archivo de tracking.xml predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ecf29-132">It is recommended that you rename the tracking XML file so that you do not overwrite the default tracking.xml file.</span></span>  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm.exe deploy-all -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2030 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
   <span data-ttu-id="ecf29-133">La información de seguimiento en BAM no incluye el contenido del mensaje, ya que se almacena en un [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="ecf29-133">The information tracked in BAM does not include the message content, because that is stored in a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] database.</span></span>  
  
   <span data-ttu-id="ecf29-134">Puede administrar la implementación de seguimiento mediante el uso de la empresa actividad supervisión de utilidad de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="ecf29-134">You can manage deployment of BAM tracking by using the Business Activity Monitoring Management Utility.</span></span> <span data-ttu-id="ecf29-135">Para obtener más información acerca de esta utilidad, vea "Utilizando el negocio actividad supervisión de utilidad de administración" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ecf29-135">For more information about this utility, see "Using the Business Activity Monitoring Management Utility" in BizTalk Server Help.</span></span>  
  
## <a name="activity-fields"></a><span data-ttu-id="ecf29-136">Campos de actividad</span><span class="sxs-lookup"><span data-stu-id="ecf29-136">Activity Fields</span></span>  
 <span data-ttu-id="ecf29-137">Los campos de la actividad de mensaje en el archivo de definición de actividad son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ecf29-137">The fields of the message activity in the activity definition file are the following:</span></span>  
  
- <span data-ttu-id="ecf29-138">ActivityName</span><span class="sxs-lookup"><span data-stu-id="ecf29-138">ActivityName</span></span>  
  
- <span data-ttu-id="ecf29-139">Categoría</span><span class="sxs-lookup"><span data-stu-id="ecf29-139">Category</span></span>  
  
- <span data-ttu-id="ecf29-140">ContentKey</span><span class="sxs-lookup"><span data-stu-id="ecf29-140">ContentKey</span></span>  
  
- <span data-ttu-id="ecf29-141">DestinationPartyName</span><span class="sxs-lookup"><span data-stu-id="ecf29-141">DestinationPartyName</span></span>  
  
- <span data-ttu-id="ecf29-142">ErrorDescription</span><span class="sxs-lookup"><span data-stu-id="ecf29-142">ErrorDescription</span></span>  
  
- <span data-ttu-id="ecf29-143">HasError</span><span class="sxs-lookup"><span data-stu-id="ecf29-143">HasError</span></span>  
  
- <span data-ttu-id="ecf29-144">InReplyToMessageID</span><span class="sxs-lookup"><span data-stu-id="ecf29-144">InReplyToMessageID</span></span>  
  
- <span data-ttu-id="ecf29-145">IsReceived</span><span class="sxs-lookup"><span data-stu-id="ecf29-145">IsReceived</span></span>  
  
- <span data-ttu-id="ecf29-146">MessageTrackingID</span><span class="sxs-lookup"><span data-stu-id="ecf29-146">MessageTrackingID</span></span>  
  
- <span data-ttu-id="ecf29-147">NoFPipInstance</span><span class="sxs-lookup"><span data-stu-id="ecf29-147">NoFPipInstance</span></span>  
  
- <span data-ttu-id="ecf29-148">PipCode</span><span class="sxs-lookup"><span data-stu-id="ecf29-148">PipCode</span></span>  
  
- <span data-ttu-id="ecf29-149">PipInstanceID</span><span class="sxs-lookup"><span data-stu-id="ecf29-149">PipInstanceID</span></span>  
  
- <span data-ttu-id="ecf29-150">PiPVersion</span><span class="sxs-lookup"><span data-stu-id="ecf29-150">PiPVersion</span></span>  
  
- <span data-ttu-id="ecf29-151">SourcePartName</span><span class="sxs-lookup"><span data-stu-id="ecf29-151">SourcePartName</span></span>  
  
- <span data-ttu-id="ecf29-152">Timestamp</span><span class="sxs-lookup"><span data-stu-id="ecf29-152">Timestamp</span></span>  
  
  <span data-ttu-id="ecf29-153">Los campos de la actividad del proceso en el archivo de definición de actividad son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ecf29-153">The fields of the process activity in the activity definition file are the following:</span></span>  
  
- <span data-ttu-id="ecf29-154">EndTime</span><span class="sxs-lookup"><span data-stu-id="ecf29-154">EndTime</span></span>  
  
- <span data-ttu-id="ecf29-155">InitiatorPartyName</span><span class="sxs-lookup"><span data-stu-id="ecf29-155">InitiatorPartyName</span></span>  
  
- <span data-ttu-id="ecf29-156">IsInitiatorRole</span><span class="sxs-lookup"><span data-stu-id="ecf29-156">IsInitiatorRole</span></span>  
  
- <span data-ttu-id="ecf29-157">PipCode</span><span class="sxs-lookup"><span data-stu-id="ecf29-157">PipCode</span></span>  
  
- <span data-ttu-id="ecf29-158">PipInstanceID</span><span class="sxs-lookup"><span data-stu-id="ecf29-158">PipInstanceID</span></span>  
  
- <span data-ttu-id="ecf29-159">PipName</span><span class="sxs-lookup"><span data-stu-id="ecf29-159">PipName</span></span>  
  
- <span data-ttu-id="ecf29-160">PipVersion</span><span class="sxs-lookup"><span data-stu-id="ecf29-160">PipVersion</span></span>  
  
- <span data-ttu-id="ecf29-161">ResponderPartyName</span><span class="sxs-lookup"><span data-stu-id="ecf29-161">ResponderPartyName</span></span>  
  
- <span data-ttu-id="ecf29-162">StartTime</span><span class="sxs-lookup"><span data-stu-id="ecf29-162">StartTime</span></span>  
  
- <span data-ttu-id="ecf29-163">Estado</span><span class="sxs-lookup"><span data-stu-id="ecf29-163">Status</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf29-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecf29-164">See Also</span></span>  
 <span data-ttu-id="ecf29-165">[Seguimiento mejorado](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="ecf29-165">[Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span></span>  
 [<span data-ttu-id="ecf29-166">Administrar la configuración, certificados, bases de datos y seguridad</span><span class="sxs-lookup"><span data-stu-id="ecf29-166">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)