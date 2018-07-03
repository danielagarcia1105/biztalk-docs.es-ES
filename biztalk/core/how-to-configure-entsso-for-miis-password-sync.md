---
title: Cómo configurar ENTSSO para la sincronización de contraseñas MIIS | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89438935-37c1-4ac9-9ca2-7af8d9bfd3ae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9aed37b5b3883242005f46dcc6a0253a4971d680
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005229"
---
# <a name="how-to-configure-entsso-for-miis-password-sync"></a><span data-ttu-id="21ad2-102">Cómo configurar ENTSSO para la sincronización de contraseñas de MIIS</span><span class="sxs-lookup"><span data-stu-id="21ad2-102">How to Configure ENTSSO for MIIS Password Sync</span></span>
<span data-ttu-id="21ad2-103">Después de configurar el archivo XML y Microsoft Identity Integration Server (MIIS), el resto de los pasos de configuración deben llevarse a cabo en el sistema de Inicio de sesión único empresarial (ENTSSO).</span><span class="sxs-lookup"><span data-stu-id="21ad2-103">After configuring the XML file and Microsoft Identity Integration Server (MIIS), the remaining configuration steps take place in the Enterprise Single Sign-On (ENTSSO) system.</span></span>  
  
### <a name="to-allow-password-sync-from-miis"></a><span data-ttu-id="21ad2-104">Para permitir la sincronización de contraseñas desde MIIS</span><span class="sxs-lookup"><span data-stu-id="21ad2-104">To allow Password Sync from MIIS</span></span>  
  
1.  <span data-ttu-id="21ad2-105">En Enterprise Single Sign-On, haga clic en el **servidores** nodo.</span><span class="sxs-lookup"><span data-stu-id="21ad2-105">In Enterprise Single Sign-On, click the **Servers** node.</span></span>  
  
2.  <span data-ttu-id="21ad2-106">Haga clic en el servidor adecuado y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-106">Right-click the appropriate server, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="21ad2-107">Haga clic en el **la sincronización de contraseñas** ficha.</span><span class="sxs-lookup"><span data-stu-id="21ad2-107">Click the **Password Sync** tab.</span></span>  
  
4.  <span data-ttu-id="21ad2-108">Seleccione **Permitir sincronización de contraseñas desde MIIS**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-108">Select **Allow password sync from MIIS**.</span></span>  
  
5.  <span data-ttu-id="21ad2-109">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-109">Click **OK**.</span></span>  
  
### <a name="to-enable-password-sync-on-the-system-level"></a><span data-ttu-id="21ad2-110">Para habilitar la sincronización de contraseñas en el sistema</span><span class="sxs-lookup"><span data-stu-id="21ad2-110">To enable Password Sync on the system level</span></span>  
  
1. <span data-ttu-id="21ad2-111">En Enterprise Single Sign-On, haga clic en el **sistema** nodo.</span><span class="sxs-lookup"><span data-stu-id="21ad2-111">In Enterprise Single Sign-On, right-click the **System** node.</span></span>  
  
2. <span data-ttu-id="21ad2-112">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-112">Click **Properties**.</span></span>  
  
    <span data-ttu-id="21ad2-113">El **propiedades** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="21ad2-113">The **Properties** dialog box appears.</span></span>  
  
3. <span data-ttu-id="21ad2-114">Haga clic en el **opciones** ficha.</span><span class="sxs-lookup"><span data-stu-id="21ad2-114">Click the **Options** tab.</span></span>  
  
4. <span data-ttu-id="21ad2-115">En el **Habilitar sincronización de contraseñas** campos, seleccione **desde Windows a los adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-115">In the **Enable Password Sync** field, select **From Windows to Adapters**.</span></span>  
  
    <span data-ttu-id="21ad2-116">**Configuración adicional**</span><span class="sxs-lookup"><span data-stu-id="21ad2-116">**Additional Configuration**</span></span>  
  
    <span data-ttu-id="21ad2-117">Por último, debe configurar uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="21ad2-117">Finally, you must configure one of the following:</span></span>  
  
   - <span data-ttu-id="21ad2-118">Un Adaptador de sincronización de contraseñas que acepte la Sincronización de contraseñas de Windows.</span><span class="sxs-lookup"><span data-stu-id="21ad2-118">A Password Sync Adapter that accepts Windows Password Sync.</span></span>  
  
   - <span data-ttu-id="21ad2-119">La Sincronización directa de contraseñas debe estar habilitada en al menos una aplicación.</span><span class="sxs-lookup"><span data-stu-id="21ad2-119">Direct Password Sync enabled on at least one application.</span></span>  
  
     <span data-ttu-id="21ad2-120">Para obtener más información sobre cómo llevar a cabo este procedimiento, consulte la documentación de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="21ad2-120">For information about how to do this, refer to your Password Sync documentation.</span></span>  
  
