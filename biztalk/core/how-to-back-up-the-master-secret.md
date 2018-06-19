---
title: Cómo realizar copias de seguridad del secreto principal | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], backing up
- backing up, Master Secret server
- Master Secret server, backing up
ms.assetid: 22c23f66-b7df-4379-8a9f-065406ba8aa8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 185f3ea674015e02cac2bdaa785c2ee06e67db65
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25969586"
---
# <a name="how-to-back-up-the-master-secret"></a><span data-ttu-id="249f8-102">Cómo realizar copias de seguridad del secreto principal</span><span class="sxs-lookup"><span data-stu-id="249f8-102">How to Back Up the Master Secret</span></span>
<span data-ttu-id="249f8-103">Es posible hacer una copia de seguridad del secreto principal desde el servidor secreto principal en un sistema de archivos NTFS o en un medio extraíble, como un disco.</span><span class="sxs-lookup"><span data-stu-id="249f8-103">You can back up the master secret from the master secret server onto an NTFS file system or removable media, such as a floppy disk.</span></span>  
  
 <span data-ttu-id="249f8-104">Es preciso ser un administrador de inicio de sesión único y un administrador de Windows para llevar a cabo esta tarea.</span><span class="sxs-lookup"><span data-stu-id="249f8-104">You must be a Single Sign-On Administrator and a Windows administrator to perform this task.</span></span> <span data-ttu-id="249f8-105">El sistema de SSO solicitará una contraseña.</span><span class="sxs-lookup"><span data-stu-id="249f8-105">The SSO system will prompt you for a password.</span></span> <span data-ttu-id="249f8-106">Para restaurar el secreto posteriormente, debe especificar la misma contraseña.</span><span class="sxs-lookup"><span data-stu-id="249f8-106">To restore the secret later, you must specify the same password.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="249f8-107">Si el servidor secreto principal no funciona y se pierde la clave o se daña, no será posible recuperar los datos almacenados en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="249f8-107">If the master secret server fails and you lose the key, or if the key becomes corrupted, you will not be able to retrieve data stored in the SSO database.</span></span> <span data-ttu-id="249f8-108">Se debe hacer una copia de seguridad del secreto principal o, de lo contrario, existirá el riesgo de perder los datos de la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="249f8-108">You must back up the master secret, or you risk losing data from the SSO database.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="249f8-109">Para hacer una copia de seguridad del secreto principal utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="249f8-109">To back up the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="249f8-110">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="249f8-110">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="249f8-111">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="249f8-111">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="249f8-112">Haga clic en **System**y, a continuación, haga clic en **secreto de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="249f8-112">Right-click **System**, and then click **Backup Secret**.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a><span data-ttu-id="249f8-113">Para hacer una copia de seguridad del secreto principal utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="249f8-113">To back up the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="249f8-114">En el **iniciar** menú, haga clic en **todos los programas**y, a continuación, haga clic en **Accesorios**.</span><span class="sxs-lookup"><span data-stu-id="249f8-114">On the **Start** menu, click **All Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="249f8-115">Haga clic en **símbolo**y, a continuación, haga clic en **ejecutar como...** .</span><span class="sxs-lookup"><span data-stu-id="249f8-115">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="249f8-116">Seleccione el administrador apropiado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="249f8-116">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="249f8-117">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="249f8-117">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="249f8-118">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="249f8-118">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="249f8-119">Tipo ** ssoconfig – backupSecret *\<archivo de copia de seguridad\>***, donde *\<archivo de copia de seguridad\>* es la ruta de acceso y nombre del archivo donde se copiarán el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="249f8-119">Type **ssoconfig –backupSecret *\<backup file\>***, where *\<backup file\>* is the path and name of the file where the master secret will be backed up.</span></span> <span data-ttu-id="249f8-120">Por ejemplo, A:\ssobackup.bak</span><span class="sxs-lookup"><span data-stu-id="249f8-120">For example, A:\ssobackup.bak</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="249f8-121">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="249f8-121">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="249f8-122">Proporcione una contraseña para proteger el archivo.</span><span class="sxs-lookup"><span data-stu-id="249f8-122">Provide a password to protect this file.</span></span> <span data-ttu-id="249f8-123">Se le solicitará que confirme la contraseña y que proporcione una sugerencia de contraseña para ayudar a recordar esta última.</span><span class="sxs-lookup"><span data-stu-id="249f8-123">You will be prompted to confirm the password and to provide a password hint to help you remember this password.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="249f8-124">El archivo de copia de seguridad debe guardarse y almacenarse en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="249f8-124">You must save and store the backup file in a secure location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249f8-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="249f8-125">See Also</span></span>  
 <span data-ttu-id="249f8-126">[Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="249f8-126">[How to Generate the Master Secret](../core/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="249f8-127">[Cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="249f8-127">[How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) </span></span>  
 <span data-ttu-id="249f8-128">[Servidor secreto principal](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="249f8-128">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="249f8-129">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="249f8-129">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)