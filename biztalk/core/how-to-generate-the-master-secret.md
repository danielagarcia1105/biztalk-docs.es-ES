---
title: "Cómo generar el secreto principal | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, generating
- managing [Master Secret server], generating
ms.assetid: 5512a8ee-bc5b-4fe4-90c7-41e3baaa723b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1a7ee4f8ffe73a71e8c0b2e3d45c7a966669fd8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-generate-the-master-secret"></a><span data-ttu-id="3e55b-102">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="3e55b-102">How to Generate the Master Secret</span></span>
<span data-ttu-id="3e55b-103">Debe tener derechos de administrador en el servidor secreto principal para realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="3e55b-103">You must have administrator rights on the master secret server in order to perform this task.</span></span> <span data-ttu-id="3e55b-104">Asimismo, debe realizar esta tarea en el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="3e55b-104">In addition, you must perform this task from the master secret server.</span></span>  
  
 <span data-ttu-id="3e55b-105">El primer servidor en el que instala el inicio de sesión único empresarial se convierte en el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="3e55b-105">The first server where you install Enterprise Single Sign-On becomes the master secret server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3e55b-106">Sólo puede haber un servidor secreto principal en el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="3e55b-106">There can be only one master secret server in your SSO system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e55b-107">Cuando se instala el inicio de sesión único empresarial como parte de la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el secreto principal se genera como parte del Asistente para configuración.</span><span class="sxs-lookup"><span data-stu-id="3e55b-107">When Enterprise Single Sign-On is installed as part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation, the master secret is generated as part of the Configuration Wizard.</span></span> <span data-ttu-id="3e55b-108">Sólo necesita realizar esta tarea si desea generar un secreto principal nuevo.</span><span class="sxs-lookup"><span data-stu-id="3e55b-108">You will only need to perform this task if you want to generate a new master secret.</span></span>  
  
### <a name="to-generate-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="3e55b-109">Para generar el secreto principal mediante el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="3e55b-109">To generate the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="3e55b-110">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="3e55b-110">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="3e55b-111">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="3e55b-111">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="3e55b-112">Haga clic en **System**y, a continuación, haga clic en **generar secreto**.</span><span class="sxs-lookup"><span data-stu-id="3e55b-112">Right-click **System**, and then click **Generate Secret**.</span></span>  
  
### <a name="to-generate-the-master-secret-using-the-command-line"></a><span data-ttu-id="3e55b-113">Para generar el secreto principal mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="3e55b-113">To generate the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="3e55b-114">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="3e55b-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="3e55b-115">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="3e55b-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="3e55b-116">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="3e55b-116">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="3e55b-117">Tipo de  **ssoconfig – generateSecret \<* archivo de copia de seguridad*\>**, donde \<* el archivo de copia de seguridad* \> es el nombre del archivo que contiene el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="3e55b-117">Type **ssoconfig –generateSecret \<*backup file*\>**, where \<*backup file*\> is the name of the file that contains the master secret.</span></span>  
  
     <span data-ttu-id="3e55b-118">Se le pedirá que escriba una contraseña para proteger el archivo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="3e55b-118">You will be prompted to enter a password to protect the file you just created.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e55b-119">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="3e55b-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e55b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e55b-120">See Also</span></span>  
 <span data-ttu-id="3e55b-121">[Cómo realizar copias de seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="3e55b-121">[How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md) </span></span>  
 <span data-ttu-id="3e55b-122">[Servidor secreto principal](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="3e55b-122">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="3e55b-123">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="3e55b-123">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)