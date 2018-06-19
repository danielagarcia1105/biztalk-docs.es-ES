---
title: Cómo cambiar la ubicación de destino de una secuencia de comandos previa y posteriores al procesamiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, file locations
- scripts, modifying
- managing [scripts], modifying
- managing [scripts], file locations
ms.assetid: 4a4fdaef-099f-4c29-9815-12404c7a2212
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eb4ba338790e301e54a9bf262a49808a0a55315
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249292"
---
# <a name="how-to-change-the-destination-location-of-a-pre--or-post-processing-script"></a><span data-ttu-id="ef7b5-102">Cómo cambiar la ubicación de destino de secuencias de comandos previas y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="ef7b5-102">How to Change the Destination Location of a Pre- or Post-processing Script</span></span>
<span data-ttu-id="ef7b5-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para cambiar la ubicación de destino de secuencias de comandos previas y posteriores al procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ef7b5-103">This topic describes how to use the BizTalk Server Administration console to change the destination location of a pre- or post-processing script.</span></span> <span data-ttu-id="ef7b5-104">Se trata de la ubicación en la que se copia la secuencia de comandos cuando se instala la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef7b5-104">This is the location to which the script is copied when the application is installed.</span></span> <span data-ttu-id="ef7b5-105">Puede que desee cambiar la ubicación de destino al implementar una aplicación en otro entorno.</span><span class="sxs-lookup"><span data-stu-id="ef7b5-105">You might want to change the destination location when deploying an application into a different environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ef7b5-106">Asegúrese de proporcionar una ubicación de destino para la secuencia de comandos que se va a ejecutar al desinstalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef7b5-106">Be sure to provide a destination location for a script that will run when the application is uninstalled.</span></span> <span data-ttu-id="ef7b5-107">Si no se hace así, la secuencia de comandos no se copiará en el sistema de archivos local y, por tanto, no se ejecutará durante la desinstalación.</span><span class="sxs-lookup"><span data-stu-id="ef7b5-107">If you do not, the script will not be copied to the local file system, and therefore will not run during uninstallation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ef7b5-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ef7b5-108">Prerequisites</span></span>  
 <span data-ttu-id="ef7b5-109">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ef7b5-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ef7b5-110">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="ef7b5-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-properties-of-a-pre--or-post-processing-script"></a><span data-ttu-id="ef7b5-111">Para modificar las propiedades de implementación de secuencias de comandos previas y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="ef7b5-111">To modify the deployment properties of a pre- or post-processing script</span></span>  
  
1.  <span data-ttu-id="ef7b5-112">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ef7b5-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ef7b5-113">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk que contiene el script que se va a modificar y, a continuación, expanda la aplicación que contiene el script.</span><span class="sxs-lookup"><span data-stu-id="ef7b5-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the script to modify, and then expand the application containing the script.</span></span>  
  
3.  <span data-ttu-id="ef7b5-114">Haga clic en el **recursos** carpeta, haga clic en la secuencia de comandos y, a continuación, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="ef7b5-114">Click the **Resources** folder, right-click the script, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="ef7b5-115">En **ubicación de destino**, escriba la ruta de acceso completa de la ubicación de destino, incluidos el nombre de archivo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ef7b5-115">In **Destination location**, type the full path of the destination location, including the file name, and then click **OK**.</span></span> <span data-ttu-id="ef7b5-116">(Puede utilizar la variable de entorno %BTAD_InstallDir% en la ruta para especificar la carpeta de instalación de la aplicación).</span><span class="sxs-lookup"><span data-stu-id="ef7b5-116">(You can use the environment variable %BTAD_InstallDir% in the path to specify the application installation folder.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef7b5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef7b5-117">See Also</span></span>  
 [<span data-ttu-id="ef7b5-118">Administrar secuencias de comandos previas y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="ef7b5-118">Managing Pre- and Post-processing Scripts</span></span>](../core/managing-pre-and-post-processing-scripts.md)