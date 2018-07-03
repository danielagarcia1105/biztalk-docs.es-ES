---
title: 'Apéndice D: crear el servidor SMTP | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7441ba9-a498-42ec-a04d-7f2731407373
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6c773935a52e58a4bc04b3f963d83d988bf78d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007085"
---
# <a name="appendix-d-create-the-smtp-server"></a><span data-ttu-id="2345b-102">Apéndice D: Crear el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="2345b-102">Appendix D: Create the SMTP Server</span></span>
<span data-ttu-id="2345b-103">Cree el servidor SMTP usado por Correo electrónico de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2345b-103">Create the SMTP Server used by SQL Server Database Mail.</span></span>  
  
<span data-ttu-id="2345b-104">Se requiere Correo electrónico de base de datos de SQL Server para configurar alertas de BAM cuando se usa alguna de las siguientes versiones de SQL:</span><span class="sxs-lookup"><span data-stu-id="2345b-104">SQL Server Database Mail is required to configure BAM Alerts when using any of the following SQL versions:</span></span> 

* [!INCLUDE[sqlserver2016_md](../includes/sqlserver2016-md.md)]
* [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]
* [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 
  
  <span data-ttu-id="2345b-105">Correo electrónico de base de datos de SQL Server usa un servidor SMTP para enviar las alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="2345b-105">SQL Server Database Mail uses an SMTP Server to send BAM Alerts.</span></span> <span data-ttu-id="2345b-106">El servidor SMTP se incluye con Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="2345b-106">SMTP Server is included with Internet Information Services (IIS).</span></span> <span data-ttu-id="2345b-107">SMTP se puede instalar en modo local o en el servidor BizTalk Server u otro servidor que tenga IIS instalado.</span><span class="sxs-lookup"><span data-stu-id="2345b-107">SMTP can be installed locally on the BizTalk Server or on another server with IIS installed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2345b-108">Normalmente, los sistemas operativos cliente como Windows 10, Windows 7, etc., no incluyen funcionalidades de servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2345b-108">Typically, client operating systems like Windows 10, Windows 7, and so on, do not include SMTP Server capabilities.</span></span> <span data-ttu-id="2345b-109">Puede conectarse a un servidor SMTP en un servidor Windows Server con la característica *Correo electrónico SMTP* de IIS.</span><span class="sxs-lookup"><span data-stu-id="2345b-109">You can connect to an existing SMTP Server on a Windows Server using the *SMTP E-mail* feature within IIS.</span></span> <span data-ttu-id="2345b-110">La característica *Correo electrónico SMTP* NO es un servidor SMTP, que es necesario para Correo electrónico de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2345b-110">The *SMTP E-mail* feature is NOT an SMTP Server, which is required for SQL Server Database Mail.</span></span> <span data-ttu-id="2345b-111">Por tanto, en este tema no se incluyen los pasos para instalar y configurar un servidor SMTP en sistemas operativos cliente.</span><span class="sxs-lookup"><span data-stu-id="2345b-111">As a result, this topic does not include the steps to install and configure an SMTP Server on client operating systems.</span></span>  

## <a name="install-and-configure-the-smtp-server"></a><span data-ttu-id="2345b-112">Instalar y configurar el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="2345b-112">Install and configure the SMTP server</span></span>  
  
<span data-ttu-id="2345b-113">Estos pasos se aplican a:</span><span class="sxs-lookup"><span data-stu-id="2345b-113">These steps apply to:</span></span>

* <span data-ttu-id="2345b-114">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="2345b-114">Windows Server 2016</span></span>
* <span data-ttu-id="2345b-115">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2345b-115">Windows Server 2012 R2</span></span>
* <span data-ttu-id="2345b-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="2345b-116">Windows Server 2012</span></span>
  
### <a name="install-smtp-server"></a><span data-ttu-id="2345b-117">Instalar el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="2345b-117">Install SMTP Server</span></span>  
   
1.  <span data-ttu-id="2345b-118">En **Administrador del servidor**, seleccione **Panel** en el panel de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="2345b-118">In **Server Manager**, select **Dashboard** in the left pane.</span></span>  
  
3.  <span data-ttu-id="2345b-119">Seleccione **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="2345b-119">Select **Add roles and features**.</span></span> <span data-ttu-id="2345b-120">También se puede abrir **Agregar roles y características** desde el menú **Administrar** de la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="2345b-120">**Add Roles and Features** can also be opened from the **Manage** menu in the top right-hand corner.</span></span>  
  
4.  <span data-ttu-id="2345b-121">En **Antes de comenzar**, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2345b-121">In **Before You Begin**, select **Next**.</span></span>  
  
5.  <span data-ttu-id="2345b-122">Seleccione **Instalación basada en características o en roles** y, después, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2345b-122">Select **Role-based or feature-based installation**, and select **Next**.</span></span>  
  
6.  <span data-ttu-id="2345b-123">Seleccione **Seleccionar un servidor del grupo de servidores**, el servidor deseado y, después, **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2345b-123">Select **Select a server from the server pool**, select the desired server, and select **Next**.</span></span> <span data-ttu-id="2345b-124">En la ventana **Selección del servidor** se muestra una lista de los servidores que se han agregado con la opción **Agregar servidor** en el **Administrador del servidor**.</span><span class="sxs-lookup"><span data-stu-id="2345b-124">The **Server Selection** window lists the servers that have been added using **Add Server** in **Server Manager**.</span></span> <span data-ttu-id="2345b-125">De forma predeterminada, se selecciona el servidor local.</span><span class="sxs-lookup"><span data-stu-id="2345b-125">By default, it selects the local server.</span></span>  
  
7.  <span data-ttu-id="2345b-126">En **Roles del servidor**, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2345b-126">In **Server Roles**, select **Next**.</span></span>  
  
8.  <span data-ttu-id="2345b-127">En **Características**, active **Servidor SMTP**.</span><span class="sxs-lookup"><span data-stu-id="2345b-127">In **Features**, check **SMTP Server**.</span></span> <span data-ttu-id="2345b-128">Si el sistema se lo pide, seleccione **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="2345b-128">If prompted, select **Add Features**.</span></span> <span data-ttu-id="2345b-129">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2345b-129">Select **Next**.</span></span>  
  
9. <span data-ttu-id="2345b-130">En **Confirmación**, seleccione **Reiniciar automáticamente el servidor de destino en caso necesario** y, después, seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-130">In **Confirmation**, select **Restart the destination server automatically if required**, and select **Install**.</span></span> <span data-ttu-id="2345b-131">Cuando haya finalizado, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-131">When complete, select **Close**.</span></span>  

### <a name="configure-the-smtp-server"></a><span data-ttu-id="2345b-132">Configurar el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="2345b-132">Configure the SMTP Server</span></span>  
 <span data-ttu-id="2345b-133">Siga estos pasos para configurar el servidor virtual SMTP con el Administrador de IIS 6.0:</span><span class="sxs-lookup"><span data-stu-id="2345b-133">The following steps configure the SMTP Virtual Server using the IIS 6.0 Manager:</span></span>  
  
1.  <span data-ttu-id="2345b-134">Abra el Administrador de IIS. Para ello, vaya a Inicio, busque **inetmgr6.exe** y ábralo.</span><span class="sxs-lookup"><span data-stu-id="2345b-134">Open the IIS Manager: In Start, search for **inetmgr6.exe**, and open it.</span></span>  
  
2.  <span data-ttu-id="2345b-135">Expanda el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="2345b-135">Expand the computer name.</span></span> <span data-ttu-id="2345b-136">Haga clic con el botón derecho en **[Servidor virtual SMTP 1]** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2345b-136">Right-click **[SMTP Virtual Server #1]**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="2345b-137">En la pestaña **Acceso**, haga clic en el botón **Retransmisión**.</span><span class="sxs-lookup"><span data-stu-id="2345b-137">In the **Access** tab, select the **Relay** button.</span></span>  
  
4.  <span data-ttu-id="2345b-138">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-138">Select **Add**.</span></span> <span data-ttu-id="2345b-139">Para **Un único equipo**, escriba `127.0.0.1` y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-139">For **Single Computer**, enter `127.0.0.1`, and select **OK**.</span></span>  
  
     <span data-ttu-id="2345b-140">Al agregar 127.0.0.1, se permite que el servidor local envíe mensajes desde este servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2345b-140">By adding 127.0.0.1, we are allowing the local server to send messages from this SMTP Server.</span></span> <span data-ttu-id="2345b-141">Si quiere que otros equipos envíen mensajes desde este servidor SMTP, escriba sus direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="2345b-141">If you want additional computers to send messages from this SMTP server, enter their IP addresses.</span></span>  
  
5.  <span data-ttu-id="2345b-142">En la pestaña **Entrega**, seleccione **Seguridad de salida**.</span><span class="sxs-lookup"><span data-stu-id="2345b-142">In the **Delivery** tab, select **Outbound Security**.</span></span> <span data-ttu-id="2345b-143">Elija entre las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2345b-143">Choose from the following:</span></span>  
  
     <span data-ttu-id="2345b-144">**Acceso anónimo**: no se requiere nombre de cuenta ni contraseña.</span><span class="sxs-lookup"><span data-stu-id="2345b-144">**Anonymous access**: An account name or password is not required.</span></span> <span data-ttu-id="2345b-145">Esta opción deshabilita la autenticación para el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2345b-145">This option disables authentication for the SMTP Server.</span></span>  
  
     <span data-ttu-id="2345b-146">**Autenticación básica**: el nombre de cuenta y la contraseña del servidor al que se va a conectar se envían sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="2345b-146">**Basic authentication**: The account name and password of the server that you are connecting to are sent as clear text.</span></span> <span data-ttu-id="2345b-147">La cuenta que especifique transmite los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2345b-147">This account you enter transmits the e-mails.</span></span> <span data-ttu-id="2345b-148">Se puede elegir autenticación básica cuando se envía correo electrónico a una cuenta personal o a una cuenta de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2345b-148">Basic Authentication can be selected when sending e-mail to a personal account or an Exchange account.</span></span> <span data-ttu-id="2345b-149">Puesto que las credenciales se pasan como texto sin cifrar, se recomienda habilitar **Cifrado TLS**.</span><span class="sxs-lookup"><span data-stu-id="2345b-149">Because the credentials are passed in clear text, it is recommended to enable **TLS encryption**.</span></span>  
  
     <span data-ttu-id="2345b-150">**Autenticación de Windows integrada**: se usan el nombre y la contraseña de la cuenta de Windows para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="2345b-150">**Integrated Windows Authentication**: The Windows domain account name and password are used to authenticate.</span></span> <span data-ttu-id="2345b-151">La cuenta que especifique transmite los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2345b-151">The account you enter transmits the e-mails.</span></span>  
  
     <span data-ttu-id="2345b-152">**Cifrado TLS**: TLS protege la conexión de forma similar a SSL.</span><span class="sxs-lookup"><span data-stu-id="2345b-152">**TLS encryption**: Similar to SSL, TLS secures the connection.</span></span> <span data-ttu-id="2345b-153">Requiere un certificado de servidor SSL válido instalado en este servidor.</span><span class="sxs-lookup"><span data-stu-id="2345b-153">Requires a valid SSL server certificate installed on this server.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="2345b-154">Para probar la funcionalidad SMTP principal con una cuenta de correo electrónico personal, incluida una cuenta de Exchange, seleccione **Acceso anónimo**.</span><span class="sxs-lookup"><span data-stu-id="2345b-154">To test core SMTP functionality with a personal e-mail account, including an Exchange account, select **Anonymous access**.</span></span> <span data-ttu-id="2345b-155">Cuando se selecciona Autenticación básica, SMTP usa el comando AUTH.</span><span class="sxs-lookup"><span data-stu-id="2345b-155">When Basic authentication is selected, SMTP uses the AUTH command.</span></span> <span data-ttu-id="2345b-156">Algunos proveedores de correo electrónico pueden dar error debido al comando AUTH.</span><span class="sxs-lookup"><span data-stu-id="2345b-156">Some e-mail providers may fail because of the AUTH command.</span></span> <span data-ttu-id="2345b-157">Si AUTH da error, es probable que se registre un error en los registros de eventos de Windows en el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2345b-157">If the AUTH command fails, an error may be logged in the Windows event logs on the SMTP Server.</span></span>  
  
6.  <span data-ttu-id="2345b-158">En la pestaña **Entrega**, seleccione **Conexiones salientes**.</span><span class="sxs-lookup"><span data-stu-id="2345b-158">In the **Delivery** tab, select **Outbound connections**.</span></span> <span data-ttu-id="2345b-159">De forma predeterminada, el puerto TCP es el 25.</span><span class="sxs-lookup"><span data-stu-id="2345b-159">By default, the TCP Port is 25.</span></span> <span data-ttu-id="2345b-160">Se puede especificar otro puerto si está abierto en el firewall.</span><span class="sxs-lookup"><span data-stu-id="2345b-160">A different port can be entered if it is open within your firewall.</span></span> <span data-ttu-id="2345b-161">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-161">Select **OK**.</span></span>  
  
7.  <span data-ttu-id="2345b-162">En la pestaña **Entrega**, seleccione **Avanzada**.</span><span class="sxs-lookup"><span data-stu-id="2345b-162">In the **Delivery** tab, select **Advanced**.</span></span> <span data-ttu-id="2345b-163">De forma predeterminada, aparece el nombre del servidor local en **Nombre de dominio completo**.</span><span class="sxs-lookup"><span data-stu-id="2345b-163">By default, the **Fully Qualified Domain Name** of the local server is listed.</span></span> <span data-ttu-id="2345b-164">Según el proveedor de Internet, el cuadro de la propiedad **Host inteligente** puede estar vacío.</span><span class="sxs-lookup"><span data-stu-id="2345b-164">Depending on the internet provider, the **Smart Host** property can remain empty.</span></span> <span data-ttu-id="2345b-165">Puede ser necesario ponerse en contacto con el proveedor de Internet para confirmar si es necesario un host inteligente.</span><span class="sxs-lookup"><span data-stu-id="2345b-165">You may need to contact the internet provider to confirm if a Smart Host is required.</span></span> <span data-ttu-id="2345b-166">En caso contrario, quizá pueda especificar smtp.*ProveedorDeCorreo*.com.</span><span class="sxs-lookup"><span data-stu-id="2345b-166">Otherwise, you may be able to enter smtp.*EMailProvider*.com.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2345b-167">Un **host inteligente** es un servidor dedicado que los servidores Exchange usan para enrutar todos los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="2345b-167">A **Smart Host**, also known as a relay host, is a dedicated server used by an Exchange Server to route all outgoing messages.</span></span> <span data-ttu-id="2345b-168">Cuando el **host inteligente** recibe los mensajes, los reenvía a un dominio remoto.</span><span class="sxs-lookup"><span data-stu-id="2345b-168">When the **Smart Host** receives the messages, the **Smart Host** forwards the messages to a remote domain.</span></span> <span data-ttu-id="2345b-169">El objetivo de un **host inteligente** es mejorar el rendimiento de un servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="2345b-169">The goal of a **Smart Host** is to improve performance of an Exchange Server.</span></span> <span data-ttu-id="2345b-170">El servidor Exchange Server solo transmite al host inteligente, en lugar de contactar repetidamente al dominio remoto hasta que se establece una conexión.</span><span class="sxs-lookup"><span data-stu-id="2345b-170">The Exchange Server only transmits to the smart host; instead of repeatedly contacting the remote domain until a connection is made.</span></span>  
  
8.  <span data-ttu-id="2345b-171">Seleccione **Aceptar** para cerrar todas las ventanas.</span><span class="sxs-lookup"><span data-stu-id="2345b-171">Select **OK** to close all windows.</span></span>  
  
9. <span data-ttu-id="2345b-172">Reinicie el servidor SMTP. Para ello, haga clic con el botón derecho en **[Servidor virtual SMTP 1]**, seleccione **Detener** y, después, seleccione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-172">Restart the SMTP Server: Right-click **[SMTP Virtual Server #1]**, select **Stop**, and then select **Start**.</span></span> <span data-ttu-id="2345b-173">Es necesario reiniciar el equipo para aplicar la configuración del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2345b-173">A restart is needed to apply the SMTP Server settings.</span></span> 

  
## <a name="windows-server-2008-r2-install-and-configure-smtp-server"></a><span data-ttu-id="2345b-174">Windows Server 2008 R2: instalar y configurar el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="2345b-174">Windows Server 2008 R2: Install and Configure SMTP Server</span></span>  
  
### <a name="install-smtp-server"></a><span data-ttu-id="2345b-175">Instalar el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="2345b-175">Install SMTP Server</span></span>  
 <span data-ttu-id="2345b-176">Siga estos pasos para instalar la característica Servidor SMTP:</span><span class="sxs-lookup"><span data-stu-id="2345b-176">The following steps install the SMTP Server feature:</span></span>  
  
1.  <span data-ttu-id="2345b-177">En **Administrador del servidor**, seleccione **Características** y, después, seleccione **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="2345b-177">In **Server Manager**, select **Features**, and select **Add Features**.</span></span>  
  
3.  <span data-ttu-id="2345b-178">En **Agregar características**, seleccione **Servidor SMTP**.</span><span class="sxs-lookup"><span data-stu-id="2345b-178">In **Add Features**, select **SMTP Server**.</span></span> <span data-ttu-id="2345b-179">Si el sistema se lo pide, seleccione **Agregar servicios de rol requeridos** y, después, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2345b-179">If prompted, select **Add Required Role Services**, and select **Next**.</span></span>  
  
4.  <span data-ttu-id="2345b-180">Para continuar con la instalación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2345b-180">Continue with the installation by selecting **Next**.</span></span>  
  
5.  <span data-ttu-id="2345b-181">En la ventana **Confirmar selecciones de instalación**, seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-181">In the **Confirm Installation Selections** window, select **Install**.</span></span> <span data-ttu-id="2345b-182">Cuando haya finalizado, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-182">When complete, select **Close**.</span></span>  
  
### <a name="configure-the-smtp-server"></a><span data-ttu-id="2345b-183">Configurar el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="2345b-183">Configure the SMTP Server</span></span>  
 <span data-ttu-id="2345b-184">Siga estos pasos para configurar el servidor virtual SMTP con el Administrador de IIS 6.0:</span><span class="sxs-lookup"><span data-stu-id="2345b-184">The following steps configure the SMTP Virtual Server using the IIS 6.0 Manager:</span></span>  
  
1.  <span data-ttu-id="2345b-185">Abra el Administrador de IIS 6.0. Para ello, en **Iniciar**, busque **IIS** y seleccione **Administrador de Internet Information Services (IIS) 6.0**.</span><span class="sxs-lookup"><span data-stu-id="2345b-185">Open the IIS 6.0 Manager: In **Start**, search for **IIS**, and select **Internet Information Services (IIS) 6.0 Manager**.</span></span>  
  
2.  <span data-ttu-id="2345b-186">Expanda el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="2345b-186">Expand the computer name.</span></span> <span data-ttu-id="2345b-187">Haga clic con el botón derecho en **[Servidor virtual SMTP 1]** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2345b-187">Right-click **[SMTP Virtual Server #1]**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="2345b-188">En la pestaña **Acceso**, haga clic en el botón **Retransmisión**.</span><span class="sxs-lookup"><span data-stu-id="2345b-188">In the **Access** tab, select the **Relay** button.</span></span>  
  
4.  <span data-ttu-id="2345b-189">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-189">Select **Add**.</span></span> <span data-ttu-id="2345b-190">Para **Un único equipo**, escriba `127.0.0.1` y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-190">For **Single Computer**, enter `127.0.0.1`, and select **OK**.</span></span>  
  
     <span data-ttu-id="2345b-191">Al agregar 127.0.0.1, se permite que el servidor local envíe mensajes desde este servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2345b-191">By adding 127.0.0.1, we are allowing the local server to send messages from this SMTP Server.</span></span> <span data-ttu-id="2345b-192">Si quiere que otros equipos envíen mensajes desde este servidor SMTP, escriba sus direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="2345b-192">If you want additional computers to send messages from this SMTP server, enter their IP addresses.</span></span>  
  
5.  <span data-ttu-id="2345b-193">En la pestaña **Entrega**, seleccione **Seguridad de salida**.</span><span class="sxs-lookup"><span data-stu-id="2345b-193">In the **Delivery** tab, select **Outbound Security**.</span></span> <span data-ttu-id="2345b-194">Elija entre las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2345b-194">Choose from the following:</span></span>  
  
     <span data-ttu-id="2345b-195">**Acceso anónimo**: no se requiere nombre de cuenta ni contraseña.</span><span class="sxs-lookup"><span data-stu-id="2345b-195">**Anonymous access**: An account name or password is not required.</span></span> <span data-ttu-id="2345b-196">Esta opción deshabilita la autenticación para el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2345b-196">This option disables authentication for the SMTP Server.</span></span>  
  
     <span data-ttu-id="2345b-197">**Autenticación básica**: el nombre de cuenta y la contraseña del servidor al que se va a conectar se envían sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="2345b-197">**Basic authentication**: The account name and password of the server that you are connecting to are sent as clear text.</span></span> <span data-ttu-id="2345b-198">Se puede elegir autenticación básica cuando se envía correo electrónico a una cuenta personal o a una cuenta de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2345b-198">Basic Authentication can be selected when sending e-mail to a personal account or an Exchange account.</span></span> <span data-ttu-id="2345b-199">Puesto que las credenciales se pasan como texto sin cifrar, se recomienda habilitar **Cifrado TLS**.</span><span class="sxs-lookup"><span data-stu-id="2345b-199">Because the credentials are passed in clear text, it is recommended to enable **TLS encryption**.</span></span>  
  
     <span data-ttu-id="2345b-200">**Autenticación de Windows integrada**: se usan el nombre y la contraseña de la cuenta de Windows para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="2345b-200">**Integrated Windows Authentication**: The Windows domain account name and password are used to authenticate.</span></span> <span data-ttu-id="2345b-201">La cuenta que especifique transmite los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2345b-201">The account you enter transmits the e-mails.</span></span>  
  
     <span data-ttu-id="2345b-202">**Cifrado TLS**: TLS protege la conexión de forma similar a SSL.</span><span class="sxs-lookup"><span data-stu-id="2345b-202">**TLS encryption**: Similar to SSL, TLS secures the connection.</span></span> <span data-ttu-id="2345b-203">Requiere un certificado de servidor SSL válido instalado en este servidor.</span><span class="sxs-lookup"><span data-stu-id="2345b-203">Requires a valid SSL server certificate installed on this server.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="2345b-204">Para probar la funcionalidad SMTP principal con una cuenta de correo electrónico personal, incluida una cuenta de Exchange, seleccione **Acceso anónimo**.</span><span class="sxs-lookup"><span data-stu-id="2345b-204">To test core SMTP functionality with a personal e-mail account, including an Exchange account, select **Anonymous access**.</span></span> <span data-ttu-id="2345b-205">Cuando se selecciona Autenticación básica, SMTP usa el comando AUTH.</span><span class="sxs-lookup"><span data-stu-id="2345b-205">When Basic authentication is selected, SMTP uses the AUTH command.</span></span> <span data-ttu-id="2345b-206">Algunos proveedores de correo electrónico pueden dar error debido al comando AUTH.</span><span class="sxs-lookup"><span data-stu-id="2345b-206">Some e-mail providers may fail because of the AUTH command.</span></span> <span data-ttu-id="2345b-207">Si AUTH da error, es probable que se registre un error en los registros de eventos de Windows en el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2345b-207">If the AUTH command fails, an error may be logged in the Windows event logs on the SMTP Server.</span></span>  
  
6.  <span data-ttu-id="2345b-208">En la pestaña **Entrega**, seleccione **Conexiones salientes**.</span><span class="sxs-lookup"><span data-stu-id="2345b-208">In the **Delivery** tab, select **Outbound connections**.</span></span> <span data-ttu-id="2345b-209">De forma predeterminada, el puerto TCP es el 25.</span><span class="sxs-lookup"><span data-stu-id="2345b-209">By default, the TCP Port is 25.</span></span> <span data-ttu-id="2345b-210">Se puede especificar otro puerto si está abierto en el firewall.</span><span class="sxs-lookup"><span data-stu-id="2345b-210">A different port can be entered if it is open within your firewall.</span></span> <span data-ttu-id="2345b-211">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-211">Select **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="2345b-212">El puerto TCP se puede usar para conexiones entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="2345b-212">The TCP Port can be used for Inbound connections and Outbound connections.</span></span>  
  
7.  <span data-ttu-id="2345b-213">En la pestaña **Entrega**, seleccione **Avanzada**.</span><span class="sxs-lookup"><span data-stu-id="2345b-213">In the **Delivery** tab, select **Advanced**.</span></span> <span data-ttu-id="2345b-214">De forma predeterminada, aparece el nombre del servidor local en **Nombre de dominio completo**.</span><span class="sxs-lookup"><span data-stu-id="2345b-214">By default, the **Fully Qualified Domain Name** of the local server is listed.</span></span> <span data-ttu-id="2345b-215">Según el proveedor de Internet, el cuadro de la propiedad **Host inteligente** puede estar vacío.</span><span class="sxs-lookup"><span data-stu-id="2345b-215">Depending on the internet provider, the **Smart Host** property can remain empty.</span></span> <span data-ttu-id="2345b-216">Puede ser necesario ponerse en contacto con el proveedor de Internet para confirmar si es necesario un host inteligente.</span><span class="sxs-lookup"><span data-stu-id="2345b-216">You may need to contact the internet provider to confirm if a Smart Host is required.</span></span> <span data-ttu-id="2345b-217">En caso contrario, quizá pueda especificar smtp.*ProveedorDeCorreo*.com.</span><span class="sxs-lookup"><span data-stu-id="2345b-217">Otherwise, you may be able to enter smtp.*EMailProvider*.com.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2345b-218">Un **host inteligente** es un servidor dedicado que los servidores Exchange usan para enrutar todos los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="2345b-218">A **Smart Host**, also known as a relay host, is a dedicated server used by an Exchange Server to route all outgoing messages.</span></span> <span data-ttu-id="2345b-219">Cuando el **host inteligente** recibe los mensajes, los reenvía a un dominio remoto.</span><span class="sxs-lookup"><span data-stu-id="2345b-219">When the **Smart Host** receives the messages, the **Smart Host** forwards the messages to a remote domain.</span></span> <span data-ttu-id="2345b-220">El objetivo de un **host inteligente** es mejorar el rendimiento de un servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="2345b-220">The goal of a **Smart Host** is to improve performance of an Exchange Server.</span></span> <span data-ttu-id="2345b-221">El servidor Exchange Server solo transmite al host inteligente, en lugar de contactar repetidamente al dominio remoto hasta que se establece una conexión.</span><span class="sxs-lookup"><span data-stu-id="2345b-221">The Exchange Server only transmits to the smart host; instead of repeatedly contacting the remote domain until a connection is made.</span></span>  
  
8.  <span data-ttu-id="2345b-222">Seleccione **Aceptar** para cerrar todas las ventanas.</span><span class="sxs-lookup"><span data-stu-id="2345b-222">Select **OK** to close all windows.</span></span>  
  
9. <span data-ttu-id="2345b-223">Es necesario reiniciar el equipo para aplicar la configuración del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2345b-223">A restart is needed to apply the SMTP Server settings.</span></span> <span data-ttu-id="2345b-224">Para reiniciar el servidor SMTP, haga clic con el botón derecho en **[Servidor virtual SMTP 1]**, seleccione **Detener** y, después, seleccione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="2345b-224">To restart the SMTP Server: Right-click **[SMTP Virtual Server #1]**, select **Stop**, and then select **Start**.</span></span>  
  
  
## <a name="test-the-smtp-server"></a><span data-ttu-id="2345b-225">Probar el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="2345b-225">Test the SMTP Server</span></span>  
 <span data-ttu-id="2345b-226">Para probar la configuración del servidor SMTP, se puede usar Telnet.</span><span class="sxs-lookup"><span data-stu-id="2345b-226">Telnet can be used to test the SMTP Server configuration.</span></span> <span data-ttu-id="2345b-227">En los pasos siguientes, se envía un mensaje mediante el servidor SMTP configurado a una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2345b-227">The following steps send a message using your configured SMTP Server to an e-mail address.</span></span> <span data-ttu-id="2345b-228">[http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) proporciona descripciones de los comandos de telnet.</span><span class="sxs-lookup"><span data-stu-id="2345b-228">[http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) provides descriptions of the telnet commands.</span></span>  
  
1. <span data-ttu-id="2345b-229">Abra una ventana de comandos como administrador.</span><span class="sxs-lookup"><span data-stu-id="2345b-229">Open a command window as Administrator.</span></span>
  
2. <span data-ttu-id="2345b-230">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="2345b-230">In the command prompt, type:</span></span>  
  
    `telnet localhost 25`  
  
    <span data-ttu-id="2345b-231">Si Telnet no está instalado, escriba lo siguiente para instalarlo:</span><span class="sxs-lookup"><span data-stu-id="2345b-231">If telnet is not installed, install it by typing:</span></span>  
  
    `pkgmgr /iu:"TelnetClient"`  
  
3. <span data-ttu-id="2345b-232">Escriba lo siguiente para iniciar la comunicación:</span><span class="sxs-lookup"><span data-stu-id="2345b-232">Start communication by typing:</span></span>  
  
    `EHLO server`  
  
4. <span data-ttu-id="2345b-233">Escriba la dirección del remitente:</span><span class="sxs-lookup"><span data-stu-id="2345b-233">Enter the Mail From address:</span></span>  
  
    `MAIL FROM: *YourEmailAddress*@*YourProvider*.com`  
  
    <span data-ttu-id="2345b-234">Por ejemplo, escriba:</span><span class="sxs-lookup"><span data-stu-id="2345b-234">For example, enter:</span></span>  
  
    `MAIL FROM: EmailAddress@outlook.com`  
  
5. <span data-ttu-id="2345b-235">Escriba la dirección del destinatario:</span><span class="sxs-lookup"><span data-stu-id="2345b-235">Enter the Mail To address:</span></span>  
  
    `RCPT TO: *YourEmailAddress*@*YourProvider*.com`  
  
    <span data-ttu-id="2345b-236">Por ejemplo, escriba:</span><span class="sxs-lookup"><span data-stu-id="2345b-236">For example, enter:</span></span>  
  
    `RCPT TO: EmailAddress@outlook.com`  
  
6. <span data-ttu-id="2345b-237">Escriba lo siguiente para indicarle al servidor SMTP que está listo para enviar datos:</span><span class="sxs-lookup"><span data-stu-id="2345b-237">Tell the SMTP Server you are ready to send data by typing:</span></span>  
  
    `DATA`  
  
7. <span data-ttu-id="2345b-238">Escriba el asunto:</span><span class="sxs-lookup"><span data-stu-id="2345b-238">Enter the Subject by typing:</span></span>  
  
    `Subject: Test Message`  
  
8. <span data-ttu-id="2345b-239">Presione Entrar dos veces.</span><span class="sxs-lookup"><span data-stu-id="2345b-239">Hit Enter twice.</span></span>  
  
9. <span data-ttu-id="2345b-240">Escriba el cuerpo del mensaje:</span><span class="sxs-lookup"><span data-stu-id="2345b-240">Enter the message body by typing:</span></span>  
  
     `This is the message body of the test message.`  
  
10. <span data-ttu-id="2345b-241">Presione Entrar, escriba un punto (.) y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="2345b-241">Hit Enter, type a period (.), and hit Enter.</span></span>  
  
    <span data-ttu-id="2345b-242">Consulte la dirección RCPT TO para ver si ha llegado el mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2345b-242">Check the RCPT TO address for the e-mail message.</span></span> <span data-ttu-id="2345b-243">Si no se ha entregado el mensaje (compruebe la bandeja de entrada y la de correo no deseado), significa que el mensaje no se envió correctamente y está en la carpeta de la cola SMTP (C:\inetpub\mailroot\Queue).</span><span class="sxs-lookup"><span data-stu-id="2345b-243">If the e-mail is not delivered (Check your Inbox and Spam folder), then the message was not successfully sent, and may reside in the SMTP Queue folder (C:\inetpub\mailroot\Queue).</span></span>  
  