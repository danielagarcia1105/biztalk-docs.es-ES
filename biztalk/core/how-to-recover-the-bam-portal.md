---
title: "Cómo recuperar el Portal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2a5df99-6d03-4f1f-8540-1700d3a0b9db
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 781191047e0ee99b0000c7b773d46aa035a7e1d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-bam-portal"></a><span data-ttu-id="4ef40-102">Cómo recuperar el portal de SAE</span><span class="sxs-lookup"><span data-stu-id="4ef40-102">How to Recover the BAM Portal</span></span>
<span data-ttu-id="4ef40-103">Si usa la Supervisión de la actividad económica (BAM), debe recuperar el portal de BAM como parte de la recuperación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ef40-103">If you are using Business Activity Monitoring (BAM), you must recover the BAM portal as a part of recovering your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4ef40-104">Si no utiliza SAE, este procedimiento es opcional.</span><span class="sxs-lookup"><span data-stu-id="4ef40-104">If you are not using BAM, this procedure is optional.</span></span>  
  
 <span data-ttu-id="4ef40-105">El procedimiento para la recuperación de la configuración del portal de BAM difiere considerablemente según la versión de IIS que use.</span><span class="sxs-lookup"><span data-stu-id="4ef40-105">The procedure for recovering the BAM portal configuration differs considerably depending on which version of IIS you are using.</span></span> <span data-ttu-id="4ef40-106">Cuando se restaura la configuración de IIS 7, use **Appcmd.exe**, y restaurar la configuración para el sitio Web predeterminado todo, no solo en el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="4ef40-106">When you restore the configuration for IIS 7, you use **Appcmd.exe**, and you restore the configuration for the entire default Web site, not just the BAM portal.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4ef40-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4ef40-107">Prerequisites</span></span>  
 <span data-ttu-id="4ef40-108">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="4ef40-108">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-the-bam-portal-configuration-iis-70"></a><span data-ttu-id="4ef40-109">Para recuperar la configuración del portal de BAM (IIS 7.0)</span><span class="sxs-lookup"><span data-stu-id="4ef40-109">To recover the BAM portal configuration (IIS 7.0)</span></span>  
  
