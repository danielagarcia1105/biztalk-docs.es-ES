---
title: Separar una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a7c421d-e0cb-4b23-b472-e501056d6329
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5673101934c4ba35deb4d63839c23e3d9cda7e4b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992629"
---
# <a name="unbind-an-orchestration"></a><span data-ttu-id="e7b85-102">Separar una orquestación</span><span class="sxs-lookup"><span data-stu-id="e7b85-102">Unbind an Orchestration</span></span>

## <a name="overview"></a><span data-ttu-id="e7b85-103">Información general</span><span class="sxs-lookup"><span data-stu-id="e7b85-103">Overview</span></span>
<span data-ttu-id="e7b85-104">En este tema se describen cómo utilizar la consola de administración de BizTalk Server para quitar enlaces de host, puerto de envío y puerto de recepción de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="e7b85-104">This topic describes how to use the BizTalk Server Administration console to remove receive port, send port, or host bindings from an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7b85-105">El desarrollador de aplicaciones puede quitar enlaces de una orquestación mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="e7b85-105">The application developer can remove bindings for an orchestration  by using the procedure in this topic.</span></span> <span data-ttu-id="e7b85-106">También puede utilizar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="e7b85-106">You can also use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="e7b85-107">Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="e7b85-107">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="e7b85-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e7b85-108">Prerequisites</span></span>  
 <span data-ttu-id="e7b85-109">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e7b85-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="e7b85-110">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="e7b85-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="remove-bindings-from-an-orchestration"></a><span data-ttu-id="e7b85-111">Quitar enlaces de una orquestación</span><span class="sxs-lookup"><span data-stu-id="e7b85-111">Remove bindings from an orchestration</span></span>  
  
1. <span data-ttu-id="e7b85-112">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e7b85-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="e7b85-113">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación desde el que desea quitar enlaces</span><span class="sxs-lookup"><span data-stu-id="e7b85-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration from which you want to remove bindings</span></span>  
  
3. <span data-ttu-id="e7b85-114">Haga clic en **orquestaciones**, haga clic en la orquestación, haga clic en **propiedades**y, a continuación, haga clic en **enlaces** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="e7b85-114">Click **Orchestrations**, right-click the orchestration, click **Properties**, and then click **Bindings** in the left pane.</span></span>  
  
4. <span data-ttu-id="e7b85-115">Para quitar los enlaces de host de la **Hosts** lista, seleccione  **\<ninguno\>**.</span><span class="sxs-lookup"><span data-stu-id="e7b85-115">To remove the host bindings, from the **Hosts** list, select **\<None\>**.</span></span>  
  
5. <span data-ttu-id="e7b85-116">Para quitar enlaces de puerto de recepción en la lista desplegable **puertos de recepción**, haga clic en  **\<ninguno\>**.</span><span class="sxs-lookup"><span data-stu-id="e7b85-116">To remove receive port bindings, from the drop-down list under **Receive Ports**, click **\<None\>**.</span></span>  
  
6. <span data-ttu-id="e7b85-117">Para quitar los enlaces de puerto de envío, en la lista desplegable **grupos de puertos de envío y puertos de envío**, haga clic en  **\<ninguno\>**.</span><span class="sxs-lookup"><span data-stu-id="e7b85-117">To remove send port bindings, from the drop-down list under **Send Ports/Send Port Groups**, click **\<None\>**.</span></span>  
  
7. <span data-ttu-id="e7b85-118">Cuando termine de quitar los enlaces, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7b85-118">When finished removing bindings, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b85-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7b85-119">See Also</span></span>  
 <span data-ttu-id="e7b85-120">[Administración de orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="e7b85-120">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="e7b85-121">[Cómo configurar enlaces para una orquestación](../core/how-to-configure-bindings-for-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="e7b85-121">[How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md) </span></span>  
 [<span data-ttu-id="e7b85-122">Implementación y administración de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e7b85-122">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)