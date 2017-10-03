---
title: "Cómo cambiar el servidor secreto principal | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, promoting
- managing [Master Secret server], promoting servers
- managing [SSO], promoting servers
- SSO, Master Secret server
- modifying, Master Secret server
- Master Secret server, changing
ms.assetid: 44a786ca-4645-44a8-b33e-d0019f0aeca9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4676db07025b4395d58df7c24252769ba65ecfb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-master-secret-server"></a><span data-ttu-id="00e60-102">Cómo cambiar el servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="00e60-102">How to Change the Master Secret Server</span></span>
<span data-ttu-id="00e60-103">Después de configurar el servidor secreto principal y la base de datos de SSO, podrá cambiar el servidor secreto principal siempre que el original haya fallado y no pueda recuperarse.</span><span class="sxs-lookup"><span data-stu-id="00e60-103">After you set up the master secret server and configure the SSO database, you can change the master secret server if the original master secret server fails and cannot be recovered.</span></span> <span data-ttu-id="00e60-104">Para cambiar el servidor secreto principal, deberá promover un servidor de SSO para convertirlo en servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="00e60-104">To change the master secret server, you need to promote an SSO server to become the master secret server.</span></span>  
  
### <a name="to-change-the-master-secret-server-using-the-mmc-snap-in"></a><span data-ttu-id="00e60-105">Para cambiar el servidor secreto principal utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="00e60-105">To change the Master Secret Server using the MMC Snap-in</span></span>  
  
1.  <span data-ttu-id="00e60-106">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="00e60-106">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="00e60-107">En el panel de ámbito, haga clic en **System**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="00e60-107">In the scope pane, right click **System**, and then click **Properties**.</span></span> <span data-ttu-id="00e60-108">El maestro de servidor secreto se muestra en el **General** pestaña de la **propiedades del sistema** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="00e60-108">The Master secret server is displayed on the **General** tab of the **System Properties** dialog box.</span></span>  
  
3.  <span data-ttu-id="00e60-109">Haga clic en **cambio** para seleccionar un nuevo patrón servidor secreto.</span><span class="sxs-lookup"><span data-stu-id="00e60-109">Click **Change** to select a new Master secret server.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="00e60-110">Cuando se utiliza el complemento MMC para cambiar el servidor secreto principal, la operación debe llevarse a cabo en éste.</span><span class="sxs-lookup"><span data-stu-id="00e60-110">When using the MMC Snap-in to change the Master Secret Server, the operation must be performed on the Master Secret Server.</span></span> <span data-ttu-id="00e60-111">No es posible cambiar el servidor secreto principal que utiliza el complemento de MMC desde un equipo que no sea el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="00e60-111">It is not possible to change the Master Secret Server using the MMC Snap-in from a computer that is not the Master Secret Server.</span></span>  
  
4.  <span data-ttu-id="00e60-112">Inicie sesión en el nuevo servidor secreto principal para restaurar el secreto principal en el Registro del nuevo servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="00e60-112">Logon to the new Master secret server to restore the Master secret to the registry of the new Master secret server.</span></span>  
  
5.  <span data-ttu-id="00e60-113">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="00e60-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
6.  <span data-ttu-id="00e60-114">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="00e60-114">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="00e60-115">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="00e60-115">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
7.  <span data-ttu-id="00e60-116">Reinicie el nuevo servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="00e60-116">Restart the new Master Secret Server.</span></span>  
  
8.  <span data-ttu-id="00e60-117">Tipo de **ssoconfig – restoreSecret \<Restaurar archivo >**, donde  **\<Restaurar archivo >** es la ruta de acceso y nombre del archivo donde se almacena el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="00e60-117">Type **ssoconfig –restoreSecret \<restore file>**, where **\<restore file>** is the path and name of the file where the master secret is stored.</span></span>  
  
     <span data-ttu-id="00e60-118">El secreto principal se almacena en el Registro en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="00e60-118">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="00e60-119">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span><span class="sxs-lookup"><span data-stu-id="00e60-119">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00e60-120">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="00e60-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-promote-a-single-sign-on-server-to-master-secret-server-using-the-command-line"></a><span data-ttu-id="00e60-121">Para promover un servidor de SSO a servidor secreto principal utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="00e60-121">To promote a Single Sign-On Server to master secret server using the command line</span></span>  
  
1.  <span data-ttu-id="00e60-122">Cree un archivo XML que incluya el nombre del servidor de SSO que desea promover a servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="00e60-122">Create an XML file that includes the name of the SSO server you want to promote to master secret server.</span></span> <span data-ttu-id="00e60-123">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="00e60-123">For example,</span></span>  
  
    ```  
    <sso>  
      <globalInfo>  
         <secretServer>SSO Server name</secretServer>  
      </globalInfo>  
    </sso>  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="00e60-124">Para cambiar el servidor secreto principal desde un equipo que no sea este servidor, asegúrese de que el archivo XML especificado contenga únicamente el nombre del servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="00e60-124">To change the Master Secret Server from a computer that is not the Master Secret Server make sure that the specified XML file contains only the Master Secret Server name.</span></span> <span data-ttu-id="00e60-125">En concreto, no debe contener la etiqueta XML de los administradores de SSO o **ssomanage - updatedb** se producirá un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="00e60-125">Specifically, it should not contain the SSO Administrators XML tag or the **ssomanage -updatedb** operation will fail.</span></span>  
  
2.  <span data-ttu-id="00e60-126">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="00e60-126">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
3.  <span data-ttu-id="00e60-127">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="00e60-127">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="00e60-128">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="00e60-128">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="00e60-129">Tipo de **ssomanage-updatedb** \< **archivo de actualización**>, donde \< **archivo de actualización**> es el nombre del archivo XML se crea en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="00e60-129">Type **ssomanage –updatedb** \<**update file**>, where \<**update file**> is the name of the XML file you create in step 1.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00e60-130">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="00e60-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="00e60-131">Reinicie el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="00e60-131">Restart the Master Secret Server.</span></span>  
  
6.  <span data-ttu-id="00e60-132">Tipo de **ssoconfig – restoresecret \<Restaurar archivo >**, donde  **\<Restaurar archivo >** es la ruta de acceso y nombre del archivo donde se almacena el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="00e60-132">Type **ssoconfig –restoresecret \<restore file>**, where **\<restore file>** is the path and name of the file where the master secret is stored.</span></span>  
  
     <span data-ttu-id="00e60-133">El secreto principal se almacena en el Registro en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="00e60-133">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="00e60-134">HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS</span><span class="sxs-lookup"><span data-stu-id="00e60-134">HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00e60-135">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="00e60-135">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e60-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="00e60-136">See Also</span></span>  
 <span data-ttu-id="00e60-137">[Servidor secreto principal](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="00e60-137">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 <span data-ttu-id="00e60-138">[Cómo agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md) </span><span class="sxs-lookup"><span data-stu-id="00e60-138">[How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md) </span></span>  
 <span data-ttu-id="00e60-139">[Cómo actualizar la base de datos SSO](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="00e60-139">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="00e60-140">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="00e60-140">Using SSO</span></span>](../core/using-sso.md)