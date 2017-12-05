---
title: Configurar e instalar los requisitos previos para BizTalk Server 2016 | Documentos de Microsoft
description: "Instrucciones paso a paso para instalar y configurar el software necesario y la configuración de BizTalk Server 2016"
author: MandiOhlinger
manager: anneta
ms.prod: biztalk-server
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa70b621-903a-4cfa-9cb0-c6a82ed8f733
caps.latest.revision: "11"
ms.author: mandia
ms.openlocfilehash: 2f03aaf7d33cc494320d1ef0944b48286bc1b24c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="set-up-and-install-prerequisites-for-biztalk-server-2016"></a><span data-ttu-id="5be63-103">Configurar e instalar los requisitos previos de BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="5be63-103">Set up and install prerequisites for BizTalk Server 2016</span></span>
<span data-ttu-id="5be63-104">Configure el servidor e instale y configure los requisitos previos de software.</span><span class="sxs-lookup"><span data-stu-id="5be63-104">Set up the server, and install and configure the software prerequisites.</span></span>

## <a name="join-the-administrators-group"></a><span data-ttu-id="5be63-105">Unirse al grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="5be63-105">Join the Administrators Group</span></span>
<span data-ttu-id="5be63-106">Para instalar y configurar BizTalk Server, inicie sesión en el servidor con una cuenta de administrador en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="5be63-106">To install and configure BizTalk Server, sign in to the server using an administrator account on the local computer.</span></span> <span data-ttu-id="5be63-107">Agregue las cuentas de usuario que administren BizTalk Server al grupo de administradores local:</span><span class="sxs-lookup"><span data-stu-id="5be63-107">Add any user accounts that are administering the BizTalk Server to the local Administrators group:</span></span>

1.  <span data-ttu-id="5be63-108">En el menú Inicio, abra **Administración de equipos**.</span><span class="sxs-lookup"><span data-stu-id="5be63-108">In the Start menu, open **Computer Management**.</span></span>

    * <span data-ttu-id="5be63-109">O bien, abra **Herramientas administrativas** y, después, seleccione **Administración de equipos**.</span><span class="sxs-lookup"><span data-stu-id="5be63-109">Or, open **Administrative Tools**, and then select **Computer Management**.</span></span>
    * <span data-ttu-id="5be63-110">O bien, abra **Administrador de servidores**, seleccione **Herramientas** y, después, **Administración de equipos**.</span><span class="sxs-lookup"><span data-stu-id="5be63-110">Or, open **Server Manager**, select **Tools**, and then select **Computer Management**.</span></span>
  
2.  <span data-ttu-id="5be63-111">Expanda **Usuarios y grupos locales** y seleccione **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="5be63-111">Expand **Local Users and Groups**, and select **Groups**.</span></span>
3.  <span data-ttu-id="5be63-112">Haga clic con el botón derecho en el grupo **Administradores** y seleccione **Agregar al grupo**.</span><span class="sxs-lookup"><span data-stu-id="5be63-112">Right-click the **Administrators** group, and select **Add to Group**.</span></span> <span data-ttu-id="5be63-113">**Agregue** las cuentas y seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="5be63-113">**Add** your accounts, and select **OK** to save your changes.</span></span> 

## <a name="change-the-computer-name-optional"></a><span data-ttu-id="5be63-114">Cambiar el nombre del equipo (opcional)</span><span class="sxs-lookup"><span data-stu-id="5be63-114">Change the computer name (optional)</span></span>
<span data-ttu-id="5be63-115">Si el nombre del equipo tiene más de 15 caracteres, configuración de BizTalk Server genera un error.</span><span class="sxs-lookup"><span data-stu-id="5be63-115">If your computer name is longer than 15 characters, then BizTalk Server configuration fails.</span></span> <span data-ttu-id="5be63-116">Para cambiar el nombre del equipo a menos de 15 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5be63-116">To change the computer name to less than 15 characters:</span></span>

1.  <span data-ttu-id="5be63-117">En **Administrador de servidores** > **Panel**, seleccione **Servidor local**.</span><span class="sxs-lookup"><span data-stu-id="5be63-117">In **Server Manager** > **Dashboard**, select **Local Server**.</span></span> 
2.  <span data-ttu-id="5be63-118">En **Propiedades**, seleccione la propiedad Nombre del equipo para cambiarla.</span><span class="sxs-lookup"><span data-stu-id="5be63-118">In **Properties**, select the Computer name property to change it.</span></span>
3. <span data-ttu-id="5be63-119">Reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="5be63-119">Restart the computer.</span></span> 