### <a name="to-configure-the-entsso-ma-for-miis-password-sync"></a><span data-ttu-id="21ad2-121">Para configurar ENTSSO MA para la sincronización de contraseñas de MIIS</span><span class="sxs-lookup"><span data-stu-id="21ad2-121">To configure the EntSSO MA for MIIS Password Sync</span></span>  
  
1.  <span data-ttu-id="21ad2-122">En el agente de administración de ENTSSO **propiedades** página, haga clic en **configurar extensiones**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-122">On the ENTSSO Management Agent **Properties** page, click **Configure Extensions**.</span></span>  
  
2.  <span data-ttu-id="21ad2-123">En el **información de conexión para la extensión de contraseña** , a continuación, haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-123">In the **Connection information for password extension** field, click **Settings**.</span></span>  
  
3.  <span data-ttu-id="21ad2-124">En el **Connect To** campo escriba el nombre del equipo que va a recibir los cambios de contraseña.</span><span class="sxs-lookup"><span data-stu-id="21ad2-124">In the **Connect To** field enter the name of the computer that will receive the password changes.</span></span>  
  
     <span data-ttu-id="21ad2-125">El nombre del equipo debe tener el mismo formato que el que se utilizó en la creación del Nombre principal del servicio (SPN) del servicio ENTSSO del dominio.</span><span class="sxs-lookup"><span data-stu-id="21ad2-125">The computer name must be in the same format that was used when creating the Service Principal Name (SPN) for the ENTSSO service on the domain.</span></span>  
  
     <span data-ttu-id="21ad2-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="21ad2-126">For example:</span></span>  
  
     <span data-ttu-id="21ad2-127">Formato corto - SPN = ENTSSO/ABCD1411, escriba ABCD1411</span><span class="sxs-lookup"><span data-stu-id="21ad2-127">Short format - SPN = ENTSSO/ABCD1411, then enter ABCD1411</span></span>  
  
4.  <span data-ttu-id="21ad2-128">Formato largo - SPN = ENTSSO/ABCD1411.CompanyName.com, escriba ABCD1411.CompanyName.com</span><span class="sxs-lookup"><span data-stu-id="21ad2-128">Long format - SPN = ENTSSO/ABCD1411.CompanyName.com then enter ABCD1411.CompanyName.com</span></span>  
  
### <a name="additional-configuration-steps"></a><span data-ttu-id="21ad2-129">Pasos de configuración adicional</span><span class="sxs-lookup"><span data-stu-id="21ad2-129">Additional Configuration Steps</span></span>  
  
1.  <span data-ttu-id="21ad2-130">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft Identity Integration Server**y, a continuación, haga clic en **Identity Manager**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-130">Click **Start**, point to **All Programs**, point to **Microsoft Identity Integration Server**, and then click **Identity Manager**.</span></span>  
  
2.  <span data-ttu-id="21ad2-131">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-131">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="21ad2-132">Seleccione **habilitar la sincronización de contraseña**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-132">Select **Enable Password Synchronization**.</span></span>  
  
4.  <span data-ttu-id="21ad2-133">En el **Ver agentes de administración**, seleccione **ADMA**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-133">In the **Management Agents view**, select **ADMA**.</span></span>  
  
5.  <span data-ttu-id="21ad2-134">En el **acción** panel, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-134">In the **Action** pane, select **Properties**.</span></span>  
  
6.  <span data-ttu-id="21ad2-135">En el **propiedades** página, seleccione **configurar particiones de directorio**y, a continuación, seleccione **habilitar esta partición como un origen de sincronización de contraseña**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-135">On the **Properties** page, select **Configure Directory Partitions**, and then select **Enable this partition as a password synchronization source**.</span></span>  
  
7.  <span data-ttu-id="21ad2-136">Haga clic en **destinos**y, a continuación, seleccione ENTSSOMA2 para que pueda recibir cambios de contraseñas desde MIIS.</span><span class="sxs-lookup"><span data-stu-id="21ad2-136">Click **Targets**, and then select ENTSSOMA2 to enable it to receive password changes from MIIS.</span></span> <span data-ttu-id="21ad2-137">Anule la selección de ENTSSOMA.</span><span class="sxs-lookup"><span data-stu-id="21ad2-137">Deselect ENTSSOMA.</span></span> <span data-ttu-id="21ad2-138">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="21ad2-138">Click **OK**, and then click **OK** again.</span></span>  
  
