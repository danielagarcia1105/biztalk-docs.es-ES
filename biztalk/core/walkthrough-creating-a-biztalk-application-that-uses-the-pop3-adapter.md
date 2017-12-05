---
title: "Tutorial: Crear una aplicación de BizTalk que utiliza el adaptador de POP3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorials, POP3 adapters
- configuring [POP3 adapters], mailboxes
- configuring [POP3 adapters], tutorials
- POP3 adapters, mailboxes
- POP3 adapters, tutorials
- configuring [POP3 adapters], Outlook Express
ms.assetid: b44c3b1d-7b4f-425c-831a-1ce5f6379595
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e677a4fb68ad4f6991585c191c8065a60b3fc337
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter"></a><span data-ttu-id="9550e-102">Tutorial: Crear una aplicación de BizTalk que usa el adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="9550e-102">Walkthrough: Creating a BizTalk Application That Uses the POP3 Adapter</span></span>
<span data-ttu-id="9550e-103">Esta sección muestra cómo crear una aplicación sencilla de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el adaptador de POP3.</span><span class="sxs-lookup"><span data-stu-id="9550e-103">This section takes you through creating a simple Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application using the POP3 adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9550e-104">La aplicación supone que tiene acceso al equipo que ejecuta Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] con los servicios de correo electrónico instalados y configurados.</span><span class="sxs-lookup"><span data-stu-id="9550e-104">The application assumes that you have access to a computer running Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] with Email Services installed and configured.</span></span> <span data-ttu-id="9550e-105">Para obtener información sobre la configuración de [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] con los servicios de correo electrónico, consulte la ayuda de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9550e-105">For information about configuring [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] with Email Services see Windows Server Help.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9550e-106">En este ejemplo, se usa Microsoft Outlook Express como cliente de correo electrónico y [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] se usan como servidor de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9550e-106">In this example Microsoft Outlook Express is used as the e-mail client and [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] is used as the e-mail server.</span></span> <span data-ttu-id="9550e-107">Sin embargo, para este escenario se podría utilizar cualquier cliente de correo electrónico POP3 y servidor POP3 que cumpla con RFC.</span><span class="sxs-lookup"><span data-stu-id="9550e-107">However, any POP3 e-mail client and RFC-compliant POP3 server could be used for this scenario.</span></span>  
  
 <span data-ttu-id="9550e-108">Esta aplicación supone que todavía no ha creado ningún puerto de envío o ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9550e-108">This application assumes that you have not yet created any send ports or receive locations.</span></span> <span data-ttu-id="9550e-109">Si dispone de puertos de envío o ubicaciones de recepción existentes, sustituya los nombres correspondientes cuando siga los pasos.</span><span class="sxs-lookup"><span data-stu-id="9550e-109">If you have existing send ports or receive locations, substitute appropriate names when you work through the steps.</span></span>  
  
 <span data-ttu-id="9550e-110">La aplicación es una sencilla aplicación de enrutamiento por contenidos que sólo utiliza un puerto de envío o una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9550e-110">The application is a simple content-based routing application using only a receive location and a send port.</span></span> <span data-ttu-id="9550e-111">La ubicación de recepción lee de un buzón en el servidor que ejecuta [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("el servidor de Windows"\).</span><span class="sxs-lookup"><span data-stu-id="9550e-111">The receive location reads from a mailbox on the server running [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("the Windows server"\).</span></span> <span data-ttu-id="9550e-112">El puerto de envío toma el mensaje de la ubicación de recepción y lo envía a la carpeta del sistema de archivos local de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9550e-112">The send port takes the message from the receive location and sends it to a folder on the local file system of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9550e-113">Para crear la aplicación, debe crear el buzón, configurar el puerto de envío y la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], iniciar el puerto de envío, habilitar la ubicación de recepción y enviar un mensaje al buzón.</span><span class="sxs-lookup"><span data-stu-id="9550e-113">To create the application, you have to create the mailbox, set up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and send port, start the send port and enable the receive location, and send a test message to the mailbox.</span></span> <span data-ttu-id="9550e-114">Para crear la aplicación, siga los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="9550e-114">Follow the steps below to create the application.</span></span>  
  