1.  <span data-ttu-id="4ef40-110">En el cuadro de diálogo Ejecutar, en el cuadro Abrir, escriba lo siguiente: `runas /user:` *computername*`\`*accountname* `cmd`y, a continuación, haga clic en **Aceptar** o Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4ef40-110">On the Run dialog, in the Open box, type the following: `runas /user:`*computername*`\`*accountname* `cmd`, and then click **OK** or press **Enter**.</span></span>  
  
     <span data-ttu-id="4ef40-111">*AccountName* debe ser miembro del grupo Administradores en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="4ef40-111">*Accountname* must be a member of the administrators group on the local computer.</span></span>  
  
2.  <span data-ttu-id="4ef40-112">Cuando se le solicite, escriba la contraseña de *accountname*y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4ef40-112">When prompted, type the password for *accountname*, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="4ef40-113">Tipo de `cd %windir%\system32\inetsrv`y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4ef40-113">Type `cd %windir%\system32\inetsrv`, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="4ef40-114">Tipo de `appcmd restore backup “` *nombrecopiadeseguridad*`”`y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4ef40-114">Type `appcmd restore backup “`*backupname*`”`, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="4ef40-115">*Nombrecopiadeseguridad* es el nombre de una copia de seguridad que creó previamente mediante **Appcmd.exe**.</span><span class="sxs-lookup"><span data-stu-id="4ef40-115">*Backupname* is the name of a backup you previously created using **Appcmd.exe**.</span></span> <span data-ttu-id="4ef40-116">Esta copia de seguridad debe existir en el **%windir%\system32\inetsrv\backup** directory.</span><span class="sxs-lookup"><span data-stu-id="4ef40-116">This backup must exist in the **%windir%\system32\inetsrv\backup** directory.</span></span> <span data-ttu-id="4ef40-117">No se puede usar la copia de seguridad para restaurar las contraseñas creadas en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="4ef40-117">The backup cannot be used to restore passwords created on a different computer.</span></span> <span data-ttu-id="4ef40-118">Si BAMAppPool se ha configurado para ejecutarse bajo una identidad que no sea el valor predeterminado **NetworkService** cuenta, debe configurar la cuenta y contraseña por separado, tal como se describe en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="4ef40-118">If the BAMAppPool is configured to run under an identity other than the default **NetworkService** account, you must configure the account and password separately, as described in the next step.</span></span>  
  
5.  <span data-ttu-id="4ef40-119">Mediante el **Internet Information Services (IIS) Manager**, seleccione **grupos de aplicaciones** en el **conexiones** panel.</span><span class="sxs-lookup"><span data-stu-id="4ef40-119">Using the **Internet Information Services (IIS) Manager**, select **Application Pools** in the **Connections** pane.</span></span>  
  
6.  <span data-ttu-id="4ef40-120">En el **grupos de aplicaciones** panel, haga clic en el **BAMAppPool**, a continuación, haga clic en **configuración avanzada**</span><span class="sxs-lookup"><span data-stu-id="4ef40-120">In the **Application Pools** pane, right-click the **BAMAppPool**, then click **Advanced Settings**</span></span>  
  
7.  <span data-ttu-id="4ef40-121">En el **configuración avanzada de**cuadro de diálogo, desplácese hacia abajo hasta la **modelo de proceso** sección.</span><span class="sxs-lookup"><span data-stu-id="4ef40-121">In the **Advanced Setting**s dialog, scroll down to the **Process Model** section.</span></span> <span data-ttu-id="4ef40-122">Haga clic en el **identidad** cuadro.</span><span class="sxs-lookup"><span data-stu-id="4ef40-122">Click the **Identity** box.</span></span> <span data-ttu-id="4ef40-123">Esto hará que aparezca un botón de puntos suspensivos en el lado derecho del cuadro.</span><span class="sxs-lookup"><span data-stu-id="4ef40-123">This will cause an ellipses button to appear on the right side of the box.</span></span> <span data-ttu-id="4ef40-124">Haga clic en el **puntos suspensivos** botón.</span><span class="sxs-lookup"><span data-stu-id="4ef40-124">Click the **ellipses** button.</span></span>  
  
8.  <span data-ttu-id="4ef40-125">En el **identidad del grupo de aplicaciones** cuadro de diálogo, haga clic en el **cuenta personalizada** , a continuación, haga clic en el **establecer** botón.</span><span class="sxs-lookup"><span data-stu-id="4ef40-125">In the **Application Pool Identity** dialog, click the **Custom account** button, then click the **Set** button.</span></span>  
  
9. <span data-ttu-id="4ef40-126">En el **establecer credenciales** diálogo cuadro, escriba el nombre de cuenta y la contraseña que desea usar para BAMAppPool.</span><span class="sxs-lookup"><span data-stu-id="4ef40-126">In the **Set Credentials** dialog box, enter the account name and password you want to use for the BAMAppPool.</span></span> <span data-ttu-id="4ef40-127">El nombre de cuenta debe especificarse como *nombre_equipo*`\`*accountname*, o *dominio*`\`*accountname*.</span><span class="sxs-lookup"><span data-stu-id="4ef40-127">The account name should be entered as *computer name*`\`*accountname*, or *domain*`\`*accountname*.</span></span> <span data-ttu-id="4ef40-128">Haga clic en **Aceptar** para cerrar el **establecer credenciales** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4ef40-128">Click **OK** to close the **Set Credentials** dialog.</span></span>  
  
10. <span data-ttu-id="4ef40-129">Haga clic en **Aceptar** para cerrar el **identidad del grupo de aplicaciones** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4ef40-129">Click **OK** to close the **Application Pool Identity** dialog.</span></span>  
  
11. <span data-ttu-id="4ef40-130">Haga clic en **Aceptar** para cerrar el **configuración avanzada** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4ef40-130">Click **OK** to close the **Advanced Settings** dialog.</span></span>  
  
12. <span data-ttu-id="4ef40-131">Compruebe que la **BAMAppPool** está seleccionado en la lista de grupos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4ef40-131">Verify that the **BAMAppPool** is selected in the list of application pools.</span></span> <span data-ttu-id="4ef40-132">En el **acciones** panel de la derecha de la **el Administrador de Internet Information Services (IIS)** pantalla **tareas del grupo de aplicaciones**, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="4ef40-132">In the **Actions** pane on the right of the **Internet Information Services (IIS) Manager** screen, under **Application Pool Tasks**, click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ef40-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ef40-133">See Also</span></span>  
 <span data-ttu-id="4ef40-134">[Recuperar un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ef40-134">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="4ef40-135">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="4ef40-135">BAM Portal</span></span>](../core/bam-portal.md)