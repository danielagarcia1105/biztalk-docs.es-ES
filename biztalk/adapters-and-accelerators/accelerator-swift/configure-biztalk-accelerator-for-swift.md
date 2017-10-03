---
title: Configurar el Acelerador de BizTalk para SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e34b0b2d-f563-468b-b6b9-536f0df96f52
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaa9812243ef7d5ff4bb8b902ac7aee48e54ab99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-biztalk-accelerator-for-swift"></a><span data-ttu-id="e4e10-102">Configurar el Acelerador de BizTalk para SWIFT</span><span class="sxs-lookup"><span data-stu-id="e4e10-102">Configure BizTalk Accelerator for SWIFT</span></span>

<span data-ttu-id="e4e10-103">Configurar la [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4e10-103">Configure the [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)].</span></span> 

<span data-ttu-id="e4e10-104">Al instalar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)], hay una casilla que permite ejecutar la configuración automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e4e10-104">When you install [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)], there is a checkbox that lets you run the configuration automatically.</span></span> <span data-ttu-id="e4e10-105">O bien, puede abrir la configuración BizTalk Accelerator for SWIFT (A4SWIFT) aparece en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e4e10-105">Or, you can open the BizTalk Accelerator for SWIFT (A4SWIFT) Configuration listed in your apps.</span></span>

<span data-ttu-id="e4e10-106">En este tema se muestra cómo configurar el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] acelerador, cómo exportar o importar una configuración y también se enumeran los pasos posteriores a la configuración.</span><span class="sxs-lookup"><span data-stu-id="e4e10-106">This topic shows you how to configure the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] accelerator, how to export or import a configuration, and also lists the post-configuration steps.</span></span>

## <a name="configure-a4swift"></a><span data-ttu-id="e4e10-107">Configurar A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="e4e10-107">Configure A4SWIFT</span></span>

1. <span data-ttu-id="e4e10-108">Abra el Acelerador de BizTalk para SWIFT (A4SWIFT) configuración.</span><span class="sxs-lookup"><span data-stu-id="e4e10-108">Open the BizTalk Accelerator for SWIFT (A4SWIFT) Configuration.</span></span>
2. <span data-ttu-id="e4e10-109">Seleccione **MCRR**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-109">Select **MCRR**.</span></span> <span data-ttu-id="e4e10-110">MCRR solo está disponible si ha instalado el **reparación de mensajes y nuevo envío** componentes.</span><span class="sxs-lookup"><span data-stu-id="e4e10-110">MCRR is available only if you installed the **Message Repair and New Submission** components.</span></span>
3. <span data-ttu-id="e4e10-111">Cuando se le pregunte **¿desea crear un nuevo grupo de base de datos**:</span><span class="sxs-lookup"><span data-stu-id="e4e10-111">When asked **Do you want to create a new database group**:</span></span>

  * <span data-ttu-id="e4e10-112">Seleccione esta opción para crear los nuevos grupos que se muestra en el **grupo** panel.</span><span class="sxs-lookup"><span data-stu-id="e4e10-112">Select this option to create the new groups shown in the **Group** pane.</span></span> 
  * <span data-ttu-id="e4e10-113">Para unirse a un grupo de base de datos existente, desactive esta opción.</span><span class="sxs-lookup"><span data-stu-id="e4e10-113">To join an existing database group, uncheck this option.</span></span>

3. <span data-ttu-id="e4e10-114">Si instaló **componentes Web de reparación de mensajes y nuevo envío**, a continuación, seleccione **WebService**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-114">If you installed **Web Components for Message Repair and New Submission**, then select **WebService**.</span></span>
4. <span data-ttu-id="e4e10-115">Seleccione el sitio web para hospedar el servicio Web de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="e4e10-115">Select the web site to host the A4SWIFT Web service.</span></span> <span data-ttu-id="e4e10-116">De forma predeterminada, se selecciona el sitio Web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e4e10-116">By default, the Default Web Site is selected.</span></span>
5. <span data-ttu-id="e4e10-117">Seleccione **aplicar configuración**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-117">Select **Apply Configuration**.</span></span>
6. <span data-ttu-id="e4e10-118">En **resumen**, compruebe los valores de configuración y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-118">In **Summary**, verify the configuration settings, and then click **Configure**.</span></span> 

    > [!TIP] 
    > <span data-ttu-id="e4e10-119">Puede guardar los ajustes de configuración como archivo XML, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="e4e10-119">You can save the configuration settings as an XML file, if desired.</span></span>

