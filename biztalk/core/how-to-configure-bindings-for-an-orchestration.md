---
title: Configurar enlaces para una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9724a3a0-c217-4f98-b6d9-21f788ce50ba
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc4daaf1fec46dea10003d8037003ad894733c2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000149"
---
# <a name="how-to-configure-bindings-for-an-orchestration"></a><span data-ttu-id="aab52-102">Cómo configurar enlaces para una orquestación</span><span class="sxs-lookup"><span data-stu-id="aab52-102">How to Configure Bindings for an Orchestration</span></span>

## <a name="overview"></a><span data-ttu-id="aab52-103">Información general</span><span class="sxs-lookup"><span data-stu-id="aab52-103">Overview</span></span>
<span data-ttu-id="aab52-104">Este tema explica cómo usar la consola de administración de BizTalk Server para configurar enlaces para una orquestación.</span><span class="sxs-lookup"><span data-stu-id="aab52-104">This topic describes how to use the BizTalk Server Administration console to configure bindings for an orchestration.</span></span> <span data-ttu-id="aab52-105">Esto conlleva enlazar los puertos lógicos definidos para la orquestación a los puertos físicos en el entorno de ensayo o de producción, así como enlazar la orquestación a un host.</span><span class="sxs-lookup"><span data-stu-id="aab52-105">This involves binding the logical ports defined for the orchestration to physical ports in the staging or production environment as well as binding the orchestration to a host.</span></span> <span data-ttu-id="aab52-106">Si ya se ha enlazado la orquestación, es posible cambiar los enlaces mediante este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="aab52-106">If the orchestration has already been bound, you can change the bindings by using this procedure.</span></span>  
  
 <span data-ttu-id="aab52-107">Después de configurar los enlaces, se puede dar de alta la orquestación e iniciarla para que comience a procesar mensajes.</span><span class="sxs-lookup"><span data-stu-id="aab52-107">After configuring bindings, you can enlist the orchestration and then start it so that it begins processing messages.</span></span> <span data-ttu-id="aab52-108">Para obtener instrucciones sobre cómo realizar estas tareas, consulte [cómo dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md) y [cómo iniciar una orquestación](../core/how-to-start-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="aab52-108">For instructions on performing these tasks, see [How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) and [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aab52-109">El desarrollador de aplicaciones puede configurar enlaces para una orquestación para probar su funcionalidad durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="aab52-109">The application developer can configure bindings for an orchestration to test its functionality during the development process either by using the procedure in this topic.</span></span> <span data-ttu-id="aab52-110">También puede utilizar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="aab52-110">You can also use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="aab52-111">Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="aab52-111">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="aab52-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aab52-112">Prerequisites</span></span>  
 <span data-ttu-id="aab52-113">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="aab52-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="aab52-114">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="aab52-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="configure-bindings-for-an-orchestration"></a><span data-ttu-id="aab52-115">Configurar enlaces para una orquestación</span><span class="sxs-lookup"><span data-stu-id="aab52-115">Configure bindings for an orchestration</span></span>  
  
1. <span data-ttu-id="aab52-116">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="aab52-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="aab52-117">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación para la que desea configurar los enlaces</span><span class="sxs-lookup"><span data-stu-id="aab52-117">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to configure bindings</span></span>  
  
3. <span data-ttu-id="aab52-118">Haga clic en **orquestaciones**, haga clic en la orquestación que desea configurar los enlaces y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="aab52-118">Click **Orchestrations**, right-click the orchestration for which you want to configure bindings, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="aab52-119">Haga clic en el **enlaces** ficha y desde el **Host** lista, seleccione el host en el que se va a dar de alta una orquestación.</span><span class="sxs-lookup"><span data-stu-id="aab52-119">Click the **Bindings** tab, and from the **Host** list, select the host on which to enlist an orchestration.</span></span>  
  
5. <span data-ttu-id="aab52-120">En la lista desplegable se enumeran en la **puertos de recepción** columna, junto a cada puerto lógico de entrada, seleccione el puerto de recepción al que desea enlazar el puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="aab52-120">From the drop-down lists in the **Receive Ports** column, next to each inbound logical port, select the receive port to which you want to bind the logical port.</span></span>  
  
6. <span data-ttu-id="aab52-121">En la lista desplegable en el **grupos de puertos de envío y puertos de envío** columna, junto a cada puerto lógico de entrada, seleccione el puerto de envío a la que desea enlazar el puerto lógico y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aab52-121">From the drop-down list in the **Send Ports/Send Port Groups** column, next to each inbound logical port, select the send port to which you want to bind the logical port, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab52-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="aab52-122">See Also</span></span>  
 <span data-ttu-id="aab52-123">[Administración de orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="aab52-123">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="aab52-124">[Cómo separar una orquestación](../core/how-to-unbind-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="aab52-124">[How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md) </span></span>  
 [<span data-ttu-id="aab52-125">Implementación y administración de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="aab52-125">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)