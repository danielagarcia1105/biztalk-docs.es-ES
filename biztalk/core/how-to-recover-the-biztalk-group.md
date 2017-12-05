---
title: "Cómo recuperar el grupo de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: deaf3ddae7d7351d53c5cd46b7d48633e0271a3d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-recover-the-biztalk-group"></a><span data-ttu-id="aa1a8-102">Cómo recuperar el grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="aa1a8-102">How to Recover the BizTalk Group</span></span>
<span data-ttu-id="aa1a8-103">Debe volver a unir BizTalk Server a un grupo de BizTalk como parte del proceso de recuperación del sistema.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-103">You must rejoin the BizTalk Server to an existing BizTalk group as part of the system recovery process.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aa1a8-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aa1a8-104">Prerequisites</span></span>  
 <span data-ttu-id="aa1a8-105">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
 <span data-ttu-id="aa1a8-106">Si va a recuperar la edición estándar de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe descargarse una cadena que facilite la recuperación del servidor.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-106">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must download a script that facilitates recovery of the server.</span></span> <span data-ttu-id="aa1a8-107">Descargar [RestoreConfig.vbe](http://go.microsoft.com/fwlink/?LinkID=195799).</span><span class="sxs-lookup"><span data-stu-id="aa1a8-107">Download [RestoreConfig.vbe](http://go.microsoft.com/fwlink/?LinkID=195799).</span></span>  
  
### <a name="to-recover-the-biztalk-group-standard-edition"></a><span data-ttu-id="aa1a8-108">Para recuperar el grupo de BizTalk (Edición estándar)</span><span class="sxs-lookup"><span data-stu-id="aa1a8-108">To recover the BizTalk group (Standard Edition)</span></span>  
  
1.  <span data-ttu-id="aa1a8-109">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-109">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="aa1a8-110">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="aa1a8-110">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="aa1a8-111">**RestoreConfig.vbe***\<SavedConfigXML  \>*</span><span class="sxs-lookup"><span data-stu-id="aa1a8-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span></span>  
  
     <span data-ttu-id="aa1a8-112">Donde  *\<SavedConfigXML\>*  es la ruta de acceso completa y el nombre del archivo de configuración guardado.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-112">Where *\<SavedConfigXML\>* is the full path and filename of the saved configuration file.</span></span>  
  
     <span data-ttu-id="aa1a8-113">Lo anterior debe aparecer sin mostrar ningún error.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-113">The above should exit without displaying any errors.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aa1a8-114">Para recuperar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition en un equipo de 64 bits, debe ejecutar **RestoreConfig.vbe** desde el símbolo de 32 bits, de modo que pueda actualizar el registro de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-114">To recover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition on a 64-bit computer, you must run **RestoreConfig.vbe** from the 32-bit command prompt so that it can update the 32-bit registry.</span></span> <span data-ttu-id="aa1a8-115">Para abrir el símbolo del sistema de 32 bits, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **c:\windows\syswow64\cmd.exe**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-115">To open the 32-bit command prompt, click **Start**, click **Run**, type **c:\windows\syswow64\cmd.exe**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aa1a8-116">El nombre del equipo en el que se ha producido el error se incluye en el archivo de configuración guardado.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-116">The name of the computer that failed is contained in the saved configuration file.</span></span> <span data-ttu-id="aa1a8-117">El nombre del equipo en el que se restaura debe tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-117">The name of the computer that you are restoring onto must have that same name.</span></span> <span data-ttu-id="aa1a8-118">Debe ejecutar la secuencia de comandos anterior en un equipo con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-118">You must run the script above on a computer with that name.</span></span> <span data-ttu-id="aa1a8-119">Sin embargo, en el archivo de configuración guardado, puede modificar el nombre del equipo en el que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-119">You can, however, change the name of the computer that failed in the saved configuration file.</span></span> <span data-ttu-id="aa1a8-120">Si lo hace, puede ejecutar la secuencia de comandos anterior en un equipo con otro nombre.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-120">If you do so, you can run the script above onto a computer with a different name.</span></span>  
  
### <a name="to-recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a><span data-ttu-id="aa1a8-121">Para recuperar el grupo de BizTalk (Edición para programadores o edición empresarial)</span><span class="sxs-lookup"><span data-stu-id="aa1a8-121">To recover the BizTalk group (Developer Edition or Enterprise Edition)</span></span>  
  
1.  <span data-ttu-id="aa1a8-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="aa1a8-123">En [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], en el árbol de consola, haga clic en **grupo**.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-123">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], in the console tree, click **Group**.</span></span>  
  
3.  <span data-ttu-id="aa1a8-124">En el panel de detalles, seleccione **unirse a un grupo de BizTalk existente**y, a continuación, especifique la base de datos de administración de BizTalk (BizTalkMgmtDb) remoto adecuado.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-124">In the details pane, select **Join an existing BizTalk Group**, and then specify the appropriate remote BizTalk Management (BizTalkMgmtDb) database.</span></span>  
  
4.  <span data-ttu-id="aa1a8-125">Haga clic en **Aplicar configuración**.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-125">Click **Apply Configuration**.</span></span>  
  
5.  <span data-ttu-id="aa1a8-126">Haga clic en **archivo**y, a continuación, haga clic en **Exit**.</span><span class="sxs-lookup"><span data-stu-id="aa1a8-126">Click **File**, and then click **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa1a8-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa1a8-127">See Also</span></span>  
 [<span data-ttu-id="aa1a8-128">Recuperación de un equipo que ejecuta BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="aa1a8-128">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)