<span data-ttu-id="5be63-120">**CONSULTE TAMBIÉN**: [Rename-Computer](https://technet.microsoft.com/library/hh849792.aspx) de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5be63-120">**SEE ALSO** : Windows PowerShell [Rename-Computer](https://technet.microsoft.com/library/hh849792.aspx)</span></span>

## <a name="enable-network-dtc-access"></a><span data-ttu-id="5be63-121">Habilitar el acceso a DTC desde la red</span><span class="sxs-lookup"><span data-stu-id="5be63-121">Enable Network DTC Access</span></span>
<span data-ttu-id="5be63-122">Si BizTalk y SQL Server están instalados en equipos independientes, habilite el acceso a DTC desde la red en BizTalk Server y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-122">If BizTalk and SQL Server are installed on separate computers, then enable Network DTC Access on the BizTalk Server and the SQL Server.</span></span> 

1. <span data-ttu-id="5be63-123">En el menú Inicio, abra "dcomcnfg".</span><span class="sxs-lookup"><span data-stu-id="5be63-123">In the Start menu, open "dcomcnfg".</span></span>

    * <span data-ttu-id="5be63-124">O bien, abra **Herramientas administrativas** y, después, seleccione **Servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="5be63-124">Or, open **Administrative Tools**, and then select **Component Services**.</span></span>
    * <span data-ttu-id="5be63-125">O bien, abra **Administrador de servidores**, seleccione **Herramientas** y, después, **Servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="5be63-125">Or, open **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>
  
2. <span data-ttu-id="5be63-126">Expanda **Servicios de componentes**, **Equipos**, **Mi PC** y **Coordinador de transacciones distribuidas**.</span><span class="sxs-lookup"><span data-stu-id="5be63-126">Expand **Component Services**, expand **Computers**, expand **My Computer**,  and expand **Distributed Transaction Coordinator**.</span></span>
3. <span data-ttu-id="5be63-127">Haga clic con el botón derecho en **DTC local** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5be63-127">Right-click **Local DTC**, and select **Properties**.</span></span>
4. <span data-ttu-id="5be63-128">Vaya a la pestaña **Seguridad** y seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5be63-128">Go to the **Security** tab, and check the following:</span></span>  
    * <span data-ttu-id="5be63-129">Acceso de DTC a la red</span><span class="sxs-lookup"><span data-stu-id="5be63-129">Network DTC Access</span></span>
    * <span data-ttu-id="5be63-130">Permitir entrantes</span><span class="sxs-lookup"><span data-stu-id="5be63-130">Allow Inbound</span></span>
    * <span data-ttu-id="5be63-131">Permitir salientes</span><span class="sxs-lookup"><span data-stu-id="5be63-131">Allow Outbound</span></span>
    * <span data-ttu-id="5be63-132">No se requiere autenticación</span><span class="sxs-lookup"><span data-stu-id="5be63-132">No Authentication Required</span></span>
5. <span data-ttu-id="5be63-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5be63-133">Select **OK**.</span></span> <span data-ttu-id="5be63-134">Si se le pide que reinicie MS DTC, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5be63-134">If prompted to restart MS DTC, select **Yes**.</span></span> 

<span data-ttu-id="5be63-135">Para conocer otras opciones necesarias, consulte [Solucionar problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span><span class="sxs-lookup"><span data-stu-id="5be63-135">For additional settings that may be needed, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>

## <a name="configure-application-event-log-optional"></a><span data-ttu-id="5be63-136">Configurar el registro de eventos de aplicación (opcional)</span><span class="sxs-lookup"><span data-stu-id="5be63-136">Configure Application Event Log (optional)</span></span>

<span data-ttu-id="5be63-137">El programa de instalación de BizTalk Server mantiene un registro de eventos en el registro de eventos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5be63-137">BizTalk Server setup keeps a record of events in the Application Event Log.</span></span> <span data-ttu-id="5be63-138">En función de las características de BizTalk Server instaladas, la cantidad de espacio necesaria en el registro puede superar su límite.</span><span class="sxs-lookup"><span data-stu-id="5be63-138">Depending on the BizTalk Server features installed, the amount of space required in the log may exceed its limit.</span></span> <span data-ttu-id="5be63-139">Si se agota el espacio del registro de eventos de aplicaciones durante la instalación, esta no se llevará a cabo.</span><span class="sxs-lookup"><span data-stu-id="5be63-139">If the application event log runs out of space during the setup, the installation fails.</span></span> <span data-ttu-id="5be63-140">Este error se puede evitar cambiando la configuración del registro de eventos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5be63-140">Changing the Application Event Log settings prevents this failure.</span></span>

1. <span data-ttu-id="5be63-141">En el menú Inicio, abra el **Visor de eventos**:</span><span class="sxs-lookup"><span data-stu-id="5be63-141">In the Start menu, open **Event Viewer**:</span></span>

    * <span data-ttu-id="5be63-142">O bien, abra **Herramientas administrativas** y, después, seleccione **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="5be63-142">Or, open **Administrative Tools**, and then select **Event Viewer**.</span></span>
    * <span data-ttu-id="5be63-143">O bien, abra **Administrador de servidores**, seleccione **Herramientas** y, después, **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="5be63-143">Or, open **Server Manager**, select **Tools**, and then select **Event Viewer**.</span></span>
  
2. <span data-ttu-id="5be63-144">Expanda **Registros de Windows**, haga clic con el botón derecho en **Aplicación** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5be63-144">Expand **Windows Logs**, right-click **Application**, and then select **Properties**.</span></span> 
3. <span data-ttu-id="5be63-145">Para determinar el espacio disponible, compare las propiedades **Tamaño del registro** y **Máximo tamaño de registro**.</span><span class="sxs-lookup"><span data-stu-id="5be63-145">To determine the available space, compare the **Log Size** and the **Maximum log size** properties.</span></span> 

    * <span data-ttu-id="5be63-146">Para agregar más espacio, especifique un número más alto en **Máximo tamaño de registro**.</span><span class="sxs-lookup"><span data-stu-id="5be63-146">To add space, enter a higher number in **Maximum log size**.</span></span>
    * <span data-ttu-id="5be63-147">Para habilitar la sobrescritura de los eventos antiguos cuando se llene el registro, seleccione **Sobrescribir eventos cuando sea necesario**.</span><span class="sxs-lookup"><span data-stu-id="5be63-147">To enable overwriting of old events when the log becomes full, select **Overwrite events as needed**.</span></span>
    * <span data-ttu-id="5be63-148">Para borrar los eventos del registro, seleccione **Vaciar registro**.</span><span class="sxs-lookup"><span data-stu-id="5be63-148">To clear the log events, select **Clear log**.</span></span>

4. <span data-ttu-id="5be63-149">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5be63-149">Select **OK**.</span></span>

## <a name="edge-cant-be-opened-optional"></a><span data-ttu-id="5be63-150">No se puede abrir borde (opcional)</span><span class="sxs-lookup"><span data-stu-id="5be63-150">Edge can’t be opened (optional)</span></span>

<span data-ttu-id="5be63-151">Al usar Edge, aparece el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="5be63-151">When using Edge, the following message displays:</span></span>  
`Microsoft Edge can't be opened using the Built-in Administrator account. Sign in with a different account and try again.`

<span data-ttu-id="5be63-152">Para permitir que se abra Edge con la cuenta predefinida de administrador:</span><span class="sxs-lookup"><span data-stu-id="5be63-152">To allow Edge to open using the built-in administrator account:</span></span>

1. <span data-ttu-id="5be63-153">En el menú Inicio, abra **Directiva de seguridad local**.</span><span class="sxs-lookup"><span data-stu-id="5be63-153">In the Start menu, open **Local Security Policy**.</span></span> <span data-ttu-id="5be63-154">O bien, abra **Administrador de servidores**, seleccione **Herramientas** y, después, **Directiva de seguridad local**.</span><span class="sxs-lookup"><span data-stu-id="5be63-154">Or, open **Server Manager**, select **Tools**, and then select **Local Security Policy**.</span></span>
2.  <span data-ttu-id="5be63-155">Expanda **Directivas locales** y seleccione **Opciones de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="5be63-155">Expand **Local Policies**, and select **Security Options**.</span></span> 
3.  <span data-ttu-id="5be63-156">Vaya a la directiva **Control de cuentas de usuario: Modo de aprobación de administrador para la cuenta predefinida Administrador** y **habilite** la directiva.</span><span class="sxs-lookup"><span data-stu-id="5be63-156">Go to the **User Account Control: Admin Approval Mode for the Built-in Administrator account** policy, and **Enable** the policy.</span></span> 
4. <span data-ttu-id="5be63-157">Seleccione **Aceptar** y reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="5be63-157">Select **OK**, and restart your computer.</span></span>

## <a name="install-windows-updates"></a><span data-ttu-id="5be63-158">Instalar actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="5be63-158">Install Windows Updates</span></span>

<span data-ttu-id="5be63-159">Asegúrese de instalar las últimas actualizaciones críticas de Windows.</span><span class="sxs-lookup"><span data-stu-id="5be63-159">Be sure to install the latest critical Windows updates.</span></span> 

1. <span data-ttu-id="5be63-160">En el menú Inicio, abra **Actualizaciones de Windows** y compruebe si hay actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="5be63-160">On the Start menu, open **Windows Updates**, and check for updates.</span></span> <span data-ttu-id="5be63-161">También puede abrir **Configuración** y seleccionar **Actualización y seguridad**.</span><span class="sxs-lookup"><span data-stu-id="5be63-161">You can also open **Settings**, and select **Update and security**.</span></span>
2. <span data-ttu-id="5be63-162">Tras instalar las actualizaciones, puede ser necesario reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="5be63-162">After installing updates, you may need to restart the computer.</span></span>

## <a name="enable-iis"></a><span data-ttu-id="5be63-163">Habilite el servicio IIS</span><span class="sxs-lookup"><span data-stu-id="5be63-163">Enable IIS</span></span>
<span data-ttu-id="5be63-164">BizTalk Server requiere IIS para las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="5be63-164">BizTalk Server requires IIS for the following features:</span></span>

- <span data-ttu-id="5be63-165">adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="5be63-165">HTTP adapter</span></span>
- <span data-ttu-id="5be63-166">Adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="5be63-166">SOAP adapter</span></span>
- <span data-ttu-id="5be63-167">Adaptador de Windows Sharepoint Services</span><span class="sxs-lookup"><span data-stu-id="5be63-167">Windows SharePoint Services adapter</span></span>
- <span data-ttu-id="5be63-168">Cifrado de Capa de sockets seguros (SSL)</span><span class="sxs-lookup"><span data-stu-id="5be63-168">Secure Sockets Layer (SSL) encryption</span></span>
- <span data-ttu-id="5be63-169">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="5be63-169">BAM Portal</span></span>
- <span data-ttu-id="5be63-170">ENRUTAMIENTO</span><span class="sxs-lookup"><span data-stu-id="5be63-170">EDI</span></span>

<span data-ttu-id="5be63-171">IIS se incluye con el sistema operativo como un **rol** o una **característica**, según el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5be63-171">IIS is included with the operating system as a **Role** or a **Feature**, depending on the OS.</span></span> <span data-ttu-id="5be63-172">Para instalar:</span><span class="sxs-lookup"><span data-stu-id="5be63-172">To install:</span></span>

1. <span data-ttu-id="5be63-173">En el menú Inicio, abra **Activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="5be63-173">In the Start menu, open **Turn Windows Features on or off**.</span></span> <span data-ttu-id="5be63-174">O bien, abra **Administrador del servidor**, seleccione **Administrar** y, después, **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="5be63-174">Or, open **Server Manager**, select **Manage**, and then select **Add roles and features**.</span></span>
2. <span data-ttu-id="5be63-175">Seleccione **Internet Information Services** o **Servidor web (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="5be63-175">Select **Internet Information Services** or **Web Server (IIS)**.</span></span> <span data-ttu-id="5be63-176">Además de las opciones predeterminadas, seleccione las siguientes:</span><span class="sxs-lookup"><span data-stu-id="5be63-176">In addition to the default checked options, also select the following:</span></span> 

    <span data-ttu-id="5be63-177">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="5be63-177">**Windows 10**</span></span>
    - <span data-ttu-id="5be63-178">En **Herramientas de administración web**, seleccione también:</span><span class="sxs-lookup"><span data-stu-id="5be63-178">In **Web Management Tools**, also check:</span></span>  
        - <span data-ttu-id="5be63-179">Compatibilidad con la administración de IIS 6</span><span class="sxs-lookup"><span data-stu-id="5be63-179">IIS 6 Management Compatibility</span></span>
        - <span data-ttu-id="5be63-180">Consola de administración de IIS 6</span><span class="sxs-lookup"><span data-stu-id="5be63-180">IIS 6 Management Console</span></span>
        - <span data-ttu-id="5be63-181">Herramientas de scripting de IIS 6 (instala adsutil.vbs)</span><span class="sxs-lookup"><span data-stu-id="5be63-181">IIS 6 Scripting Tools (Installs adsutil.vbs)</span></span>
        - <span data-ttu-id="5be63-182">Compatibilidad con la configuración de IIS 6 y metabase de IIS</span><span class="sxs-lookup"><span data-stu-id="5be63-182">IIS Metabase and IIS 6 configuration compatibility</span></span>
        - <span data-ttu-id="5be63-183">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="5be63-183">IIS Management Console</span></span>
    - <span data-ttu-id="5be63-184">En **Servicios World Wide Web**, expanda **Seguridad** y seleccione también:</span><span class="sxs-lookup"><span data-stu-id="5be63-184">In **World Wide Web Services**, expand **Security** and also check:</span></span>
        - <span data-ttu-id="5be63-185">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="5be63-185">Basic Authentication</span></span>
        - <span data-ttu-id="5be63-186">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="5be63-186">Windows Authentication</span></span>    

    <span data-ttu-id="5be63-187">**Windows Server**</span><span class="sxs-lookup"><span data-stu-id="5be63-187">**Windows Server**</span></span>
    - <span data-ttu-id="5be63-188">En **Seguridad**, seleccione también:</span><span class="sxs-lookup"><span data-stu-id="5be63-188">In **Security**, also check:</span></span> 
        - <span data-ttu-id="5be63-189">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="5be63-189">Basic Authentication</span></span>
        - <span data-ttu-id="5be63-190">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="5be63-190">Windows Authentication</span></span>    
    - <span data-ttu-id="5be63-191">En **Herramientas de administración**, seleccione también:</span><span class="sxs-lookup"><span data-stu-id="5be63-191">In **Management Tools**, also check:</span></span>  
        - <span data-ttu-id="5be63-192">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="5be63-192">IIS Management Console</span></span>
        - <span data-ttu-id="5be63-193">Compatibilidad con la administración de IIS 6</span><span class="sxs-lookup"><span data-stu-id="5be63-193">IIS 6 Management Compatibility</span></span>
        - <span data-ttu-id="5be63-194">Compatibilidad con la metabase de IIS 6</span><span class="sxs-lookup"><span data-stu-id="5be63-194">IIS 6 Metabase compatibility</span></span>
        - <span data-ttu-id="5be63-195">Consola de administración de IIS 6</span><span class="sxs-lookup"><span data-stu-id="5be63-195">IIS 6 Management Console</span></span>
        - <span data-ttu-id="5be63-196">Herramientas de scripting de IIS 6 (instala adsutil.vbs)</span><span class="sxs-lookup"><span data-stu-id="5be63-196">IIS 6 Scripting Tools (Installs adsutil.vbs)</span></span>

3. <span data-ttu-id="5be63-197">Continúe con la instalación y reinicie el equipo si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="5be63-197">Continue with the installation, and restart the computer if prompted.</span></span> 

<span data-ttu-id="5be63-198">**CONSULTE TAMBIÉN**: Instalar IIS en [Windows 8 o Windows Server 2012](http://www.iis.net/learn/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012).</span><span class="sxs-lookup"><span data-stu-id="5be63-198">**SEE ALSO** : Install IIS on [Windows 8 or Windows Server 2012](http://www.iis.net/learn/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012).</span></span>


## <a name="run-64-bit-bam-portal-optional"></a><span data-ttu-id="5be63-199">Ejecutar el portal de BAM de 64 bits (opcional)</span><span class="sxs-lookup"><span data-stu-id="5be63-199">Run 64-bit BAM portal (optional)</span></span>
<span data-ttu-id="5be63-200">Si no utiliza el portal de BAM, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="5be63-200">If you don't use the BAM portal, then you can skip this section.</span></span> 

<span data-ttu-id="5be63-201">El portal de BAM se ejecuta en modo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="5be63-201">The BAM Portal runs in 32-bit mode.</span></span> <span data-ttu-id="5be63-202">Si está utilizando Internet Information Services (IIS) en un entorno de 64 bits, a continuación, establezca el grupo de aplicaciones para que se ejecute en modo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="5be63-202">If you are using Internet Information Services (IIS) in a 64-bit environment, then set the application pool to run in 32-bit mode.</span></span> 

#### <a name="using-adsutilvbs"></a><span data-ttu-id="5be63-203">Mediante adsutil.vbs</span><span class="sxs-lookup"><span data-stu-id="5be63-203">Using adsutil.vbs</span></span>
1.  <span data-ttu-id="5be63-204">Abra un símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="5be63-204">Open a command prompt as administrator.</span></span> 
2.  <span data-ttu-id="5be63-205">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="5be63-205">In the command prompt, type:</span></span>  
    `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`
3. <span data-ttu-id="5be63-206">Seleccione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="5be63-206">Select Enter.</span></span>

#### <a name="using-iis-manager"></a><span data-ttu-id="5be63-207">Mediante el Administrador de IIS</span><span class="sxs-lookup"><span data-stu-id="5be63-207">Using IIS Manager</span></span>
1. <span data-ttu-id="5be63-208">En el menú Inicio, abra "inetmgr".</span><span class="sxs-lookup"><span data-stu-id="5be63-208">In the Start menu, open "inetmgr".</span></span>
2.  <span data-ttu-id="5be63-209">Expanda el nombre del equipo y seleccione **Grupos de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="5be63-209">Expand the computer name, and select **Application Pools**.</span></span>
3.  <span data-ttu-id="5be63-210">Haga clic con el botón derecho en **DefaultAppPool** y seleccione **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="5be63-210">Right-click **DefaultAppPool**, and select **Advanced Settings**.</span></span> 
4.  <span data-ttu-id="5be63-211">Cambie el valor de **Habilitar aplicaciones de 32 bits** a **True**.</span><span class="sxs-lookup"><span data-stu-id="5be63-211">Change the value of **Enable 32-bit Applications** to **True**.</span></span> 
5.  <span data-ttu-id="5be63-212">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5be63-212">Select **OK**.</span></span>

## <a name="install-windows-identity-foundation-wif-optional"></a><span data-ttu-id="5be63-213">Instalar Windows Identity Foundation (WIF) (opcional)</span><span class="sxs-lookup"><span data-stu-id="5be63-213">Install Windows Identity Foundation (WIF) (optional)</span></span>
<span data-ttu-id="5be63-214">Si usa el adaptador de SharePoint Services, BizTalk Server requiere WIF.</span><span class="sxs-lookup"><span data-stu-id="5be63-214">If you use the SharePoint Services adapter, BizTalk Server requires WIF.</span></span> <span data-ttu-id="5be63-215">Si no usa el adaptador de SharePoint Services, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="5be63-215">If you don't use the SharePoint Services adapter, you can skip this section.</span></span>

<span data-ttu-id="5be63-216">Windows Identity Foundation se incluye con el sistema operativo como **característica**.</span><span class="sxs-lookup"><span data-stu-id="5be63-216">Windows Identity Foundation is included with the operating system as a **Feature**.</span></span>

1. <span data-ttu-id="5be63-217">En el menú Inicio, abra **Activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="5be63-217">In the Start menu, open **Turn Windows Features on or off**.</span></span> <span data-ttu-id="5be63-218">O bien, abra **Administrador del servidor**, seleccione **Administrar** y, después, **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="5be63-218">Or, open **Server Manager**, select **Manage**, and then select **Add roles and features**.</span></span>
2. <span data-ttu-id="5be63-219">Seleccione **Windows Identity Foundation 3.5** y continúe con la instalación.</span><span class="sxs-lookup"><span data-stu-id="5be63-219">Select **Windows Identity Foundation 3.5**, and continue with the installation.</span></span> 
3. <span data-ttu-id="5be63-220">Reinicie el equipo si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="5be63-220">Restart the computer if prompted.</span></span>

## <a name="install--configure-smtp-server-optional"></a><span data-ttu-id="5be63-221">Instalar y configurar el servidor SMTP (opcional)</span><span class="sxs-lookup"><span data-stu-id="5be63-221">Install & configure SMTP Server (optional)</span></span>
<span data-ttu-id="5be63-222">Si usa alertas de BAM, BizTalk Server requiere el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5be63-222">If you use BAM Alerts, BizTalk Server requires SMTP Server.</span></span> <span data-ttu-id="5be63-223">Si no usa las alertas de BAM, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="5be63-223">If you don't use BAM Alerts, you can skip this section.</span></span>

<span data-ttu-id="5be63-224">Correo electrónico de base de datos de SQL Server usa un servidor SMTP para enviar las alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="5be63-224">SQL Server Database Mail uses an SMTP Server to send BAM Alerts.</span></span> <span data-ttu-id="5be63-225">El servidor SMTP se puede instalar en modo local o en BizTalk Server u otro servidor que tenga IIS instalado.</span><span class="sxs-lookup"><span data-stu-id="5be63-225">SMTP Server can be installed locally on the BizTalk Server or on another server with IIS installed.</span></span> <span data-ttu-id="5be63-226">El servidor SMTP no está disponible en sistemas operativos cliente, como Windows 8.1 o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5be63-226">SMTP Server is not available on client operating systems, such as Windows 8.1 or Windows 10.</span></span> 

<span data-ttu-id="5be63-227">El servidor SMTP se incluye con los sistemas operativos de servidor como una **característica**.</span><span class="sxs-lookup"><span data-stu-id="5be63-227">SMTP Server is included with server operating systems as a **Feature**.</span></span>

1. <span data-ttu-id="5be63-228">En el menú Inicio, abra **Activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="5be63-228">In the Start menu, open **Turn Windows Features on or off**.</span></span> <span data-ttu-id="5be63-229">O bien, abra **Administrador del servidor**, seleccione **Administrar** y, después, **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="5be63-229">Or, open **Server Manager**, select **Manage**, and then select **Add roles and features**.</span></span>
2. <span data-ttu-id="5be63-230">Seleccione **Servidor SMTP** y continúe con la instalación.</span><span class="sxs-lookup"><span data-stu-id="5be63-230">Select **SMTP Server**, and continue with the installation.</span></span> 
3. <span data-ttu-id="5be63-231">Reinicie el equipo si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="5be63-231">Restart the computer if prompted.</span></span>

## <a name="install-excel-2016-or-2013-optional"></a><span data-ttu-id="5be63-232">Instalar Excel 2016 o 2013 (opcional)</span><span class="sxs-lookup"><span data-stu-id="5be63-232">Install Excel 2016 or 2013 (optional)</span></span>
<span data-ttu-id="5be63-233">Si utiliza supervisión de la actividad económica (BAM), BizTalk Server requiere Excel.</span><span class="sxs-lookup"><span data-stu-id="5be63-233">If you use Business Activity Monitoring (BAM), BizTalk Server requires Excel.</span></span> <span data-ttu-id="5be63-234">Si no usa BAM, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="5be63-234">If you don't use BAM, you can skip this section.</span></span>

<span data-ttu-id="5be63-235">El libro de BAM de Office Excel se usa para definir los procesos empresariales que desee supervisar.</span><span class="sxs-lookup"><span data-stu-id="5be63-235">The BAM Office Excel Workbook defines the business processes you want to monitor.</span></span> <span data-ttu-id="5be63-236">El libro de Excel de BAM también se usa para definir el modo en que los usuarios empresariales ven los datos que BAM recopila.</span><span class="sxs-lookup"><span data-stu-id="5be63-236">You also use the BAM Excel Workbook to define the way business users see the data collected by BAM.</span></span>

> [!IMPORTANT] 
> * <span data-ttu-id="5be63-237">BizTalk Server solo es compatible con la versión de 32 bits de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="5be63-237">BizTalk Server supports only 32-bit version of Microsoft Office.</span></span> 
> * <span data-ttu-id="5be63-238">Para cargar correctamente BAM.xla en Excel, instale **Visual Basic para Aplicaciones** (en **Características compartidas de Office**).</span><span class="sxs-lookup"><span data-stu-id="5be63-238">To successfully load BAM.xla into Excel, install **Visual Basic for Applications** (under **Office Shared Features**).</span></span> <span data-ttu-id="5be63-239">En caso contrario, es posible que reciba este error: `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`</span><span class="sxs-lookup"><span data-stu-id="5be63-239">Otherwise, you may get error: `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`</span></span>

#### <a name="install-excel-2016"></a><span data-ttu-id="5be63-240">Instalar Excel 2016</span><span class="sxs-lookup"><span data-stu-id="5be63-240">Install Excel 2016</span></span>

<span data-ttu-id="5be63-241">Office 2016 se instala con "hacer clic y ejecutar" o el "instalador de C2R".</span><span class="sxs-lookup"><span data-stu-id="5be63-241">Office 2016 is installed using "Click-to-Run" or "C2R Installer".</span></span> <span data-ttu-id="5be63-242">La instalación de C2R descarga e instala todos los programas de Office.</span><span class="sxs-lookup"><span data-stu-id="5be63-242">The C2R installation downloads and installs all programs within Office.</span></span> <span data-ttu-id="5be63-243">En el caso de BAM, solo necesitamos Excel.</span><span class="sxs-lookup"><span data-stu-id="5be63-243">For BAM, we only need Excel.</span></span> <span data-ttu-id="5be63-244">Para solucionar este problema, descargue e instale la [Herramienta de implementación de Office 2016](https://www.microsoft.com/download/details.aspx?id=49117) para personalizar el instalador de C2R.</span><span class="sxs-lookup"><span data-stu-id="5be63-244">To work around this, download and install the [Office 2016 Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117) to customize the C2R installer.</span></span>

1. <span data-ttu-id="5be63-245">Descargue e instale la [Herramienta de implementación de Office 2016](https://www.microsoft.com/download/details.aspx?id=49117).</span><span class="sxs-lookup"><span data-stu-id="5be63-245">Download and install the [Office 2016 Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117).</span></span>
2. <span data-ttu-id="5be63-246">En la carpeta con los archivos de la Herramienta de implementación de Office 2016 que ha extraído, abra el archivo **configuration.xml** con un editor de texto, como Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="5be63-246">In the folder with the Office 2016 Deployment Tool files you extracted, open the **configuration.xml** file with a text editor, such as notepad.</span></span>
3. <span data-ttu-id="5be63-247">Reemplace la sección `<Configuration>` por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5be63-247">Replace the `<Configuration>` section with the following:</span></span>  

    ```
    <Configuration>
    <Add SourcePath="D:\" OfficeClientEdition="32">
    <Product ID="O365ProPlusRetail" >
      <Language ID="en-us" />
      <ExcludeApp ID="Access" />
      <ExcludeApp ID="Groove" />
      <ExcludeApp ID="InfoPath" />
      <ExcludeApp ID="Lync" />
      <ExcludeApp ID="OneDrive" />
      <ExcludeApp ID="OneNote" />
      <ExcludeApp ID="Outlook" />
      <ExcludeApp ID="PowerPoint" />
      <ExcludeApp ID="Project" />
      <ExcludeApp ID="Publisher" />
      <ExcludeApp ID="SharePointDesigner" />
      <ExcludeApp ID="Visio" />
      <ExcludeApp ID="Word" />
    </Product>
    </Add>
    </Configuration>
    ```
    
    <span data-ttu-id="5be63-248">Reemplace "SourcePath" por la ubicación del archivo ISO de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="5be63-248">Replace “SourcePath” with the location of your Office 2016 ISO file.</span></span>
4. <span data-ttu-id="5be63-249">En la carpeta con los archivos de la Herramienta de implementación de Office 2016, mantenga pulsada la tecla **Mayúsculas** y haga clic con el botón derecho en un área vacía de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="5be63-249">In the folder with the Office 2016 Deployment Tool files, hold down the **SHIFT** key, and right-click an empty area in the folder.</span></span> <span data-ttu-id="5be63-250">Seleccione **Abrir ventana de comandos aquí**.</span><span class="sxs-lookup"><span data-stu-id="5be63-250">Select **Open command window here**.</span></span> 
5. <span data-ttu-id="5be63-251">Para iniciar la instalación de Excel, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5be63-251">Start the Excel installation by entering the following:</span></span>  
  `setup.exe /configure configuration.xml`

    > [!TIP]
    > <span data-ttu-id="5be63-252">`setup.exe /download configuration.xml` descarga los archivos de instalación de Office necesarios.</span><span class="sxs-lookup"><span data-stu-id="5be63-252">`setup.exe /download configuration.xml` downloads the required office setup files.</span></span>
 
6. <span data-ttu-id="5be63-253">Seleccione Excel y continúe con la instalación.</span><span class="sxs-lookup"><span data-stu-id="5be63-253">Select Excel, and continue with the installation.</span></span> 
 
<span data-ttu-id="5be63-254">**CONSULTE TAMBIÉN**: [Opciones de configuración de la Herramienta de implementación de Office](https://technet.microsoft.com/library/jj219426.aspx) e [Instalar Office 2016 o 2013](https://support.office.com/article/Install-Office-on-your-PC-or-Mac-4414eaaf-0478-48be-9c42-23adc4716658).</span><span class="sxs-lookup"><span data-stu-id="5be63-254">**SEE ALSO** : [Configuration options for the Office Deployment Tool](https://technet.microsoft.com/library/jj219426.aspx) and [Install Office 2016 or 2013](https://support.office.com/article/Install-Office-on-your-PC-or-Mac-4414eaaf-0478-48be-9c42-23adc4716658)</span></span>

#### <a name="install-excel-2013"></a><span data-ttu-id="5be63-255">Instalar Excel 2013</span><span class="sxs-lookup"><span data-stu-id="5be63-255">Install Excel 2013</span></span>
1. <span data-ttu-id="5be63-256">Ejecute el programa de instalación de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="5be63-256">Run the Microsoft Office setup.</span></span>
2. <span data-ttu-id="5be63-257">Seleccione una **instalación personalizada** y seleccione Excel.</span><span class="sxs-lookup"><span data-stu-id="5be63-257">Select a **Custom Install**, and select Excel.</span></span>
3. <span data-ttu-id="5be63-258">Continúe con la instalación.</span><span class="sxs-lookup"><span data-stu-id="5be63-258">Continue with the installation.</span></span>   

## <a name="install-visual-c-redistributable-package"></a><span data-ttu-id="5be63-259">Instalar el paquete redistribuible de Visual C++</span><span class="sxs-lookup"><span data-stu-id="5be63-259">Install Visual C++ redistributable package</span></span>

<span data-ttu-id="5be63-260">Descargue e instale el [paquete redistribuible de Visual C++](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package).</span><span class="sxs-lookup"><span data-stu-id="5be63-260">Download and install the [Visual C++ redistributable package](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package).</span></span> <span data-ttu-id="5be63-261">Se requiere la versión de 2013, aunque se use Visual Studio 2015.</span><span class="sxs-lookup"><span data-stu-id="5be63-261">The 2013 version is required, even though Visual Studio 2015 is used.</span></span>

<span data-ttu-id="5be63-262">El [descargas de Visual C++](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads) enumera todas las versiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="5be63-262">The [Visual C++ downloads](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads) lists all the available versions.</span></span>

## <a name="install-visual-studio-2015-optional"></a><span data-ttu-id="5be63-263">Instalar Visual Studio 2015 (opcional)</span><span class="sxs-lookup"><span data-stu-id="5be63-263">Install Visual Studio 2015 (optional)</span></span>
<span data-ttu-id="5be63-264">BizTalk Server requiere Visual Studio para crear proyectos de BizTalk mediante las herramientas de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="5be63-264">BizTalk Server requires Visual Studio to create BizTalk projects using the development tools.</span></span> <span data-ttu-id="5be63-265">Si usa un servidor de ensayo o de producción o si no va a realizar ninguna tarea de desarrollo de BizTalk, omita esta sección.</span><span class="sxs-lookup"><span data-stu-id="5be63-265">If this is a staging or production server, or you're not doing any BizTalk development, then skip this section.</span></span>

<span data-ttu-id="5be63-266">Se recomienda la edición Visual Studio Enterprise, pero también se admiten las ediciones Professional y Community.</span><span class="sxs-lookup"><span data-stu-id="5be63-266">Visual Studio Enterprise Edition is recommended, but Professional and Community editions are also supported.</span></span> 

1. <span data-ttu-id="5be63-267">Ejecute el programa de instalación de Visual Studio como administrador.</span><span class="sxs-lookup"><span data-stu-id="5be63-267">Run the Visual Studio setup as Administrator.</span></span>
2. <span data-ttu-id="5be63-268">Seleccione una instalación **predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="5be63-268">Select a **Default** installation.</span></span> <span data-ttu-id="5be63-269">BizTalk Server no necesita ninguna característica opcional.</span><span class="sxs-lookup"><span data-stu-id="5be63-269">BizTalk Server does not require any of the optional features.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5be63-270">Si usa Visual Studio para algo más que proyectos de BizTalk, seleccione la instalación **personalizada** para instalar otras características.</span><span class="sxs-lookup"><span data-stu-id="5be63-270">If you use Visual Studio for more than BizTalk projects, then select the **Custom** installation to install other features.</span></span> <span data-ttu-id="5be63-271">Algunas de las características usadas con frecuencia incluyen Microsoft Web Developer Tools, Microsoft Office Developer Tools, herramientas de PowerShell para Visual Studio y herramientas de publicación ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="5be63-271">Some commonly-used features include Microsoft Web Developer Tools, Microsoft Office Developer Tools, PowerShell Tools for Visual Studio, and ClickOnce Publishing Tools.</span></span>
 
3. <span data-ttu-id="5be63-272">Continúe con la instalación y reinicie el equipo si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="5be63-272">Continue with the installation, and restart your computer if prompted.</span></span>

<span data-ttu-id="5be63-273">**CONSULTE TAMBIÉN**: [Instalar Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span><span class="sxs-lookup"><span data-stu-id="5be63-273">**SEE ALSO** : [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx)</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="5be63-274">Si instala Visual Studio antes de instalar BizTalk Server y después actualiza a Visual Studio Team Explorer, puede que sea necesario reparar la instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-274">If you install Visual Studio before installing BizTalk Server, and then upgrade to Visual Studio Team Explorer, you may need to repair your BizTalk Server installation.</span></span>
> - <span data-ttu-id="5be63-275">Visual Studio instala automáticamente Microsoft SQL Server Express, que BizTalk Server no usa.</span><span class="sxs-lookup"><span data-stu-id="5be63-275">Visual Studio automatically installs Microsoft SQL Server Express; which is not used by BizTalk Server.</span></span> <span data-ttu-id="5be63-276">Desinstale Microsoft SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="5be63-276">Uninstall Microsoft SQL Server Express.</span></span> <span data-ttu-id="5be63-277">También puede desinstalar Microsoft SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="5be63-277">You can also uninstall Microsoft SQL Server Compact.</span></span>  
> - <span data-ttu-id="5be63-278">Las herramientas de desarrollo de BizTalk Server se basan en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5be63-278">The BizTalk Server development tools are based on Visual Studio.</span></span> <span data-ttu-id="5be63-279">Como mínimo, debe instalar el componente Microsoft Visual C#® .NET antes de instalar el SDK y herramientas de desarrollo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-279">At a minimum, install the Microsoft Visual C#® .NET component before you install the BizTalk Server Developer Tools and SDK.</span></span>
> - <span data-ttu-id="5be63-280">El tiempo de ejecución de BizTalk Server necesita .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="5be63-280">The BizTalk Server runtime requires .NET Framework 4.6.</span></span> <span data-ttu-id="5be63-281">Si está instalado el adaptador de Windows Communication Foundation (WCF) o el Interceptor de WCF, .NET Framework 3.0 es necesario</span><span class="sxs-lookup"><span data-stu-id="5be63-281">If the Windows Communication Foundation (WCF) adapter or WCF Interceptor is installed, then .NET Framework 3.0 is required</span></span>

#### <a name="uninstall-sql-server-express"></a><span data-ttu-id="5be63-282">Desinstalar SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="5be63-282">Uninstall SQL Server Express</span></span>
1. <span data-ttu-id="5be63-283">En el menú Inicio, abra **Programas y características**.</span><span class="sxs-lookup"><span data-stu-id="5be63-283">In the Start menu, open **Programs and Features**.</span></span> <span data-ttu-id="5be63-284">O bien, abra el **Panel de control** y seleccione **Desinstalar un programa**.</span><span class="sxs-lookup"><span data-stu-id="5be63-284">Or, open the **Control Panel**, and select **Uninstall a program**.</span></span>
2. <span data-ttu-id="5be63-285">Desinstalación:</span><span class="sxs-lookup"><span data-stu-id="5be63-285">Uninstall:</span></span> 
    - <span data-ttu-id="5be63-286">Microsoft SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="5be63-286">Microsoft SQL Server 2014 Express LocalDb</span></span>
    - <span data-ttu-id="5be63-287">Microsoft SQL Server Compact 4.0 SP1 x64 ENU</span><span class="sxs-lookup"><span data-stu-id="5be63-287">Microsoft SQL Server Compact 4.0 SP1 x64 ENU</span></span>
    - <span data-ttu-id="5be63-288">Microsoft SQL Server 2016 LocalDB (SQL Server 2016 Express LocalDB)</span><span class="sxs-lookup"><span data-stu-id="5be63-288">Microsoft SQL Server 2016 LocalDB (SQL Server 2016 Express LocalDB)</span></span>
    
3. <span data-ttu-id="5be63-289">Continúe con la desinstalación y reinicie el equipo si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="5be63-289">Continue with the uninstall, and restart your computer if prompted.</span></span> 

## <a name="install-sql-server-2016"></a><span data-ttu-id="5be63-290">Instalar SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="5be63-290">Install SQL Server 2016</span></span>
<span data-ttu-id="5be63-291">BizTalk Server requiere SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-291">BizTalk Server requires SQL Server.</span></span> <span data-ttu-id="5be63-292">SQL Server se puede instalar en el mismo equipo que BizTalk o en un equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="5be63-292">SQL Server can be installed on the same computer as BizTalk, or on a different computer.</span></span> <span data-ttu-id="5be63-293">La mayoría de los entornos de producción instala BizTalk y SQL en servidores independientes.</span><span class="sxs-lookup"><span data-stu-id="5be63-293">Most production environments install BizTalk and SQL on separate servers.</span></span> 

> [!IMPORTANT]
> - <span data-ttu-id="5be63-294">No se recomienda o no se admite el uso de SQL Server Express Edition.</span><span class="sxs-lookup"><span data-stu-id="5be63-294">SQL Server Express Edition is not recommended or supported.</span></span> <span data-ttu-id="5be63-295">Esta edición no incluye ciertas características que necesita BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-295">The Express edition does not include certain features needed by BizTalk Server.</span></span>
> - <span data-ttu-id="5be63-296">BizTalk Server admite SQL Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5be63-296">BizTalk Server supports SQL Standard Edition.</span></span> <span data-ttu-id="5be63-297">Pero para usar la agregación en tiempo real de la Supervisión de la actividad económica (ATR de BAM), debe instalar SQL Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="5be63-297">However, to use Business Activity Monitoring real-time aggregation (BAM RTA), install SQL Server Enterprise Edition.</span></span> <span data-ttu-id="5be63-298">No se admite la agregación en tiempo real (ATR) de BAM en la versión Standard Edition de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-298">BAM real-time aggregation (RTA) is not supported in the Standard Edition of SQL Server.</span></span>
> - <span data-ttu-id="5be63-299">Para poder usar el SDK de BizTalk Server en su totalidad o implementar aplicaciones de BizTalk Server desde Visual Studio, instale las herramientas de desarrollo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-299">To fully use the BizTalk Server SDK or deploy BizTalk Server applications from a Visual Studio, install the SQL Server Development Tools.</span></span>
> - <span data-ttu-id="5be63-300">BizTalk Server admite todas las intercalaciones de SQL Server, tanto si distinguen mayúsculas y minúsculas como si no, excepto las intercalaciones binarias.</span><span class="sxs-lookup"><span data-stu-id="5be63-300">BizTalk Server supports all case-sensitive and case-insensitive SQL Server collations except for binary collations.</span></span> <span data-ttu-id="5be63-301">No se admiten intercalaciones binarias.</span><span class="sxs-lookup"><span data-stu-id="5be63-301">Binary collations are not supported.</span></span>

<span data-ttu-id="5be63-302">**Para obtener pasos de instalación específicos, consulte** [instalar SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup) o [instalar SQL Server 2014](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx).</span><span class="sxs-lookup"><span data-stu-id="5be63-302">**For specific install steps, see** [Install SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup) or [Install SQL Server 2014](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx).</span></span>

1. <span data-ttu-id="5be63-303">Inicie la instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-303">Start the SQL Server installation.</span></span> 
2. <span data-ttu-id="5be63-304">Durante la instalación de las características, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5be63-304">During the Feature setup, select the following:</span></span>
    - <span data-ttu-id="5be63-305">Servicios de Motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="5be63-305">Database Engine Services</span></span>
        - <span data-ttu-id="5be63-306">Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5be63-306">SQL Server Replication</span></span>
        - <span data-ttu-id="5be63-307">R Services (en bases de datos) (**opcional**; información en [SQL Server R Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services))</span><span class="sxs-lookup"><span data-stu-id="5be63-307">R Services (in-Database) (**optional**; info at [SQL Server R Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services))</span></span>
        - <span data-ttu-id="5be63-308">Extracciones de texto completo y semánticas de búsqueda</span><span class="sxs-lookup"><span data-stu-id="5be63-308">Full-Text and Semantic Extractions for Search</span></span>
    - <span data-ttu-id="5be63-309">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5be63-309">Analysis Services</span></span>
    - <span data-ttu-id="5be63-310">Reporting Services (nativo)</span><span class="sxs-lookup"><span data-stu-id="5be63-310">Reporting Services - Native</span></span>
    - <span data-ttu-id="5be63-311">Características compartidas</span><span class="sxs-lookup"><span data-stu-id="5be63-311">Shared Features</span></span>
        - <span data-ttu-id="5be63-312">Conectividad con las herramientas de cliente</span><span class="sxs-lookup"><span data-stu-id="5be63-312">Client Tools Connectivity</span></span>
        - <span data-ttu-id="5be63-313">Integration Services</span><span class="sxs-lookup"><span data-stu-id="5be63-313">Integration Services</span></span>

    > [!NOTE]
    > <span data-ttu-id="5be63-314">**SQL Server Data Tools** no se incluye en la instalación predeterminada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-314">**SQL Server Data Tools** is not included in the default installation of SQL Server.</span></span> <span data-ttu-id="5be63-315">No es necesario, pero se puede descargar en [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt).</span><span class="sxs-lookup"><span data-stu-id="5be63-315">It is not required, but can be downloaded at [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt).</span></span> <span data-ttu-id="5be63-316">Descargue [**SQL Server Management Studio (SSMS)**](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms), que funciona con todas las versiones compatibles de SQL Server, incluido Azure SQL Database.</span><span class="sxs-lookup"><span data-stu-id="5be63-316">Download [**SQL Server Management Studio (SSMS)**](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) that works with all supported versions of SQL Server, including Azure SQL Database.</span></span> 

3. <span data-ttu-id="5be63-317">Continúe con la instalación y reinicie el equipo si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="5be63-317">Continue with the installation, and restart the computer if prompted.</span></span>

## <a name="disable-shared-memory"></a><span data-ttu-id="5be63-318">Deshabilite la memoria compartida</span><span class="sxs-lookup"><span data-stu-id="5be63-318">Disable Shared Memory</span></span>

1. <span data-ttu-id="5be63-319">Abra el **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="5be63-319">Open **SQL Server Configuration Manager**.</span></span>
2. <span data-ttu-id="5be63-320">En el Administrador de configuración de SQL Server, expanda **configuración de red de SQL Server**y, a continuación, seleccione **protocolos para MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="5be63-320">In SQL Server Configuration Manager, expand **SQL Server Network Configuration**, and then select **Protocols for MSSQLSERVER**.</span></span>
3. <span data-ttu-id="5be63-321">Haga clic con el botón derecho en **Memoria compartida** y seleccione **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="5be63-321">Right-click **Shared Memory**, and then select **Disable**.</span></span>
4. <span data-ttu-id="5be63-322">Seleccione **Services de SQL Server**, haga clic en SQL **Server (MSSQLSERVER)**y, a continuación, seleccione **detener**.</span><span class="sxs-lookup"><span data-stu-id="5be63-322">Select **SQL Server Services**, right-click SQL **Server (MSSQLSERVER)**, and then select **Stop**.</span></span> <span data-ttu-id="5be63-323">Después de detener el servicio, haga clic en **SQL Server (MSSQLSERVER)**y, a continuación, seleccione **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="5be63-323">After the service has stopped, right-click **SQL Server (MSSQLSERVER)**, and then select **Start**.</span></span>
5. <span data-ttu-id="5be63-324">Cierre el **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="5be63-324">Close **SQL Server Configuration Manager**.</span></span>

<span data-ttu-id="5be63-325">Normalmente, el protocolo de memoria compartida solo afecta a los clientes (BizTalk Server) que están instalados en el mismo equipo que SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-325">Typically, the Shared Memory protocol only impacts clients (BizTalk Server) that are installed on the same computer as SQL Server.</span></span> <span data-ttu-id="5be63-326">Bajo determinadas condiciones de sobrecarga (como, por ejemplo, cuando los clientes obtienen acceso al servidor SQL Server desde el mismo equipo), el protocolo de memoria compartida de SQL Server puede reducir el rendimiento de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-326">Under certain stress conditions (such as clients accessing SQL Server from the same computer), the SQL Server Shared Memory protocol may lower BizTalk Server performance.</span></span> <span data-ttu-id="5be63-327">Al deshabilitar el protocolo de red de memoria compartida, resuelve esto.</span><span class="sxs-lookup"><span data-stu-id="5be63-327">Disabling the Shared Memory network protocol resolves this.</span></span>

> [!TIP]
> <span data-ttu-id="5be63-328">Si se produce un error en el Agente SQL Server iniciar después de deshabilitar la memoria compartida, a continuación, confirme [ODBC Driver 13.1 para SQL Server](https://www.microsoft.com/download/details.aspx?id=53339) está instalado.</span><span class="sxs-lookup"><span data-stu-id="5be63-328">If SQL Server Agent fails to start after disabling Shared Memory, then confirm [ODBC Driver 13.1 for SQL Server](https://www.microsoft.com/download/details.aspx?id=53339) is installed.</span></span>

## <a name="install-sql-xml-4"></a><span data-ttu-id="5be63-329">Instalar SQL XML 4</span><span class="sxs-lookup"><span data-stu-id="5be63-329">Install SQL XML 4</span></span>
<span data-ttu-id="5be63-330">Se requiere para el tiempo de ejecución de BizTalk Server, herramientas administrativas y BAM.</span><span class="sxs-lookup"><span data-stu-id="5be63-330">Required for BizTalk Server Runtime, Administrative Tools, and BAM.</span></span> 

<span data-ttu-id="5be63-331">Descargue e instale [SqlXml 4.0](https://www.microsoft.com/download/details.aspx?id=30403).</span><span class="sxs-lookup"><span data-stu-id="5be63-331">Download and install [SqlXml 4.0](https://www.microsoft.com/download/details.aspx?id=30403).</span></span>

## <a name="configure-sql-database-mail-optional"></a><span data-ttu-id="5be63-332">Configurar el correo electrónico de base de datos de SQL (opcional)</span><span class="sxs-lookup"><span data-stu-id="5be63-332">Configure SQL Database Mail (optional)</span></span>
<span data-ttu-id="5be63-333">Si usa alertas de BAM, BizTalk Server requiere correo electrónico de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-333">If you use BAM Alerts, BizTalk Server requires SQL Server Database Mail.</span></span> <span data-ttu-id="5be63-334">Si no usa las alertas de BAM, omita esta sección.</span><span class="sxs-lookup"><span data-stu-id="5be63-334">If you don't use BAM Alerts, then skip this section.</span></span> 

<span data-ttu-id="5be63-335">**CONSULTE TAMBIÉN**: más información sobre el [Correo electrónico de base de datos](https://docs.microsoft.com/sql/relational-databases/database-mail/database-mail).</span><span class="sxs-lookup"><span data-stu-id="5be63-335">**SEE ALSO** : More on [Database Mail](https://docs.microsoft.com/sql/relational-databases/database-mail/database-mail).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="5be63-336">Debe saber el nombre del servidor y el número de puerto TCP del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5be63-336">You need to know the server name and TCP port number for the SMTP Server.</span></span> <span data-ttu-id="5be63-337">Si instaló IIS y el servidor SMTP en el mismo equipo, use el servidor SMTP local.</span><span class="sxs-lookup"><span data-stu-id="5be63-337">If you installed IIS and SMTP Server on this same computer, then you use the local SMTP Server.</span></span> <span data-ttu-id="5be63-338">Si el servidor SMTP requiere autenticación, tenga preparados el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="5be63-338">If the SMTP server requires authentication, then have the user name and password ready.</span></span>
> - <span data-ttu-id="5be63-339">El portal de BAM y las alertas de BAM son características independientes.</span><span class="sxs-lookup"><span data-stu-id="5be63-339">The BAM portal and BAM Alerts are separate features.</span></span> <span data-ttu-id="5be63-340">Si usa las alertas de BAM, se requiere el Correo electrónico de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-340">If you are using BAM Alerts, then SQL Server Database Mail is required.</span></span> <span data-ttu-id="5be63-341">Si no usa las alertas de BAM, no se requiere el Correo electrónico de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5be63-341">If you are not using BAM Alerts, then SQL Server Database Mail is not required.</span></span>

<span data-ttu-id="5be63-342">**Para los pasos de configuración específicos, consulte**: configurar [correo electrónico de base de datos de SQL Server 2016](https://docs.microsoft.com/sql/relational-databases/database-mail/configure-database-mail) o [correo electrónico de base de datos de SQL Server 2014](https://msdn.microsoft.com/library/hh245116(v=sql.120).aspx).</span><span class="sxs-lookup"><span data-stu-id="5be63-342">**For specific configuration steps, see**: Configure [SQL Server 2016 Database Mail](https://docs.microsoft.com/sql/relational-databases/database-mail/configure-database-mail) or [SQL Server 2014 Database Mail](https://msdn.microsoft.com/library/hh245116(v=sql.120).aspx).</span></span>

   
<span data-ttu-id="5be63-343">Para enviar un correo electrónico de prueba:</span><span class="sxs-lookup"><span data-stu-id="5be63-343">To send a test email:</span></span> 
1.  <span data-ttu-id="5be63-344">Haga clic con el botón derecho en **Correo electrónico de base de datos** y seleccione **Enviar correo electrónico de prueba**.</span><span class="sxs-lookup"><span data-stu-id="5be63-344">Right-click **Database Mail**, and select **Send Test E-Mail**.</span></span> 
2.  <span data-ttu-id="5be63-345">Escriba una dirección de correo electrónico **Para:** y seleccione **Enviar correo electrónico de prueba**.</span><span class="sxs-lookup"><span data-stu-id="5be63-345">Enter a **To:** email address, and select **Send Test E-Mail**.</span></span>  
 
<span data-ttu-id="5be63-346">Si el destinatario **Para:** lo recibe, el Correo electrónico de base de datos está configurado.</span><span class="sxs-lookup"><span data-stu-id="5be63-346">If the **To:** recipient receives the email, then Database Mail is configured.</span></span> 

## <a name="install-winscp-optional"></a><span data-ttu-id="5be63-347">Instalar WinSCP (opcional)</span><span class="sxs-lookup"><span data-stu-id="5be63-347">Install WinSCP (optional)</span></span>
<span data-ttu-id="5be63-348">Requiere el adaptador de FTP.</span><span class="sxs-lookup"><span data-stu-id="5be63-348">Required by the FTP adapter.</span></span> <span data-ttu-id="5be63-349">Si no utiliza el adaptador de FTP, a continuación, omita esta sección.</span><span class="sxs-lookup"><span data-stu-id="5be63-349">If you don't use the FTP adapter, then skip this section.</span></span> 

<span data-ttu-id="5be63-350">Descargue e instale [WinSCP](http://winscp.net).</span><span class="sxs-lookup"><span data-stu-id="5be63-350">Download and install [WinSCP](http://winscp.net).</span></span> 

## <a name="next-step"></a><span data-ttu-id="5be63-351">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="5be63-351">Next step</span></span>
<span data-ttu-id="5be63-352">Instalar [BizTalk Server 2016](../install-and-config-guides/install-biztalk-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="5be63-352">Install [BizTalk Server 2016](../install-and-config-guides/install-biztalk-server-2016.md).</span></span>