## <a name="create-a-mailbox-on-windows-server-2003"></a><span data-ttu-id="9550e-115">Crear un buzón en Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="9550e-115">Create a mailbox on Windows Server 2003</span></span>  
 <span data-ttu-id="9550e-116">Para crear un buzón en Windows Server 2003 con servicios de correo electrónico instalados, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9550e-116">To create a mailbox on Windows Server 2003 with Email Services installed, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9550e-117">Haga clic en **iniciar**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **servicio POP3**.</span><span class="sxs-lookup"><span data-stu-id="9550e-117">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **POP3 Service**.</span></span>  
  
2.  <span data-ttu-id="9550e-118">Expanda  *\<servername\>*  y haga clic en el dominio donde desea crear un buzón.</span><span class="sxs-lookup"><span data-stu-id="9550e-118">Expand *\<servername\>* and click the domain where you would like to create a mailbox.</span></span>  
  
3.  <span data-ttu-id="9550e-119">En el **servicio POP3** cuadro de diálogo, en el panel derecho, haga clic en el **Agregar buzón** opción.</span><span class="sxs-lookup"><span data-stu-id="9550e-119">In the **POP3 Service** dialog box, in the right pane, click the **Add Mailbox** option.</span></span>  
  
4.  <span data-ttu-id="9550e-120">En el **Agregar buzón** cuadro de diálogo, en la **nombre del buzón** , escriba **EmailTest**.</span><span class="sxs-lookup"><span data-stu-id="9550e-120">In the **Add Mailbox** dialog box, in the **Mailbox Name** box, type **EmailTest**.</span></span>  
  
5.  <span data-ttu-id="9550e-121">Seleccione el **crear un usuario asociado para este buzón** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="9550e-121">Select the **Create associated user for this mailbox** check box.</span></span>  
  
6.  <span data-ttu-id="9550e-122">En el **contraseña** y **Confirmar contraseña** cuadros, escriba una contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9550e-122">In the **Password** and **Confirm Password** boxes, type a password, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="9550e-123">Tome nota de la **nombre de la cuenta** y **servidor de correo** inicie sesión en la información que se muestra para su uso con la autenticación de texto no cifrado en el **servicio POP3** cuadro de diálogo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9550e-123">Make a note of the **Account name** and **Mail Server** log on information displayed for use with clear text authentication in the **POP3 Service** dialog box, and then click **OK**.</span></span> <span data-ttu-id="9550e-124">La ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que configure con el tipo de transporte POP3 usará esta información.</span><span class="sxs-lookup"><span data-stu-id="9550e-124">This information will be used by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location that you configure with the POP3 transport type.</span></span>  
  
## <a name="create-the-receive-location"></a><span data-ttu-id="9550e-125">Crear la ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="9550e-125">Create the receive location</span></span>  
 <span data-ttu-id="9550e-126">Para crear la ubicación de recepción, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9550e-126">Follow these steps to create the receive location:</span></span>  
  
1.  <span data-ttu-id="9550e-127">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga doble clic en la base de datos predeterminada  **\<**  *nombre_equipo***\>. BizTalkMgmtDb.dbo**, donde *nombre_equipo* es el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="9550e-127">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console double-click the default database **\<***machine_name***\>.BizTalkMgmtDb.dbo**, where *machine_name* is the name of your computer.</span></span> <span data-ttu-id="9550e-128">Haga clic en **aplicaciones**, a continuación, haga clic en **BizTalk.Application.1**.</span><span class="sxs-lookup"><span data-stu-id="9550e-128">Click **Applications**, then click **BizTalk.Application.1**.</span></span>  
  
2.  <span data-ttu-id="9550e-129">Haga clic en **puertos de recepción**, haga clic en **New**, haga clic en **unidireccional puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="9550e-129">Right-click **Receive Ports**, click **New**, click **One-way receive port**.</span></span>  
  
3.  <span data-ttu-id="9550e-130">En el **propiedades de puerto de recepción** cuadro de diálogo, en la **nombre** , escriba **POP3Receive**.</span><span class="sxs-lookup"><span data-stu-id="9550e-130">In the **Receive Port Properties** dialog box, in the **Name** box, type **POP3Receive**.</span></span>  
  
4.  <span data-ttu-id="9550e-131">Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="9550e-131">Click **Receive Locations**, and then click **New**.</span></span>  <span data-ttu-id="9550e-132">En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba **POP3Receive**.</span><span class="sxs-lookup"><span data-stu-id="9550e-132">In the **Receive Location Properties** dialog box, in the **Name** box, type **POP3Receive**.</span></span>  
  
