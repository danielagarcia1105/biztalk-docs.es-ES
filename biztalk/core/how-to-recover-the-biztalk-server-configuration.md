---
title: Cómo recuperar la configuración del servidor de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1d39e50-4296-49c7-bd1e-63b1325af168
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 179ff0690c7c07dcf58bf2d7fd92a885435509cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980341"
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a><span data-ttu-id="fa0e9-102">Cómo recuperar la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fa0e9-102">How to Recover the BizTalk Server Configuration</span></span>
<span data-ttu-id="fa0e9-103">Como parte de la recuperación del servidor BizTalk, también debe importar el archivo de configuración que creó cuando instaló el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fa0e9-103">As part of recovering your BizTalk server, you must also import the configuration file that you created when you installed BizTalk Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fa0e9-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fa0e9-104">Prerequisites</span></span>  
 <span data-ttu-id="fa0e9-105">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="fa0e9-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-the-biztalk-server-configuration"></a><span data-ttu-id="fa0e9-106">Para recuperar la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fa0e9-106">To recover the BizTalk Server configuration</span></span>  
  
1. <span data-ttu-id="fa0e9-107">Con el Bloc de notas, edite el archivo de configuración de BizTalk Server del que previamente ha realizado una copia de seguridad, escriba las contraseñas de la cuenta de usuario para todos los servicios de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fa0e9-107">Using Notepad, edit the BizTalk Server configuration file that you previously backed up, and enter the user account passwords for all of the BizTalk Server services.</span></span>  
  
2. <span data-ttu-id="fa0e9-108">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="fa0e9-108">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
3. <span data-ttu-id="fa0e9-109">En **configuración de Microsoft BizTalk Server**, haga clic en **importar configuración**.</span><span class="sxs-lookup"><span data-stu-id="fa0e9-109">In **Microsoft BizTalk Server Configuration**, click **Import Configuration**.</span></span>  
  
    <span data-ttu-id="fa0e9-110">Compruebe que no aparezca ningún icono de invalidación frente a ninguna característica.</span><span class="sxs-lookup"><span data-stu-id="fa0e9-110">Verify that there are no invalidation icons appearing in front of any feature.</span></span> <span data-ttu-id="fa0e9-111">Si alguna de las características tiene errores de configuración, es el momento de corregirlos.</span><span class="sxs-lookup"><span data-stu-id="fa0e9-111">If any of the features have configuration errors, now is the time to correct them.</span></span>  
  
4. <span data-ttu-id="fa0e9-112">Haga clic en **Aplicar configuración**.</span><span class="sxs-lookup"><span data-stu-id="fa0e9-112">Click **Apply Configuration**.</span></span>  
  
    <span data-ttu-id="fa0e9-113">Cuando se hayan configurado todas las características de BizTalk Server, cierre la ventana de configuración.</span><span class="sxs-lookup"><span data-stu-id="fa0e9-113">After all of the BizTalk Server features are configured, close the configuration window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0e9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa0e9-114">See Also</span></span>  
 <span data-ttu-id="fa0e9-115">[Recuperación de un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="fa0e9-115">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="fa0e9-116">Cómo realizar copias de seguridad de la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fa0e9-116">How to Back Up The BizTalk Server Configuration</span></span>](../core/how-to-back-up-the-biztalk-server-configuration.md)