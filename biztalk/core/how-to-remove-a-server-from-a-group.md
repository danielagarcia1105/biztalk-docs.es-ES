---
title: "Cómo quitar un servidor de un grupo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- groups, servers
- managing [groups], deleting servers
- servers, deleting
- deleting, groups
- servers
- managing [servers], deleting from groups
- groups, deleting
- servers, groups
- deleting, servers
ms.assetid: 85596e18-fa17-4f44-bc20-2e4cb578e109
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b69eb694da320e598c7d0cfe5a03d58e0a723a8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-server-from-a-group"></a><span data-ttu-id="66471-102">Cómo quitar un servidor de un grupo</span><span class="sxs-lookup"><span data-stu-id="66471-102">How to Remove a Server from a Group</span></span>
<span data-ttu-id="66471-103">Un servidor sólo se puede asociar con un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="66471-103">A server can only be associated with one BizTalk group.</span></span> <span data-ttu-id="66471-104">Si un servidor pertenece ya a otro grupo, debe quitar primero ese servidor del grupo actual para poder agregarlo al grupo nuevo.</span><span class="sxs-lookup"><span data-stu-id="66471-104">If a server already belongs to another group, you must first remove that server from its current group before you can add it to a new group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="66471-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="66471-105">Prerequisites</span></span>  
 <span data-ttu-id="66471-106">Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores de Windows.</span><span class="sxs-lookup"><span data-stu-id="66471-106">To perform this procedure, you must be logged on as a member of the Windows Administrators group.</span></span>  
  
### <a name="to-remove-a-server-from-a-group"></a><span data-ttu-id="66471-107">Para quitar un servidor de un grupo</span><span class="sxs-lookup"><span data-stu-id="66471-107">To remove a server from a group</span></span>  
  
1.  <span data-ttu-id="66471-108">En el equipo que desea quitar de un grupo de BizTalk Server, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **deconfiguracióndeBizTalkServer**.</span><span class="sxs-lookup"><span data-stu-id="66471-108">On the computer that you want to remove from a BizTalk Server group, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="66471-109">En la barra de menús, haga clic en **desconfigurar características**.</span><span class="sxs-lookup"><span data-stu-id="66471-109">On the menu bar, click **Unconfigure Features**.</span></span>  
  
3.  <span data-ttu-id="66471-110">En el **desconfigurar características** cuadro de diálogo, seleccione **grupo**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="66471-110">In the **Unconfigure Features** dialog box, select **Group**, and then click **OK**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="66471-111">Al quitar la configuración de un grupo, también se quitará la configuración de todas las características dependientes que ya estén configuradas en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="66471-111">Unconfiguring a group will also unconfigure all dependent features that are already configured on that computer.</span></span>  
  
4.  <span data-ttu-id="66471-112">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="66471-112">Click **Yes**.</span></span>  
  
5.  <span data-ttu-id="66471-113">En el Asistente para la configuración de Microsoft BizTalk Server, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="66471-113">In the Microsoft BizTalk Server Configuration Wizard, click **Next**.</span></span>  
  
     <span data-ttu-id="66471-114">Se quitará la configuración del grupo y de las características dependientes.</span><span class="sxs-lookup"><span data-stu-id="66471-114">The Group and its dependent features are unconfigured.</span></span>  
  
6.  <span data-ttu-id="66471-115">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="66471-115">Click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66471-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="66471-116">See Also</span></span>  
 <span data-ttu-id="66471-117">[Administración de grupos](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="66471-117">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="66471-118">[Grupos de BizTalk](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="66471-118">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="66471-119">[Cómo agregar un servidor a un grupo](../core/how-to-add-a-server-to-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="66471-119">[How to Add a Server to a Group](../core/how-to-add-a-server-to-a-group.md) </span></span>  
 <span data-ttu-id="66471-120">[Cómo mover un servidor de un grupo a otro](../core/how-to-move-a-server-from-one-group-to-another.md) </span><span class="sxs-lookup"><span data-stu-id="66471-120">[How to Move a Server from One Group to Another](../core/how-to-move-a-server-from-one-group-to-another.md) </span></span>  
 <span data-ttu-id="66471-121">[Cómo modificar las propiedades de grupo](../core/how-to-modify-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="66471-121">[How to Modify Group Properties](../core/how-to-modify-group-properties.md) </span></span>  
 [<span data-ttu-id="66471-122">Administración de servidores</span><span class="sxs-lookup"><span data-stu-id="66471-122">Managing Servers</span></span>](../core/managing-servers.md)