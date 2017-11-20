---
title: "Cómo realizar copias de seguridad del Portal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cea02e6-e387-4048-a1f3-d7c3c562f470
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e7308e54505c795e35ffa2fbb2d287c1a49ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-the-bam-portal"></a><span data-ttu-id="4129d-102">Cómo realizar una copia de seguridad del portal de SAE</span><span class="sxs-lookup"><span data-stu-id="4129d-102">How to Back Up the BAM Portal</span></span>
<span data-ttu-id="4129d-103">Si utiliza Supervisión de la actividad económica (SAE), debe realizar una copia de seguridad del portal de SAE como parte de la realización de copias de seguridad de su servidor de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4129d-103">If you are using Business Activity Monitoring (BAM), you must back up the BAM portal as part of backing up your BizTalk server.</span></span> <span data-ttu-id="4129d-104">Si no utiliza SAE, este procedimiento es opcional.</span><span class="sxs-lookup"><span data-stu-id="4129d-104">If you are not using BAM, this procedure is optional.</span></span>  
  
 <span data-ttu-id="4129d-105">Algunas partes del proceso de copia de seguridad difieren en gran medida en función de la versión de Internet Information Services (IIS) de la que esté realizando una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4129d-105">Certain portions of the backup process differ markedly depending on which version of Internet Information Services (IIS) you are backing up.</span></span> <span data-ttu-id="4129d-106">IIS 6.0 permite realizar una copia de seguridad de la configuración del grupo de aplicaciones y de la configuración de sitio web de manera independiente; también puede cifrar los archivos de copia de seguridad de la configuración mediante una contraseña.</span><span class="sxs-lookup"><span data-stu-id="4129d-106">IIS 6.0 permits you to back up the application pool configuration and web site configuration separately, and you can encrypt the configuration backup files using a password.</span></span>  
  
 <span data-ttu-id="4129d-107">IIS 7.0 guarda la configuración para el sitio web y el grupo de aplicaciones en un único archivo applicationHost.config. No se cifra el archivo applicationHost.config, pero las contraseñas de cuenta, si los hay, se cifran en el archivo.</span><span class="sxs-lookup"><span data-stu-id="4129d-107">IIS 7.0 saves configuration settings for both the application pool and web site to a single file, applicationHost.config. The applicationHost.config file is not encrypted, but account passwords, if any, are encrypted in the file.</span></span> <span data-ttu-id="4129d-108">El cifrado se realiza mediante el certificado del equipo del que está realizando una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4129d-108">Encryption is performed using the certificate from the computer you are backing up.</span></span> <span data-ttu-id="4129d-109">Esta configuración no se puede restaurar en un equipo distinto de aquel en el que se originó.</span><span class="sxs-lookup"><span data-stu-id="4129d-109">This configuration cannot be restored to a computer other than the one from which it originated.</span></span>  
  
 <span data-ttu-id="4129d-110">No se puede realizar copias de seguridad de la configuración de portal de BAM mediante el Administrador de IIS 7.0; debe utilizar el **Appcmd.exe** herramienta de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4129d-110">You cannot back up the BAM portal configuration using the IIS 7.0 Manager; you must use the **Appcmd.exe** command-line tool.</span></span> <span data-ttu-id="4129d-111">Para obtener más información acerca de Appcmd, vea [http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497).</span><span class="sxs-lookup"><span data-stu-id="4129d-111">For more information about Appcmd, see [http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4129d-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4129d-112">Prerequisites</span></span>  
 <span data-ttu-id="4129d-113">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="4129d-113">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-back-up-the-bam-portal-iis-70"></a><span data-ttu-id="4129d-114">Para realizar una copia de seguridad del portal de BAM (IIS 7.0)</span><span class="sxs-lookup"><span data-stu-id="4129d-114">To back up the BAM portal (IIS 7.0)</span></span>  
  
1.  <span data-ttu-id="4129d-115">Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4129d-115">Click **Start**, and then click **Run**.</span></span>  
  
2.  <span data-ttu-id="4129d-116">En el cuadro de diálogo Ejecutar, en el cuadro Abrir, escriba lo siguiente: `runas /user:` *computername*`\`*accountname* `cmd`y, a continuación, haga clic en **Aceptar** o Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4129d-116">On the Run dialog, in the Open box, type the following: `runas /user:`*computername*`\`*accountname* `cmd`, and then click **OK** or press **Enter**.</span></span>  
  
     <span data-ttu-id="4129d-117">*AccountName* debe ser miembro del grupo Administradores en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="4129d-117">*Accountname* must be a member of the administrators group on the local computer.</span></span>  
  
3.  <span data-ttu-id="4129d-118">Cuando se le solicite, escriba la contraseña de *accountname*y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4129d-118">When prompted, type the password for *accountname*, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="4129d-119">Tipo de `cd %windir%\system32\inetsrv`y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4129d-119">Type `cd %windir%\system32\inetsrv`, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="4129d-120">Tipo de `appcmd add backup “` *nombrecopiadeseguridad*`”`y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4129d-120">Type `appcmd add backup “`*backupname*`”`, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="4129d-121">No es necesario que escriba un nombre para la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4129d-121">You do not have to enter a backup name.</span></span> <span data-ttu-id="4129d-122">Si no se indica, se generará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4129d-122">If not set, it will be autogenerated.</span></span> <span data-ttu-id="4129d-123">Un ejemplo de nombre de la copia de seguridad generado automáticamente es “20090224T123302”.</span><span class="sxs-lookup"><span data-stu-id="4129d-123">An example of an autogenerated backup name is “20090224T123302.”</span></span>  
  
     <span data-ttu-id="4129d-124">Para ver una lista de copias de seguridad de configuración existente, escriba `appcmd list backup`y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4129d-124">To see a list of existing configuration backups, type `appcmd list backup`, and then press **Enter**.</span></span> <span data-ttu-id="4129d-125">Copias de seguridad creadas por el usuario se guardan en el **%windir%\system32\inetsrv\backup** directory.</span><span class="sxs-lookup"><span data-stu-id="4129d-125">Backups created by the user are saved in the **%windir%\system32\inetsrv\backup** directory.</span></span> <span data-ttu-id="4129d-126">Para ver una lista de las opciones de copia de seguridad proporcionadas por **appcmd.exe**, tipo `appcmd backup /?`y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4129d-126">To see a list of the backup options provided by **appcmd.exe**, type `appcmd backup /?`, and then press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4129d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4129d-127">See Also</span></span>  
 <span data-ttu-id="4129d-128">[Realizar una copia de seguridad de un equipo que ejecuta BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="4129d-128">[Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span></span>  
 <span data-ttu-id="4129d-129">[Recuperar un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="4129d-129">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="4129d-130">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="4129d-130">BAM Portal</span></span>](../core/bam-portal.md)