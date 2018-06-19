---
title: Cómo detener una orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], stopping
- orchestrations, stopping
ms.assetid: a8009c23-ca83-4d2f-97dd-df660adbc279
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57e51842171c31f2da509e92d9364948aeceb1d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255924"
---
# <a name="how-to-stop-an-orchestration"></a><span data-ttu-id="94293-102">Cómo detener una orquestación</span><span class="sxs-lookup"><span data-stu-id="94293-102">How to Stop an Orchestration</span></span>
<span data-ttu-id="94293-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para detener una orquestación.</span><span class="sxs-lookup"><span data-stu-id="94293-103">This topic describes how to use the BizTalk Server Administration console to stop an orchestration.</span></span> <span data-ttu-id="94293-104">Al detener una orquestación, se desactivan y suspenden todos los mensajes de activación que se reciben.</span><span class="sxs-lookup"><span data-stu-id="94293-104">Stopping an orchestration deactivates and suspends all of the arriving activation messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94293-105">El desarrollador de aplicaciones detiene una orquestación durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="94293-105">The application developer stop an orchestration during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94293-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="94293-106">Prerequisites</span></span>  
 <span data-ttu-id="94293-107">Para llevar a cabo el procedimiento descrito en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores o del grupo de operadores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="94293-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="94293-108">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="94293-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-stop-an-orchestration"></a><span data-ttu-id="94293-109">Para detener una orquestación</span><span class="sxs-lookup"><span data-stu-id="94293-109">To stop an orchestration</span></span>  
  
1.  <span data-ttu-id="94293-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="94293-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="94293-111">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación que desea detener.</span><span class="sxs-lookup"><span data-stu-id="94293-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to stop.</span></span>  
  
3.  <span data-ttu-id="94293-112">Haga clic en **orquestaciones**, haga clic en la orquestación y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="94293-112">Click **Orchestrations**, right-click the orchestration, and then click **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94293-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="94293-113">See Also</span></span>  
 <span data-ttu-id="94293-114">[Administrar orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="94293-114">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="94293-115">[Cómo iniciar una orquestación](../core/how-to-start-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="94293-115">[How to Start an Orchestration](../core/how-to-start-an-orchestration.md) </span></span>  
 [<span data-ttu-id="94293-116">Cómo iniciar y detener una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="94293-116">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)