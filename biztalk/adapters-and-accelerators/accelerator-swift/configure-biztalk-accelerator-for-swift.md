---
title: Configurar el Acelerador de BizTalk para SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e34b0b2d-f563-468b-b6b9-536f0df96f52
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57b56495e66d835451eb8641f3fd9407462593c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997461"
---
# <a name="configure-biztalk-accelerator-for-swift"></a><span data-ttu-id="75f4c-102">Configurar el Acelerador de BizTalk para SWIFT</span><span class="sxs-lookup"><span data-stu-id="75f4c-102">Configure BizTalk Accelerator for SWIFT</span></span>

<span data-ttu-id="75f4c-103">Configurar la [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75f4c-103">Configure the [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)].</span></span> 

<span data-ttu-id="75f4c-104">Al instalar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)], hay una casilla que le permite ejecutar automáticamente la configuración.</span><span class="sxs-lookup"><span data-stu-id="75f4c-104">When you install [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)], there is a checkbox that lets you run the configuration automatically.</span></span> <span data-ttu-id="75f4c-105">O bien, puede abrir la configuración BizTalk Accelerator for SWIFT (A4SWIFT) enumerado en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="75f4c-105">Or, you can open the BizTalk Accelerator for SWIFT (A4SWIFT) Configuration listed in your apps.</span></span>

<span data-ttu-id="75f4c-106">Este tema muestra cómo configurar el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] acelerador, cómo exportar o importar una configuración y también se enumeran los pasos posteriores a la configuración.</span><span class="sxs-lookup"><span data-stu-id="75f4c-106">This topic shows you how to configure the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] accelerator, how to export or import a configuration, and also lists the post-configuration steps.</span></span>

## <a name="configure-a4swift"></a><span data-ttu-id="75f4c-107">Configuración de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="75f4c-107">Configure A4SWIFT</span></span>

1. <span data-ttu-id="75f4c-108">Abra el Acelerador de BizTalk para SWIFT (A4SWIFT) configuración.</span><span class="sxs-lookup"><span data-stu-id="75f4c-108">Open the BizTalk Accelerator for SWIFT (A4SWIFT) Configuration.</span></span>
2. <span data-ttu-id="75f4c-109">Seleccione **MCRR**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-109">Select **MCRR**.</span></span> <span data-ttu-id="75f4c-110">MCRR solo está disponible si ha instalado el **reparación de mensajes y nuevo envío** componentes.</span><span class="sxs-lookup"><span data-stu-id="75f4c-110">MCRR is available only if you installed the **Message Repair and New Submission** components.</span></span>
3. <span data-ttu-id="75f4c-111">Cuando se le pida **desea crear un nuevo grupo de base de datos**:</span><span class="sxs-lookup"><span data-stu-id="75f4c-111">When asked **Do you want to create a new database group**:</span></span>

   * <span data-ttu-id="75f4c-112">Seleccione esta opción para crear los nuevos grupos que se muestra en el **grupo** panel.</span><span class="sxs-lookup"><span data-stu-id="75f4c-112">Select this option to create the new groups shown in the **Group** pane.</span></span> 
   * <span data-ttu-id="75f4c-113">Para unirse a un grupo de base de datos existente, desactive esta opción.</span><span class="sxs-lookup"><span data-stu-id="75f4c-113">To join an existing database group, uncheck this option.</span></span>

4. <span data-ttu-id="75f4c-114">Si instaló **componentes Web de reparación de mensajes y nuevo envío**, a continuación, seleccione **WebService**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-114">If you installed **Web Components for Message Repair and New Submission**, then select **WebService**.</span></span>
5. <span data-ttu-id="75f4c-115">Seleccione el sitio web para hospedar el servicio Web de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="75f4c-115">Select the web site to host the A4SWIFT Web service.</span></span> <span data-ttu-id="75f4c-116">De forma predeterminada, se selecciona el sitio Web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="75f4c-116">By default, the Default Web Site is selected.</span></span>
6. <span data-ttu-id="75f4c-117">Seleccione **aplicar configuración**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-117">Select **Apply Configuration**.</span></span>
7. <span data-ttu-id="75f4c-118">En **resumen**, compruebe los valores de configuración y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-118">In **Summary**, verify the configuration settings, and then click **Configure**.</span></span> 

    > [!TIP] 
    > <span data-ttu-id="75f4c-119">Puede guardar los ajustes de configuración como archivo XML, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="75f4c-119">You can save the configuration settings as an XML file, if desired.</span></span>