7. <span data-ttu-id="e4e10-120">Seleccione **finalizar** cuando se completa la configuración.</span><span class="sxs-lookup"><span data-stu-id="e4e10-120">Select **Finish** when the configuration completes.</span></span>

## <a name="export-or-import-a-configuration"></a><span data-ttu-id="e4e10-121">Exportar o importar una configuración</span><span class="sxs-lookup"><span data-stu-id="e4e10-121">Export or import a configuration</span></span>
<span data-ttu-id="e4e10-122">Puede exportar la configuración de A4SWIFT en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="e4e10-122">You can export the configuration settings of A4SWIFT to an XML file.</span></span> <span data-ttu-id="e4e10-123">A continuación, se puede importar esta configuración para configurar otra instalación de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="e4e10-123">These settings can then be imported to configure another A4SWIFT installation.</span></span> 

### <a name="export-the-configuration"></a><span data-ttu-id="e4e10-124">Exportar la configuración</span><span class="sxs-lookup"><span data-stu-id="e4e10-124">Export the configuration</span></span>

1. <span data-ttu-id="e4e10-125">Abra el Acelerador de Microsoft BizTalk para SWIFT configuración y seleccione **Exportar configuración**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-125">Open the Microsoft BizTalk Accelerator for SWIFT Configuration, and select **Export Configuration**.</span></span>
2. <span data-ttu-id="e4e10-126">En **Guardar como**, vaya a la carpeta donde desea guardar el archivo de configuración, escriba un nombre para el archivo de configuración y, a continuación, **guardar**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-126">In **Save As**, browse to the folder where you want to save the configuration file, enter a name for the configuration file, and then **Save**.</span></span>
3. <span data-ttu-id="e4e10-127">Cuando se exportan correctamente, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-127">When exported successfully, select **OK**.</span></span>

### <a name="import-a-configuration"></a><span data-ttu-id="e4e10-128">Importar una configuración</span><span class="sxs-lookup"><span data-stu-id="e4e10-128">Import a configuration</span></span>
1. <span data-ttu-id="e4e10-129">Abra el Acelerador de Microsoft BizTalk para SWIFT configuración y seleccione **importar configuración**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-129">Open the Microsoft BizTalk Accelerator for SWIFT Configuration, and select **Import Configuration**.</span></span>
2. <span data-ttu-id="e4e10-130">Vaya a la carpeta que contiene el archivo de configuración, seleccione el archivo y, a continuación, seleccione **importación**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-130">Browse to the folder that contains the configuration file, select the file, and then select **Import**.</span></span>

## <a name="post-configuration-steps"></a><span data-ttu-id="e4e10-131">Pasos posteriores a la configuración</span><span class="sxs-lookup"><span data-stu-id="e4e10-131">Post-configuration steps</span></span>

### <a name="add-users-to-the-a4swift-users-group"></a><span data-ttu-id="e4e10-132">Agregar usuarios al grupo usuarios de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="e4e10-132">Add users to the A4SWIFT Users group</span></span>

<span data-ttu-id="e4e10-133">Después de configurar la [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)], agregar la cuenta que ejecuta la instancia de host BizTalkServerApplication para el **A4SWIFT usuarios** grupo (*no* el **administradores de A4SWIFT** grupo).</span><span class="sxs-lookup"><span data-stu-id="e4e10-133">After you configure the [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)], add the account that runs the BizTalkServerApplication host instance to the **A4SWIFT Users** group (*not* the **A4SWIFT Administrators** group).</span></span> 

<span data-ttu-id="e4e10-134">**Pasos**:</span><span class="sxs-lookup"><span data-stu-id="e4e10-134">**Steps**:</span></span>

