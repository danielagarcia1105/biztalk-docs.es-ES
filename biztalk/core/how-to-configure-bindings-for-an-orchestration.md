---
title: Configurar enlaces para una orquestación | Documentos de Microsoft
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
ms.openlocfilehash: adb695f9636327107887397372d5fc2dda74e4eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248924"
---
# <a name="how-to-configure-bindings-for-an-orchestration"></a><span data-ttu-id="96d3e-102">Cómo configurar enlaces para una orquestación</span><span class="sxs-lookup"><span data-stu-id="96d3e-102">How to Configure Bindings for an Orchestration</span></span>

## <a name="overview"></a><span data-ttu-id="96d3e-103">Información general</span><span class="sxs-lookup"><span data-stu-id="96d3e-103">Overview</span></span>
<span data-ttu-id="96d3e-104">Este tema explica cómo usar la consola de administración de BizTalk Server para configurar enlaces para una orquestación.</span><span class="sxs-lookup"><span data-stu-id="96d3e-104">This topic describes how to use the BizTalk Server Administration console to configure bindings for an orchestration.</span></span> <span data-ttu-id="96d3e-105">Esto conlleva enlazar los puertos lógicos definidos para la orquestación a los puertos físicos en el entorno de ensayo o de producción, así como enlazar la orquestación a un host.</span><span class="sxs-lookup"><span data-stu-id="96d3e-105">This involves binding the logical ports defined for the orchestration to physical ports in the staging or production environment as well as binding the orchestration to a host.</span></span> <span data-ttu-id="96d3e-106">Si ya se ha enlazado la orquestación, es posible cambiar los enlaces mediante este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="96d3e-106">If the orchestration has already been bound, you can change the bindings by using this procedure.</span></span>  
  
 <span data-ttu-id="96d3e-107">Después de configurar los enlaces, se puede dar de alta la orquestación e iniciarla para que comience a procesar mensajes.</span><span class="sxs-lookup"><span data-stu-id="96d3e-107">After configuring bindings, you can enlist the orchestration and then start it so that it begins processing messages.</span></span> <span data-ttu-id="96d3e-108">Para obtener instrucciones acerca de cómo realizar estas tareas, consulte [cómo dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md) y [cómo iniciar una orquestación](../core/how-to-start-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="96d3e-108">For instructions on performing these tasks, see [How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) and [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96d3e-109">El desarrollador de aplicaciones puede configurar enlaces para una orquestación para probar su funcionalidad durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="96d3e-109">The application developer can configure bindings for an orchestration to test its functionality during the development process either by using the procedure in this topic.</span></span> <span data-ttu-id="96d3e-110">También puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="96d3e-110">You can also use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="96d3e-111">Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="96d3e-111">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="96d3e-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="96d3e-112">Prerequisites</span></span>  
 <span data-ttu-id="96d3e-113">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="96d3e-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="96d3e-114">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="96d3e-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="configure-bindings-for-an-orchestration"></a><span data-ttu-id="96d3e-115">Configurar enlaces para una orquestación</span><span class="sxs-lookup"><span data-stu-id="96d3e-115">Configure bindings for an orchestration</span></span>  
  
1.  <span data-ttu-id="96d3e-116">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="96d3e-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="96d3e-117">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación para la que va a configurar los enlaces</span><span class="sxs-lookup"><span data-stu-id="96d3e-117">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to configure bindings</span></span>  
  
3.  <span data-ttu-id="96d3e-118">Haga clic en **orquestaciones**, haga clic en la orquestación para la que desea configurar los enlaces y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="96d3e-118">Click **Orchestrations**, right-click the orchestration for which you want to configure bindings, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="96d3e-119">Haga clic en el **enlaces** ficha y desde el **Host** lista, seleccione el host en el que se va a dar de alta una orquestación.</span><span class="sxs-lookup"><span data-stu-id="96d3e-119">Click the **Bindings** tab, and from the **Host** list, select the host on which to enlist an orchestration.</span></span>  
  
5.  <span data-ttu-id="96d3e-120">En la lista desplegable se enumeran en la **puertos de recepción** columna, junto a cada puerto lógico de entrada, seleccione el puerto de recepción al que desea enlazar el puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="96d3e-120">From the drop-down lists in the **Receive Ports** column, next to each inbound logical port, select the receive port to which you want to bind the logical port.</span></span>  
  
6.  <span data-ttu-id="96d3e-121">En la lista desplegable de la **grupos de puertos de envío y puertos de envío** columna, junto a cada puerto lógico de entrada, seleccione el puerto de envío a la que desea enlazar el puerto lógico y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96d3e-121">From the drop-down list in the **Send Ports/Send Port Groups** column, next to each inbound logical port, select the send port to which you want to bind the logical port, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d3e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="96d3e-122">See Also</span></span>  
 <span data-ttu-id="96d3e-123">[Administrar orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="96d3e-123">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="96d3e-124">[Cómo separar una orquestación](../core/how-to-unbind-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="96d3e-124">[How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md) </span></span>  
 [<span data-ttu-id="96d3e-125">Implementar y administrar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="96d3e-125">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)