5.  <span data-ttu-id="9550e-133">En el **tipo de transporte** cuadro, seleccione **POP3**.</span><span class="sxs-lookup"><span data-stu-id="9550e-133">In the **Transport Type** box, select **POP3**.</span></span>  
  
6.  <span data-ttu-id="9550e-134">En el **controlador de recepción** cuadro, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="9550e-134">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
7.  <span data-ttu-id="9550e-135">En el **canalización de recepción** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span><span class="sxs-lookup"><span data-stu-id="9550e-135">In the **Receive Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
8.  <span data-ttu-id="9550e-136">En el **transporte** cuadro, haga clic en el **configurar** botón.</span><span class="sxs-lookup"><span data-stu-id="9550e-136">In the **Transport** box, click the **Configure** button.</span></span>  
  
9. <span data-ttu-id="9550e-137">En el **propiedades de transporte POP3** cuadro de diálogo, en la **aplicar descodificación MIME** cuadro, seleccione **False**.</span><span class="sxs-lookup"><span data-stu-id="9550e-137">In the **POP3 Transport Properties** dialog box, in the **Apply MIME Decoding** box, select **False**.</span></span>  
  
10. <span data-ttu-id="9550e-138">En el **servidor de correo electrónico** , escriba el nombre del servidor basado en Windows Server donde creó un buzón.</span><span class="sxs-lookup"><span data-stu-id="9550e-138">In the **Mail Server** box, type the name of the Windows Server-based server where you created a mailbox.</span></span>  
  
11. <span data-ttu-id="9550e-139">En el **esquema de autenticación** cuadro, seleccione **básica**.</span><span class="sxs-lookup"><span data-stu-id="9550e-139">In the **Authentication Scheme** box, select **Basic**.</span></span>  
  
12. <span data-ttu-id="9550e-140">En el **contraseña** cuadro, haga clic en la flecha de lista desplegable y escriba la contraseña del buzón.</span><span class="sxs-lookup"><span data-stu-id="9550e-140">In the **Password** box, click the drop-down arrow and type the password for the mailbox.</span></span>  
  
13. <span data-ttu-id="9550e-141">En el **nombre de usuario** , escriba el nombre de usuario completo para el buzón, por ejemplo  *username@host.domain.toplevel_domain.*</span><span class="sxs-lookup"><span data-stu-id="9550e-141">In the **User Name** box, type the fully qualified user name for the mailbox, for example *username@host.domain.toplevel_domain.*</span></span>  
  
14. <span data-ttu-id="9550e-142">En el **intervalo de sondeo** , escriba **1**, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="9550e-142">In the **Polling Interval** box, type **1**, click **OK**, and then click **OK** again.</span></span>  
  
## <a name="create-the-send-port-and-destination-folder-on-the-biztalk-server"></a><span data-ttu-id="9550e-143">Crear la carpeta de puerto de envío y de destino en el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9550e-143">Create the send port and destination folder on the BizTalk server</span></span>  
 <span data-ttu-id="9550e-144">Siga estos pasos para crear el puerto de envío y la carpeta de destino en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9550e-144">Follow these steps to create the send port and destination folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="9550e-145">Cree una carpeta en el sistema de archivos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9550e-145">Create a folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] file system.</span></span> <span data-ttu-id="9550e-146">Éste será el destino del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="9550e-146">This will be the destination for the send port.</span></span>  
  
2.  <span data-ttu-id="9550e-147">Haga clic en **puertos de envío**, haga clic en **nuevo** , a continuación, haga clic en **puerto de envío unidireccional estático.**</span><span class="sxs-lookup"><span data-stu-id="9550e-147">Right-click **Send Ports**, click **New,** then click **Static one-way Send Port.**</span></span>  
  
3.  <span data-ttu-id="9550e-148">En el **propiedades de puerto de envío** cuadro de diálogo, en la **tipo de transporte** cuadro, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="9550e-148">In the **Send Port Properties** dialog box, in the **Transport Type** box, select **FILE**.</span></span>  
  
4.  <span data-ttu-id="9550e-149">En el **nombre** , escriba **SendToFile**.</span><span class="sxs-lookup"><span data-stu-id="9550e-149">In the **Name** box, type **SendToFile**.</span></span>  
  