1. <span data-ttu-id="e4e10-135">Abra **Services**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-135">Open **Services**.</span></span> <span data-ttu-id="e4e10-136">Los servicios también está disponible en **el administrador del servidor**y, a continuación, **herramientas**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-136">Services is also available in **Server Manager**, and then **Tools**.</span></span> 
2. <span data-ttu-id="e4e10-137">En la lista, busque **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-137">In the list, find **BizTalk Service BizTalk Group: BizTalkServerApplication**.</span></span> 
3. <span data-ttu-id="e4e10-138">Doble: seleccione esta opción para abrir sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="e4e10-138">Double-select to open its properties.</span></span>
4. <span data-ttu-id="e4e10-139">En el **iniciar sesión** ficha, tenga en cuenta la cuenta de usuario aparece como **esta cuenta**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-139">In the **Log On** tab, note the user account listed as **This account**.</span></span>
5. <span data-ttu-id="e4e10-140">Abra **usuarios y grupos locales** (en administración de equipos) y, a continuación, busque la **A4SWIFT usuarios** grupo.</span><span class="sxs-lookup"><span data-stu-id="e4e10-140">Open **Local Users and Groups** (in Computer Management), and then find the **A4SWIFT Users** group.</span></span> <span data-ttu-id="e4e10-141">Agregue la cuenta de usuario a este grupo.</span><span class="sxs-lookup"><span data-stu-id="e4e10-141">Add the user account to this group.</span></span>

> [!TIP] 
> <span data-ttu-id="e4e10-142">La cuenta de instancia de host necesita esta pertenencia a grupos para el componente de tiempo de ejecución de reparación de mensajes de host para tener acceso a la base de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e4e10-142">The host instance account needs this group membership for the host Message Repair runtime component to access the BizTalk Server database.</span></span>

### <a name="check-the-identity-of-the-application-pool"></a><span data-ttu-id="e4e10-143">Comprobar la identidad del grupo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e4e10-143">Check the identity of the application pool</span></span>
<span data-ttu-id="e4e10-144">El servicio web de A4SWIFT_MRSR se hospeda en una aplicación en IIS.</span><span class="sxs-lookup"><span data-stu-id="e4e10-144">The A4SWIFT_MRSR web service is hosted in an application in IIS.</span></span> <span data-ttu-id="e4e10-145">La identidad del grupo de aplicaciones *no* ser servicio de red.</span><span class="sxs-lookup"><span data-stu-id="e4e10-145">The application pool identity *cannot* be Network Service.</span></span> <span data-ttu-id="e4e10-146">Cambie la identidad del grupo de aplicaciones a una cuenta local o de dominio que sea miembro de la **A4SWIFT usuarios** grupo.</span><span class="sxs-lookup"><span data-stu-id="e4e10-146">Change the identity of the application pool to a local or domain account that is a member of the **A4SWIFT Users** group.</span></span>

<span data-ttu-id="e4e10-147">**Pasos**:</span><span class="sxs-lookup"><span data-stu-id="e4e10-147">**Steps**:</span></span>

1. <span data-ttu-id="e4e10-148">Abra **Administrador de Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-148">Open **Internet Information Services Manager**.</span></span> <span data-ttu-id="e4e10-149">El Administrador de IIS también está disponible en **el administrador del servidor**y, a continuación, **herramientas**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-149">The IIS Manager is also available in **Server Manager**, and then **Tools**.</span></span> 
2. <span data-ttu-id="e4e10-150">Expanda el **sitio Web predeterminado**y seleccione el servicio web de A4SWIFT_MRSR.</span><span class="sxs-lookup"><span data-stu-id="e4e10-150">Expand the **Default Web Site**, and select the A4SWIFT_MRSR web service.</span></span> 
3. <span data-ttu-id="e4e10-151">Seleccione **configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="e4e10-151">Select **Basic Settings**.</span></span> <span data-ttu-id="e4e10-152">Se muestra el nombre del grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e4e10-152">The name of the application pool is listed.</span></span>
4. <span data-ttu-id="e4e10-153">En el panel izquierdo, seleccione **grupos de aplicaciones**y, a continuación, seleccione el grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e4e10-153">In the left pane, select **Application Pools**, and then select your application pool.</span></span>
5. <span data-ttu-id="e4e10-154">Seleccione **configuración avanzada**y cambie el **identidad** si es necesario.</span><span class="sxs-lookup"><span data-stu-id="e4e10-154">Select **Advanced Settings**, and change the **Identity** if needed.</span></span>