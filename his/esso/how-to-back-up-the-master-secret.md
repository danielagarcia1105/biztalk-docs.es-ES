---
title: Cómo realizar copias de seguridad del secreto principal | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0841c52a-7b15-45f8-9900-f5c9e3abd90b
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 124c077d7a15a4938f94239518ad02c8268074a4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30251000"
---
# <a name="how-to-back-up-the-master-secret"></a><span data-ttu-id="8643d-102">Cómo realizar copias de seguridad del secreto principal</span><span class="sxs-lookup"><span data-stu-id="8643d-102">How to Back Up the Master Secret</span></span>
<span data-ttu-id="8643d-103">Es posible hacer una copia de seguridad del secreto principal desde el servidor secreto principal en un sistema de archivos NTFS o en un medio extraíble, como un disco.</span><span class="sxs-lookup"><span data-stu-id="8643d-103">You can back up the master secret from the master secret server onto an NTFS file system or removable media, such as a floppy disk.</span></span>  
  
 <span data-ttu-id="8643d-104">Debe ser un administrador de inicio de sesión único y un administrador de Windows para realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="8643d-104">You must be a Single Sign-On administrator and a Windows administrator to perform this task.</span></span> <span data-ttu-id="8643d-105">El sistema de inicio de sesión único (SSO) le pedirá una contraseña.</span><span class="sxs-lookup"><span data-stu-id="8643d-105">The Single Sign-On (SSO) system will prompt you for a password.</span></span> <span data-ttu-id="8643d-106">Para restaurar el secreto posteriormente, debe especificar la misma contraseña.</span><span class="sxs-lookup"><span data-stu-id="8643d-106">To restore the secret later, you must specify the same password.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8643d-107">Si el servidor secreto principal se bloquea y se pierde la clave, o si se daña la clave, no podrá recuperar los datos almacenados en la base de datos de credenciales.</span><span class="sxs-lookup"><span data-stu-id="8643d-107">If the master secret server crashes and you lose the key, or if the key becomes corrupted, you will not be able to retrieve data stored in the Credential database.</span></span> <span data-ttu-id="8643d-108">Debe hacer copia de seguridad del secreto principal o se arriesga a perder los datos de la base de datos de credenciales.</span><span class="sxs-lookup"><span data-stu-id="8643d-108">You must back up the master secret, or you risk losing data from the Credential database.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="8643d-109">Para hacer una copia de seguridad del secreto principal utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="8643d-109">To back up the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="8643d-110">Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="8643d-110">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="8643d-111">En el panel de ámbito del complemento de Microsoft Management Console (MMC) de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="8643d-111">In the scope pane of the ENTSSO Microsoft Management Console (MMC) Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="8643d-112">Haga clic en **System**y, a continuación, haga clic en **copia de seguridad secreto principal**.</span><span class="sxs-lookup"><span data-stu-id="8643d-112">Right-click **System**, and then click **Back up Master Secret**.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a><span data-ttu-id="8643d-113">Para hacer una copia de seguridad del secreto principal utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="8643d-113">To back up the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="8643d-114">En el **iniciar** menú, haga clic en **programas**y, a continuación, haga clic en **Accesorios**.</span><span class="sxs-lookup"><span data-stu-id="8643d-114">On the **Start** menu, click **Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="8643d-115">Haga clic en **símbolo**y, a continuación, haga clic en **ejecutar como...** .</span><span class="sxs-lookup"><span data-stu-id="8643d-115">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="8643d-116">Seleccione el administrador apropiado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8643d-116">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="8643d-117">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="8643d-117">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="8643d-118">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="8643d-118">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="8643d-119">Tipo de `ssoconfig –backupsecret <backup file>`, donde  *\<archivo de copia de seguridad >* es la ruta de acceso y nombre del archivo donde el secreto principal se copiarán, por ejemplo, `A:\ssobackup.bak`.</span><span class="sxs-lookup"><span data-stu-id="8643d-119">Type `ssoconfig –backupsecret <backup file>`, where *\<backup file>* is the path and name of the file where the master secret will be backed up, for example, `A:\ssobackup.bak`.</span></span>  
  
5.  <span data-ttu-id="8643d-120">Proporcione una contraseña para ayudar a proteger este archivo.</span><span class="sxs-lookup"><span data-stu-id="8643d-120">Provide a password to help protect this file.</span></span>  
  
     <span data-ttu-id="8643d-121">Se le solicitará que confirme la contraseña y que proporcione una sugerencia de contraseña para ayudar a recordar esta última.</span><span class="sxs-lookup"><span data-stu-id="8643d-121">You will be prompted to confirm the password and to provide a password hint to help you remember this password.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8643d-122">El archivo de copia de seguridad debe guardarse y almacenarse en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="8643d-122">You must save and store the backup file in a secure location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8643d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8643d-123">See Also</span></span>  
 <span data-ttu-id="8643d-124">[Cómo generar el secreto principal](../esso/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="8643d-124">[How to Generate the Master Secret](../esso/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="8643d-125">[Cómo restaurar el secreto principal](../esso/how-to-restore-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="8643d-125">[How to Restore the Master Secret](../esso/how-to-restore-the-master-secret.md) </span></span>  
 <span data-ttu-id="8643d-126">[Servidor secreto principal](../esso/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="8643d-126">[Master Secret Server](../esso/master-secret-server.md) </span></span>  
 [<span data-ttu-id="8643d-127">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="8643d-127">Managing the Master Secret</span></span>](../esso/managing-the-master-secret.md)