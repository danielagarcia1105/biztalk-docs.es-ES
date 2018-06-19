---
title: Recuperar el grupo de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3563956daa4848d4d67c1321c23676b21f9e4735
ms.sourcegitcommit: 78376935362715684b451eb6da9f2b1e8c129c2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
ms.locfileid: "28944100"
---
# <a name="how-to-recover-the-biztalk-group"></a><span data-ttu-id="dbb0b-102">Cómo recuperar el grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="dbb0b-102">How to Recover the BizTalk Group</span></span>
<span data-ttu-id="dbb0b-103">Debe volver a unir BizTalk Server a un grupo de BizTalk como parte del proceso de recuperación del sistema.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-103">You must rejoin the BizTalk Server to an existing BizTalk group as part of the system recovery process.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dbb0b-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dbb0b-104">Prerequisites</span></span>  
 <span data-ttu-id="dbb0b-105">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
 <span data-ttu-id="dbb0b-106">Si va a recuperar la edición estándar de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe descargarse una cadena que facilite la recuperación del servidor.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-106">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must download a script that facilitates recovery of the server.</span></span> <span data-ttu-id="dbb0b-107">Descargar [RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462).</span><span class="sxs-lookup"><span data-stu-id="dbb0b-107">Download [RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462).</span></span>  
  
## <a name="recover-the-biztalk-group-standard-edition"></a><span data-ttu-id="dbb0b-108">Recuperar el grupo de BizTalk (Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="dbb0b-108">Recover the BizTalk group (Standard Edition)</span></span>  
  
1.  <span data-ttu-id="dbb0b-109">Haga clic en **iniciar**, tipo **cmd**y, a continuación, seleccione **símbolo**.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-109">Click **Start**, type **cmd**, and then select **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="dbb0b-110">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="dbb0b-110">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="dbb0b-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span><span class="sxs-lookup"><span data-stu-id="dbb0b-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span></span>  
  
     <span data-ttu-id="dbb0b-112">Donde  *\<SavedConfigXML\>*  es la ruta de acceso completa y el nombre del archivo de configuración guardado.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-112">Where *\<SavedConfigXML\>* is the full path and filename of the saved configuration file.</span></span>  
  
     <span data-ttu-id="dbb0b-113">Lo anterior debe aparecer sin mostrar ningún error.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-113">The above should exit without displaying any errors.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dbb0b-114">Para recuperar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition en un equipo de 64 bits, debe ejecutar **RestoreConfig.vbe** desde el símbolo de 32 bits, de modo que pueda actualizar el registro de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-114">To recover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition on a 64-bit computer, you must run **RestoreConfig.vbe** from the 32-bit command prompt so that it can update the 32-bit registry.</span></span> <span data-ttu-id="dbb0b-115">Para abrir el símbolo del sistema de 32 bits, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **c:\windows\syswow64\cmd.exe**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-115">To open the 32-bit command prompt, click **Start**, click **Run**, type **c:\windows\syswow64\cmd.exe**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dbb0b-116">El nombre del equipo en el que se ha producido el error se incluye en el archivo de configuración guardado.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-116">The name of the computer that failed is contained in the saved configuration file.</span></span> <span data-ttu-id="dbb0b-117">El nombre del equipo en el que se restaura debe tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-117">The name of the computer that you are restoring onto must have that same name.</span></span> <span data-ttu-id="dbb0b-118">Debe ejecutar la secuencia de comandos anterior en un equipo con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-118">You must run the script above on a computer with that name.</span></span> <span data-ttu-id="dbb0b-119">Sin embargo, en el archivo de configuración guardado, puede modificar el nombre del equipo en el que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-119">You can, however, change the name of the computer that failed in the saved configuration file.</span></span> <span data-ttu-id="dbb0b-120">Si lo hace, puede ejecutar la secuencia de comandos anterior en un equipo con otro nombre.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-120">If you do so, you can run the script above onto a computer with a different name.</span></span>  
  
## <a name="recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a><span data-ttu-id="dbb0b-121">Recuperar el grupo de BizTalk (Developer Edition o Enterprise Edition)</span><span class="sxs-lookup"><span data-stu-id="dbb0b-121">Recover the BizTalk group (Developer Edition or Enterprise Edition)</span></span>  
  
1.  <span data-ttu-id="dbb0b-122">Abra **configuración de BizTalk Server** (menú Inicio).</span><span class="sxs-lookup"><span data-stu-id="dbb0b-122">Open **BizTalk Server Configuration** (Start menu).</span></span>
  
2.  <span data-ttu-id="dbb0b-123">En administración de BizTalk Server, seleccione **grupo**.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-123">In BizTalk Server Administration, select **Group**.</span></span>  
  
3.  <span data-ttu-id="dbb0b-124">En el panel de detalles, seleccione **unirse a un grupo de BizTalk existente**y, a continuación, escriba la base de datos de administración de BizTalk (BizTalkMgmtDb) remoto.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-124">In the details pane, select **Join an existing BizTalk Group**, and then enter the remote BizTalk Management (BizTalkMgmtDb) database.</span></span>  
  
4.  <span data-ttu-id="dbb0b-125">Seleccione **aplicar configuración**.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-125">Select **Apply Configuration**.</span></span>  
  
5.  <span data-ttu-id="dbb0b-126">Seleccione **archivo**y, a continuación, seleccione **Exit**.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-126">Select **File**, and then select **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb0b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbb0b-127">See Also</span></span>  
 [<span data-ttu-id="dbb0b-128">Recuperación de un equipo que ejecuta BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="dbb0b-128">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)
