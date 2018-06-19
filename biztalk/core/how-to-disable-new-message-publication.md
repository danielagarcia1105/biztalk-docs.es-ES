---
title: Deshabilitar publicación de nuevos mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9099ecaa-31ed-4880-a0f6-8dbfaf783f7a
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 478cf89ac4677d60e9a5b5a855998e0b0e5120c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254564"
---
# <a name="disable-new-message-publication"></a><span data-ttu-id="292b6-102">Deshabilitar la publicación de mensajes nuevos</span><span class="sxs-lookup"><span data-stu-id="292b6-102">Disable New Message Publication</span></span>

## <a name="overview"></a><span data-ttu-id="292b6-103">Información general</span><span class="sxs-lookup"><span data-stu-id="292b6-103">Overview</span></span>
<span data-ttu-id="292b6-104">Instrumental de administración de Windows (WMI) o la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usa para deshabilitar la publicación de nuevos mensajes.</span><span class="sxs-lookup"><span data-stu-id="292b6-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console or Windows Management Instrumentation (WMI) to disable new message publication.</span></span> <span data-ttu-id="292b6-105">En la base de datos de cuadro de mensajes se deshabilita la publicación de mensajes nuevos para dejar de recibir mensajes nuevos en esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="292b6-105">You disable new message publication in the MessageBox database to stop the receipt of new messages by the MessageBox database.</span></span> <span data-ttu-id="292b6-106">En algunos entornos de BizTalk Server, puede mejorar el rendimiento si se deshabilita la publicación de mensajes nuevos para la base de datos de cuadro de mensajes principal.</span><span class="sxs-lookup"><span data-stu-id="292b6-106">In some BizTalk Server environments, you can improve performance if you disable new message publication for the master MessageBox database.</span></span> <span data-ttu-id="292b6-107">Deshabilitar la publicación de mensajes nuevos no afecta a los mensajes existentes en la base de datos de cuadro de mensajes ni a las instancias de servicio que están en curso.</span><span class="sxs-lookup"><span data-stu-id="292b6-107">Disabling new message publication does not affect existing messages in the MessageBox database or service instances that are in progress.</span></span>  
  
 <span data-ttu-id="292b6-108">Para obtener información acerca del uso de WMI para deshabilitar la publicación de mensajes nuevos, consulte el **MSBTS_MsgBoxSetting.DisableNewMessagePublication propiedad (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="292b6-108">For information about using WMI to disable new message publication, see the **MSBTS_MsgBoxSetting.DisableNewMessagePublication Property (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="292b6-109">Debe deshabilitar la publicación de mensajes nuevos antes de eliminar una base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="292b6-109">You must disable the publication of new messages before you delete a MessageBox database.</span></span> <span data-ttu-id="292b6-110">Para obtener información acerca de cómo eliminar una base de datos de cuadro de mensajes, vea [cómo eliminar una base de datos de cuadro de mensajes](../core/how-to-delete-a-messagebox-database.md).</span><span class="sxs-lookup"><span data-stu-id="292b6-110">For information about deleting a MessageBox database, see [How to Delete a MessageBox Database](../core/how-to-delete-a-messagebox-database.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="292b6-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="292b6-111">Prerequisites</span></span>  
 <span data-ttu-id="292b6-112">Los administradores de las bases de datos de cuadro de mensajes deben tener los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="292b6-112">Administrators who manage MessageBox databases must have the required user rights.</span></span> <span data-ttu-id="292b6-113">Debe tener los siguientes derechos de usuario para administrar las bases de datos de cuadro de mensajes y deshabilitar la publicación de mensajes nuevos:</span><span class="sxs-lookup"><span data-stu-id="292b6-113">You must have the following user rights to manage MessageBox databases and disable new message publication:</span></span>  
  
-   <span data-ttu-id="292b6-114">Debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="292b6-114">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="292b6-115">Debe ser administrador de SQL Server en el equipo donde reside la base de datos.</span><span class="sxs-lookup"><span data-stu-id="292b6-115">You must be a SQL Server Administrator on the computer where the database exists.</span></span>  
  
## <a name="disable-steps"></a><span data-ttu-id="292b6-116">Deshabilitar pasos</span><span class="sxs-lookup"><span data-stu-id="292b6-116">Disable steps</span></span>
  
1.  <span data-ttu-id="292b6-117">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="292b6-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="292b6-118">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **cuadros de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="292b6-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Message Boxes**.</span></span>  
  
3.  <span data-ttu-id="292b6-119">En el panel de detalles, haga clic en la base de datos de cuadro de mensajes que desea deshabilitar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="292b6-119">In the details pane, right-click the MessageBox database you want to disable, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="292b6-120">En el **propiedades de cuadro de mensaje** cuadro de diálogo, seleccione la **Deshabilitar publicación de nuevos mensajes** casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="292b6-120">In the **Message Box Properties** dialog box, select the **Disable new message publication** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="292b6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="292b6-121">See Also</span></span>  
 <span data-ttu-id="292b6-122">[Administrar bases de datos de cuadro de mensajes](../core/managing-messagebox-databases.md) </span><span class="sxs-lookup"><span data-stu-id="292b6-122">[Managing MessageBox Databases](../core/managing-messagebox-databases.md) </span></span>  
 <span data-ttu-id="292b6-123">[Agregar una nueva base de datos de cuadro de mensajes](../core/how-to-add-a-new-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="292b6-123">[Add a New MessageBox Database](../core/how-to-add-a-new-messagebox-database.md) </span></span>  
 <span data-ttu-id="292b6-124">[Eliminar una base de datos de cuadro de mensajes](../core/how-to-delete-a-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="292b6-124">[Delete a MessageBox Database](../core/how-to-delete-a-messagebox-database.md) </span></span>  
 [<span data-ttu-id="292b6-125">La base de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="292b6-125">The MessageBox Database</span></span>](../core/the-messagebox-database.md)