8. <span data-ttu-id="75f4c-120">Seleccione **finalizar** cuando se complete la configuración.</span><span class="sxs-lookup"><span data-stu-id="75f4c-120">Select **Finish** when the configuration completes.</span></span>

## <a name="export-or-import-a-configuration"></a><span data-ttu-id="75f4c-121">Exportar o importar una configuración</span><span class="sxs-lookup"><span data-stu-id="75f4c-121">Export or import a configuration</span></span>
<span data-ttu-id="75f4c-122">Puede exportar la configuración de A4SWIFT a un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="75f4c-122">You can export the configuration settings of A4SWIFT to an XML file.</span></span> <span data-ttu-id="75f4c-123">Estas opciones, a continuación, pueden importarse para configurar otra instalación de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="75f4c-123">These settings can then be imported to configure another A4SWIFT installation.</span></span> 

### <a name="export-the-configuration"></a><span data-ttu-id="75f4c-124">Exportar la configuración</span><span class="sxs-lookup"><span data-stu-id="75f4c-124">Export the configuration</span></span>

1. <span data-ttu-id="75f4c-125">Abra el Acelerador de Microsoft BizTalk para SWIFT configuración y seleccione **Exportar configuración**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-125">Open the Microsoft BizTalk Accelerator for SWIFT Configuration, and select **Export Configuration**.</span></span>
2. <span data-ttu-id="75f4c-126">En **Guardar como**, vaya a la carpeta donde desea guardar el archivo de configuración, escriba un nombre para el archivo de configuración y, a continuación, **guardar**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-126">In **Save As**, browse to the folder where you want to save the configuration file, enter a name for the configuration file, and then **Save**.</span></span>
3. <span data-ttu-id="75f4c-127">Cuando se exportan correctamente, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-127">When exported successfully, select **OK**.</span></span>

### <a name="import-a-configuration"></a><span data-ttu-id="75f4c-128">Importar una configuración</span><span class="sxs-lookup"><span data-stu-id="75f4c-128">Import a configuration</span></span>
1. <span data-ttu-id="75f4c-129">Abra el Acelerador de Microsoft BizTalk para SWIFT configuración y seleccione **importar configuración**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-129">Open the Microsoft BizTalk Accelerator for SWIFT Configuration, and select **Import Configuration**.</span></span>
2. <span data-ttu-id="75f4c-130">Vaya a la carpeta que contiene el archivo de configuración, seleccione el archivo y, a continuación, seleccione **importación**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-130">Browse to the folder that contains the configuration file, select the file, and then select **Import**.</span></span>

## <a name="post-configuration-steps"></a><span data-ttu-id="75f4c-131">Pasos posteriores a la configuración</span><span class="sxs-lookup"><span data-stu-id="75f4c-131">Post-configuration steps</span></span>

### <a name="add-users-to-the-a4swift-users-group"></a><span data-ttu-id="75f4c-132">Agregar usuarios al grupo usuarios de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="75f4c-132">Add users to the A4SWIFT Users group</span></span>

<span data-ttu-id="75f4c-133">Después de configurar el [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)], agregue la cuenta que ejecuta la instancia de host BizTalkServerApplication para el **los usuarios de A4SWIFT** grupo (*no* el **administradoresdeA4SWIFT** grupo).</span><span class="sxs-lookup"><span data-stu-id="75f4c-133">After you configure the [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)], add the account that runs the BizTalkServerApplication host instance to the **A4SWIFT Users** group (*not* the **A4SWIFT Administrators** group).</span></span> 

<span data-ttu-id="75f4c-134">**Pasos**:</span><span class="sxs-lookup"><span data-stu-id="75f4c-134">**Steps**:</span></span>

