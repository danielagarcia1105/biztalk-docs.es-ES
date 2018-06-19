---
title: Separar una orquestación | Documentos de Microsoft
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
ms.openlocfilehash: 38b8adc77e5e8579339931e49abb501f9981e5fc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970282"
---
# <a name="unbind-an-orchestration"></a><span data-ttu-id="174a4-102">Separar una orquestación</span><span class="sxs-lookup"><span data-stu-id="174a4-102">Unbind an Orchestration</span></span>

## <a name="overview"></a><span data-ttu-id="174a4-103">Información general</span><span class="sxs-lookup"><span data-stu-id="174a4-103">Overview</span></span>
<span data-ttu-id="174a4-104">En este tema se describen cómo utilizar la consola de administración de BizTalk Server para quitar enlaces de host, puerto de envío y puerto de recepción de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="174a4-104">This topic describes how to use the BizTalk Server Administration console to remove receive port, send port, or host bindings from an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="174a4-105">El desarrollador de aplicaciones puede quitar enlaces de una orquestación mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="174a4-105">The application developer can remove bindings for an orchestration  by using the procedure in this topic.</span></span> <span data-ttu-id="174a4-106">También puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="174a4-106">You can also use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="174a4-107">Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="174a4-107">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="174a4-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="174a4-108">Prerequisites</span></span>  
 <span data-ttu-id="174a4-109">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="174a4-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="174a4-110">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="174a4-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="remove-bindings-from-an-orchestration"></a><span data-ttu-id="174a4-111">Quitar enlaces de una orquestación</span><span class="sxs-lookup"><span data-stu-id="174a4-111">Remove bindings from an orchestration</span></span>  
  
1.  <span data-ttu-id="174a4-112">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="174a4-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="174a4-113">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación desde el que va a quitar enlaces</span><span class="sxs-lookup"><span data-stu-id="174a4-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration from which you want to remove bindings</span></span>  
  
3.  <span data-ttu-id="174a4-114">Haga clic en **orquestaciones**, haga clic en la orquestación, haga clic en **propiedades**y, a continuación, haga clic en **enlaces** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="174a4-114">Click **Orchestrations**, right-click the orchestration, click **Properties**, and then click **Bindings** in the left pane.</span></span>  
  
4.  <span data-ttu-id="174a4-115">Para quitar los enlaces de host, de la **Hosts** lista, seleccione  **\<ninguno\>**.</span><span class="sxs-lookup"><span data-stu-id="174a4-115">To remove the host bindings, from the **Hosts** list, select **\<None\>**.</span></span>  
  
5.  <span data-ttu-id="174a4-116">Para quitar enlaces de puertos de recepción en la lista desplegable de **puertos de recepción**, haga clic en  **\<ninguno\>**.</span><span class="sxs-lookup"><span data-stu-id="174a4-116">To remove receive port bindings, from the drop-down list under **Receive Ports**, click **\<None\>**.</span></span>  
  
6.  <span data-ttu-id="174a4-117">Para quitar enlaces de puertos de envío, en la lista desplegable de **grupos de puertos de envío y puertos de envío**, haga clic en  **\<ninguno\>**.</span><span class="sxs-lookup"><span data-stu-id="174a4-117">To remove send port bindings, from the drop-down list under **Send Ports/Send Port Groups**, click **\<None\>**.</span></span>  
  
7.  <span data-ttu-id="174a4-118">Cuando termine de quitar los enlaces, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="174a4-118">When finished removing bindings, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="174a4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="174a4-119">See Also</span></span>  
 <span data-ttu-id="174a4-120">[Administrar orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="174a4-120">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="174a4-121">[Cómo configurar enlaces para una orquestación](../core/how-to-configure-bindings-for-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="174a4-121">[How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md) </span></span>  
 [<span data-ttu-id="174a4-122">Implementar y administrar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="174a4-122">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)