5.  <span data-ttu-id="9550e-150">En el **transporte** cuadro, haga clic en el **configurar** botón.</span><span class="sxs-lookup"><span data-stu-id="9550e-150">In the **Transport** box, click the **Configure** button.</span></span>  
  
6.  <span data-ttu-id="9550e-151">Junto a la **carpeta de destino** cuadro, haga clic en **examinar**, seleccione la carpeta que creó en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9550e-151">Next to the **Destination folder** box, click **Browse**, select the folder that you created on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="9550e-152">En el **nombre de archivo** , escriba **%MessageID%.txt**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9550e-152">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="9550e-153">En el **canalización de envío** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span><span class="sxs-lookup"><span data-stu-id="9550e-153">In the **Send Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
9. <span data-ttu-id="9550e-154">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="9550e-154">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="9550e-155">En el **propiedad** cuadro, seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="9550e-155">In the **Property** box, select **BTS.ReceivePortName**.</span></span>  
  
11. <span data-ttu-id="9550e-156">En el **valor** , escriba **POP3Receive**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9550e-156">In the **Value** box, type **POP3Receive**, and then click **OK**.</span></span>  
  
## <a name="enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="9550e-157">Habilitar la ubicación de recepción e iniciar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="9550e-157">Enable the receive location and start the send port</span></span>  
 <span data-ttu-id="9550e-158">Para habilitar la ubicación de recepción e iniciar el puerto de envío, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9550e-158">Follow these steps to enable the receive location and start the send port:</span></span>  
  
1.  <span data-ttu-id="9550e-159">Haga clic en el **POP3Receive** ubicación de recepción y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="9550e-159">Right-click the **POP3Receive** receive location, and then click **Enable**.</span></span>  
  
2.  <span data-ttu-id="9550e-160">Haga clic en el **SendToFile** puerto de envío y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="9550e-160">Right-click the **SendToFile** send port, and then click **Start**.</span></span>  
  
 <span data-ttu-id="9550e-161">El paso siguiente es probar la aplicación mediante el envío de un mensaje de prueba al buzón supervisado mediante la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9550e-161">The next step is to test the application by sending a test message to the mailbox monitored by the receive location.</span></span>  
  
## <a name="configure-outlook-express-to-send-an-e-mail-message-to-the-mailbox"></a><span data-ttu-id="9550e-162">Configurar Outlook Express para enviar un mensaje de correo electrónico al buzón</span><span class="sxs-lookup"><span data-stu-id="9550e-162">Configure Outlook Express to send an e-mail message to the mailbox</span></span>  
 <span data-ttu-id="9550e-163">Para configurar Outlook Express para enviar un mensaje de correo electrónico al buzón, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9550e-163">Follow these steps to configure Outlook Express to send an e-mail message to the mailbox:</span></span>  
  
1.  <span data-ttu-id="9550e-164">Haga clic en **iniciar**, seleccione **programas**y, a continuación, haga clic en **Outlook Express**.</span><span class="sxs-lookup"><span data-stu-id="9550e-164">Click **Start**, point to **Programs**, and then click **Outlook Express**.</span></span>  
  
2.  <span data-ttu-id="9550e-165">En Outlook Express, en el **herramientas** menú, haga clic en **cuentas**.</span><span class="sxs-lookup"><span data-stu-id="9550e-165">In Outlook Express, on the **Tools** menu, click **Accounts**.</span></span>  
  
3.  <span data-ttu-id="9550e-166">Haga clic en **agregar** y, a continuación, haga clic en **correo**.</span><span class="sxs-lookup"><span data-stu-id="9550e-166">Click **Add** and then click **Mail**.</span></span>  
  
4.  <span data-ttu-id="9550e-167">En el **nombre para mostrar** , escriba un nombre para mostrar y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9550e-167">In the **Display name** box, type a display name, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="9550e-168">En el **dirección de correo electrónico de Internet** cuadro de diálogo, en la **dirección de correo electrónico** , escriba **EmailTest @< nombreDeDominio >**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9550e-168">In the **Internet E-mail address** dialog box, in the **E-mail address** box, type **EmailTest@<domain_name>**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="9550e-169">Asegúrese de escribir el valor adecuado para *< nombreDeDominio >*.</span><span class="sxs-lookup"><span data-stu-id="9550e-169">Make sure to enter the appropriate value for *<domain_name>*.</span></span> <span data-ttu-id="9550e-170">Este valor debe coincidir con el nombre de dominio en el que se creó este buzón en la interfaz de administración de servicio POP3 en el servidor Windows.</span><span class="sxs-lookup"><span data-stu-id="9550e-170">This value should match the name of the domain under which this mailbox was created in the POP3 Service Administration interface on the Windows server.</span></span>  
  
