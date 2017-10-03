---
title: "Cómo recuperar el inicio de sesión único empresarial | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 845e6ff7-88a8-4ab4-b307-f9275d44600e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa0c0b5435e235a07046f311a971a0036dc8346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-enterprise-single-sign-on"></a><span data-ttu-id="852f2-102">Cómo recuperar el inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="852f2-102">How to Recover Enterprise Single Sign-On</span></span>
<span data-ttu-id="852f2-103">Antes de poder recuperar BizTalk Server, es preciso recuperar el inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="852f2-103">Before you can recover BizTalk Server, you must first recover Enterprise Single Sign-On (SSO).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="852f2-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="852f2-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="852f2-105">Para llevar a cabo esta tarea, debe haber iniciado sesión como miembro del grupo de administradores de inicio de sesión único y del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="852f2-105">You must be logged on as a member of the Single Sign-On Administrators group and a member of the Administrators group to perform this task.</span></span>  
  
-   <span data-ttu-id="852f2-106">Es preciso disponer de la contraseña utilizada durante la configuración de SSO.</span><span class="sxs-lookup"><span data-stu-id="852f2-106">You must have the password used during SSO configuration.</span></span>  
  
-   <span data-ttu-id="852f2-107">Todas las bases de datos están intactas en el servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="852f2-107">All databases are intact on the remote server.</span></span>  
  
-   <span data-ttu-id="852f2-108">El archivo de copia de seguridad del secreto principal está intacto y se encuentra almacenado en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="852f2-108">The backup master secret file is intact and stored in a safe place.</span></span>  
  
### <a name="to-recover-enterprise-single-sign-on"></a><span data-ttu-id="852f2-109">Para recuperar el inicio de sesión único empresarial</span><span class="sxs-lookup"><span data-stu-id="852f2-109">To recover Enterprise Single Sign-On</span></span>  
  
1.  <span data-ttu-id="852f2-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="852f2-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="852f2-111">Configuración de Microsoft BizTalk Server, en el árbol de consola, haga clic en **SSO empresarial**.</span><span class="sxs-lookup"><span data-stu-id="852f2-111">In Microsoft BizTalk Server Configuration, in the console tree, click **Enterprise SSO**.</span></span>  
  
3.  <span data-ttu-id="852f2-112">En el panel de detalles, seleccione **habilitar Enterprise Single Sign-On en este equipo**y, a continuación, haga clic en **unir un sistema SSO existente**.</span><span class="sxs-lookup"><span data-stu-id="852f2-112">In the details pane, select **Enable Enterprise Single Sign-On on this computer**, and then click **Join an existing SSO system**.</span></span>  
  
4.  <span data-ttu-id="852f2-113">En **almacenes de datos**, escriba el nombre de SQL server que hospeda la base de datos SSO y el nombre de la base de datos SSO.</span><span class="sxs-lookup"><span data-stu-id="852f2-113">In **Data stores**, enter the name of the SQL server hosting the SSO database and the name of the SSO database.</span></span>  
  
5.  <span data-ttu-id="852f2-114">En **servicio de Windows**, escriba el nombre de usuario y la contraseña para la cuenta de servicio SSO que usó al instalar y configurar BizTalk Server originalmente.</span><span class="sxs-lookup"><span data-stu-id="852f2-114">In **Windows service**, enter the user name and password for the SSO service account that you used when you originally installed and configured BizTalk Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="852f2-115">Se puede utilizar una cuenta distinta, pero, para ello, es preciso que ésta pertenezca al grupo de administradores de inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="852f2-115">You can use a different account, but it must be a member of the Single Sign-On Administrators group.</span></span>  
  
6.  <span data-ttu-id="852f2-116">Haga clic en **Aplicar configuración**.</span><span class="sxs-lookup"><span data-stu-id="852f2-116">Click **Apply Configuration**.</span></span>  
  
     <span data-ttu-id="852f2-117">Aparecerá una advertencia de que no se recuperó ningún secreto principal.</span><span class="sxs-lookup"><span data-stu-id="852f2-117">A warning that no master secrets were retrieved is displayed.</span></span> <span data-ttu-id="852f2-118">Se puede utilizar el Visor de sucesos para comprobar que se ha iniciado el servicio de inicio de sesión único empresarial y que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="852f2-118">You can use Event Viewer to verify that the Enterprise Single Sign-On service is now started and running on the computer.</span></span>  
  
7.  <span data-ttu-id="852f2-119">Haga clic en **archivo**y, a continuación, haga clic en **Exit**.</span><span class="sxs-lookup"><span data-stu-id="852f2-119">Click **File**, and then click **Exit**.</span></span>  
  
8.  <span data-ttu-id="852f2-120">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="852f2-120">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="852f2-121">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="852f2-121">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="852f2-122">**CD programa programa\Archivos comunes\enterprise Single Sign-On**</span><span class="sxs-lookup"><span data-stu-id="852f2-122">**cd Program Files\Common Files\Enterprise Single Sign-On**</span></span>  
  
10. <span data-ttu-id="852f2-123">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="852f2-123">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="852f2-124">**ssoconfig - restoreSecret***\<backupfile >* </span><span class="sxs-lookup"><span data-stu-id="852f2-124">**ssoconfig -restoreSecret**  *\<backupfile>*</span></span>  
  
     <span data-ttu-id="852f2-125">donde  *\<backupfile >* es el nombre del archivo secreto maestro que hizo copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="852f2-125">where *\<backupfile>* is the name of the master secret file that you backed up.</span></span>  
  
     <span data-ttu-id="852f2-126">Cuando **ssoconfig** le pide la contraseña del archivo de copia de seguridad, escriba la contraseña que se especificó durante la configuración de SSO.</span><span class="sxs-lookup"><span data-stu-id="852f2-126">When **ssoconfig** prompts you for the backup file password, enter the password that was specified during SSO configuration.</span></span> <span data-ttu-id="852f2-127">Si la contraseña es correcta, **ssoconfig** muestra el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="852f2-127">If the password is correct, **ssoconfig** displays the following message:</span></span>  
  
     <span data-ttu-id="852f2-128">**La operación se completó correctamente**</span><span class="sxs-lookup"><span data-stu-id="852f2-128">**The operation completed successfully**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="852f2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="852f2-129">See Also</span></span>  
 <span data-ttu-id="852f2-130">[Recuperar un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="852f2-130">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="852f2-131">Configuración de Enterprise SSO mediante la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="852f2-131">Configuring Enterprise SSO Using the BizTalk Server Configuration</span></span>](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)