1. <span data-ttu-id="75f4c-135">Abra **servicios**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-135">Open **Services**.</span></span> <span data-ttu-id="75f4c-136">También está disponible en los servicios **administrador del servidor**y, a continuación, **herramientas**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-136">Services is also available in **Server Manager**, and then **Tools**.</span></span> 
2. <span data-ttu-id="75f4c-137">En la lista, busque **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-137">In the list, find **BizTalk Service BizTalk Group: BizTalkServerApplication**.</span></span> 
3. <span data-ttu-id="75f4c-138">Haga doble clic para abrir sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="75f4c-138">Double-select to open its properties.</span></span>
4. <span data-ttu-id="75f4c-139">En el **iniciar sesión** ficha, tenga en cuenta que la cuenta de usuario aparece como **esta cuenta**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-139">In the **Log On** tab, note the user account listed as **This account**.</span></span>
5. <span data-ttu-id="75f4c-140">Abra **usuarios y grupos locales** (administración de equipos) y, a continuación, busque el **los usuarios de A4SWIFT** grupo.</span><span class="sxs-lookup"><span data-stu-id="75f4c-140">Open **Local Users and Groups** (in Computer Management), and then find the **A4SWIFT Users** group.</span></span> <span data-ttu-id="75f4c-141">Agregue la cuenta de usuario a este grupo.</span><span class="sxs-lookup"><span data-stu-id="75f4c-141">Add the user account to this group.</span></span>

> [!TIP] 
> <span data-ttu-id="75f4c-142">La cuenta de instancia de host necesita esta pertenencia a grupos para el componente de tiempo de ejecución de reparación de mensajes de host para tener acceso a la base de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="75f4c-142">The host instance account needs this group membership for the host Message Repair runtime component to access the BizTalk Server database.</span></span>

### <a name="check-the-identity-of-the-application-pool"></a><span data-ttu-id="75f4c-143">Comprobar la identidad del grupo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="75f4c-143">Check the identity of the application pool</span></span>
<span data-ttu-id="75f4c-144">El servicio web A4SWIFT_MRSR se hospeda en una aplicación en IIS.</span><span class="sxs-lookup"><span data-stu-id="75f4c-144">The A4SWIFT_MRSR web service is hosted in an application in IIS.</span></span> <span data-ttu-id="75f4c-145">La identidad del grupo de aplicación *no* ser servicio de red.</span><span class="sxs-lookup"><span data-stu-id="75f4c-145">The application pool identity *cannot* be Network Service.</span></span> <span data-ttu-id="75f4c-146">Cambiar la identidad del grupo de aplicaciones a una cuenta local o de dominio que sea miembro de la **los usuarios de A4SWIFT** grupo.</span><span class="sxs-lookup"><span data-stu-id="75f4c-146">Change the identity of the application pool to a local or domain account that is a member of the **A4SWIFT Users** group.</span></span>

<span data-ttu-id="75f4c-147">**Pasos**:</span><span class="sxs-lookup"><span data-stu-id="75f4c-147">**Steps**:</span></span>

1. <span data-ttu-id="75f4c-148">Abra **Administrador de Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-148">Open **Internet Information Services Manager**.</span></span> <span data-ttu-id="75f4c-149">También está disponible en el Administrador de IIS **administrador del servidor**y, a continuación, **herramientas**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-149">The IIS Manager is also available in **Server Manager**, and then **Tools**.</span></span> 
2. <span data-ttu-id="75f4c-150">Expanda el **sitio Web predeterminado**y seleccione el servicio web A4SWIFT_MRSR.</span><span class="sxs-lookup"><span data-stu-id="75f4c-150">Expand the **Default Web Site**, and select the A4SWIFT_MRSR web service.</span></span> 
3. <span data-ttu-id="75f4c-151">Seleccione **configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="75f4c-151">Select **Basic Settings**.</span></span> <span data-ttu-id="75f4c-152">Se muestra el nombre del grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="75f4c-152">The name of the application pool is listed.</span></span>
4. <span data-ttu-id="75f4c-153">En el panel izquierdo, seleccione **grupos de aplicaciones**y, a continuación, seleccione el grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="75f4c-153">In the left pane, select **Application Pools**, and then select your application pool.</span></span>
5. <span data-ttu-id="75f4c-154">Seleccione **configuración avanzada**y cambie el **identidad** si es necesario.</span><span class="sxs-lookup"><span data-stu-id="75f4c-154">Select **Advanced Settings**, and change the **Identity** if needed.</span></span>