6.  <span data-ttu-id="9550e-171">En el **nombres de servidor de correo electrónico** cuadro de diálogo, en la **correo entrante** y **correo saliente** cuadros, escriba el nombre del servidor o dirección IP del servidor de Windows y, a continuación, haga clic en  **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9550e-171">In the **E-mail Server names** dialog box, in the **Incoming mail** and **Outgoing mail** boxes, type the server name or IP address of the Windows server, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="9550e-172">En el **inicio de sesión de correo de Internet** cuadro de diálogo, en la **nombre de la cuenta** , escriba **EmailTest**.</span><span class="sxs-lookup"><span data-stu-id="9550e-172">In the **Internet Mail Logon** dialog box, in the **Account name** box, type **EmailTest**.</span></span>  
  
8.  <span data-ttu-id="9550e-173">En el **contraseña** , escriba la contraseña de la cuenta EmailTest, seleccione la **recordar contraseña** opción, haga clic en **siguiente**y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9550e-173">In the **Password** box, type the password for the EmailTest account, select the **Remember password** option, click **Next**, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="9550e-174">Haga clic para seleccionar la cuenta que acaba de crear y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9550e-174">Click to select the account that you just created, and then click **Properties**.</span></span>  
  
10. <span data-ttu-id="9550e-175">En el **propiedades** cuadro de diálogo, haga clic en el **avanzadas** , haga clic para seleccionar la opción de **dejar una copia de los mensajes en el servidor**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9550e-175">In the **Properties** dialog box, click the **Advanced** tab, click to select the option to **Leave a copy of messages on the server**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="9550e-176">En el **cuentas de Internet** cuadro de diálogo, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9550e-176">In the **Internet Accounts** dialog box, click **Close**.</span></span>  
  
12. <span data-ttu-id="9550e-177">Use Outlook Express para redactar un mensaje de prueba, tipo **probar** en el **asunto** campo y escriba **EmailTest @< nombreDeDominio >** en la **a** campo.</span><span class="sxs-lookup"><span data-stu-id="9550e-177">Use Outlook Express to compose a test message, type **Test** into the **Subject** field, and type **EmailTest@<domain_name>** into the **To** field.</span></span>  
  
13. <span data-ttu-id="9550e-178">Haga clic en **enviar** para enviar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="9550e-178">Click **Send** to send the test message.</span></span> <span data-ttu-id="9550e-179">Para asegurarse de que Outlook Express envía el mensaje de prueba inmediatamente, haga clic en el **enviar/recibir** botón en la barra de herramientas de Outlook Express.</span><span class="sxs-lookup"><span data-stu-id="9550e-179">To ensure that Outlook Express sends the test message immediately, click the **Send/Recv** button in the Outlook Express toolbar.</span></span>  
  
## <a name="view-the-message"></a><span data-ttu-id="9550e-180">Ver el mensaje</span><span class="sxs-lookup"><span data-stu-id="9550e-180">View the message</span></span>  
 <span data-ttu-id="9550e-181">Para ver el mensaje, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9550e-181">Follow these steps to view the message:</span></span>  
  
1.  <span data-ttu-id="9550e-182">Utilice el Explorador de Windows para abrir la carpeta que especificó como la **carpeta de destino** del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="9550e-182">Use Windows Explorer to open the folder that you specified as the **Destination Folder** for the send port.</span></span>  
  
2.  <span data-ttu-id="9550e-183">Haga doble clic en el documento de la carpeta para ver el contenido del documento en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="9550e-183">Double click the document in the folder to view the contents of the document in Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9550e-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="9550e-184">See Also</span></span>  
 [<span data-ttu-id="9550e-185">¿Qué es el adaptador de POP3?</span><span class="sxs-lookup"><span data-stu-id="9550e-185">What Is the POP3 Adapter?</span></span>](../core/what-is-the-pop3-adapter.md)