8.  <span data-ttu-id="21ad2-139">En el **Management Agent** visualizarla, seleccione **ENTSSOMA2**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-139">In the **Management Agent** view, select **ENTSSOMA2**.</span></span> <span data-ttu-id="21ad2-140">En el panel derecho, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-140">In the right-hand pane, select **Properties**.</span></span> <span data-ttu-id="21ad2-141">En el **propiedades** página, haga clic en **configurar extensiones**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-141">On the **Properties** page, click **Configure Extensions**.</span></span>  
  
9. <span data-ttu-id="21ad2-142">Confirme que **habilitar la administración de contraseñas** está seleccionada y, a continuación, haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-142">Confirm that **Enable password management** is selected, and then click **Settings**.</span></span>  
  
10. <span data-ttu-id="21ad2-143">En el **configuración de conexión** cuadro de diálogo, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="21ad2-143">In the **Connection Settings** dialog, specify the following:</span></span>  
  
    -   <span data-ttu-id="21ad2-144">Conectarse a: INTSVR1.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="21ad2-144">Connect To: INTSVR1.fabrikam.com</span></span>  
  
    -   <span data-ttu-id="21ad2-145">Usuario: fabrikam\ssosvcact</span><span class="sxs-lookup"><span data-stu-id="21ad2-145">User: fabrikam\ssosvcact</span></span>  
  
    -   <span data-ttu-id="21ad2-146">Contraseña: ssosvcact</span><span class="sxs-lookup"><span data-stu-id="21ad2-146">Password: ssosvcact</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="21ad2-147">Los datos de esta cuenta deben coincidir con la cuenta del servicio ENTSSO configurada en INTSVR1.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="21ad2-147">This account should match the ENTSSO service account configured on INTSVR1.fabrikam.com.</span></span>  
  
11. <span data-ttu-id="21ad2-148">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="21ad2-148">Click **OK**, and then click **OK** again.</span></span>  
  
12. <span data-ttu-id="21ad2-149">También se puede deshabilitar la sincronización de contraseñas para MIIS.</span><span class="sxs-lookup"><span data-stu-id="21ad2-149">You can also disable password sync for MIIS.</span></span> <span data-ttu-id="21ad2-150">Para ello, en **Identity Manager**, haga clic en el **herramientas** menú, haga clic en **opciones**y, a continuación, anule la selección **Enable Password Synchronization**.</span><span class="sxs-lookup"><span data-stu-id="21ad2-150">To do this, in **Identity Manager**, click the **Tools** menu, click **Options**, and then deselect **Enable Password Synchronization**.</span></span>  
  
     <span data-ttu-id="21ad2-151">Sin embargo, se aplicarán las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="21ad2-151">The following restrictions will apply:</span></span>  
  
    -   <span data-ttu-id="21ad2-152">Para que la sincronización de contraseñas funcione correctamente, el SPN debe configurarse en la cuenta de servicio de ENTSSO con la que el agente de administración de ENTSSO se vaya a comunicar.</span><span class="sxs-lookup"><span data-stu-id="21ad2-152">For Password Sync to function properly, SPN must be configured on the ENTSSO service account that the ENTSSO Management Agent will communicate with.</span></span>  
  
    -   <span data-ttu-id="21ad2-153">La comunicación entre MIIS y el servidor de ENTSSO requiere Kerberos.</span><span class="sxs-lookup"><span data-stu-id="21ad2-153">Communication between MIIS and the ENTSSO server requires Kerberos.</span></span>  
  
13. <span data-ttu-id="21ad2-154">Cuando configure la extensión de contraseña en la configuración de la conexión de MIIS para el agente de administración de ENTSSO, la cuenta especificada deberá coinicidir con la cuenta de servicio del servidor de ENTSSO que reciba las contraseñas de MIIS.</span><span class="sxs-lookup"><span data-stu-id="21ad2-154">When configuring Password Extension in the MIIS connection configuration for the ENTSSO Management Agent, the account specified must match the service account for the ENTSSO server that will receive passwords from MIIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ad2-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="21ad2-155">See Also</span></span>  
 [<span data-ttu-id="21ad2-156">Cómo usar al agente de administración de ENTSSO</span><span class="sxs-lookup"><span data-stu-id="21ad2-156">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)