---
title: "Solución de problemas de herramientas de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 038a5f5c-d6eb-42db-88d6-70f3deba7a8a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7aedd8977042d15176781b0595bd5bb225a2fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-server-tools"></a><span data-ttu-id="b4866-102">Herramientas de solución de problemas de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b4866-102">Troubleshooting BizTalk Server Tools</span></span>
<span data-ttu-id="b4866-103">En este tema se proporciona una ubicación centralizada de información sobre problemas comunes que se pueden producir al usar las herramientas incluidas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4866-103">This topic provides a centralized location for information about common problems encountered while using the tools included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="b4866-104">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b4866-104">Known Issues</span></span>  
  
### <a name="biztalk-server-tools-and-utilities-may-not-function-correctly-on-a-windows-system-that-supports-uac"></a><span data-ttu-id="b4866-105">Es posible que las herramientas y utilidades de BizTalk Server no funcionen correctamente en un sistema Windows compatible con UAC</span><span class="sxs-lookup"><span data-stu-id="b4866-105">BizTalk Server Tools and Utilities May Not Function Correctly on a Windows System That Supports UAC</span></span>  
 <span data-ttu-id="b4866-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="b4866-106">**Problem**</span></span>  
  
 <span data-ttu-id="b4866-107">Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se instala en un sistema compatible con el control de cuentas de usuario (UAC), es posible que las herramientas incluidas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se inicien o no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4866-107">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a system that supports User Account Control (UAC), the tools included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may not launch successfully, or may not function correctly.</span></span>  
  
 <span data-ttu-id="b4866-108">**Causa**</span><span class="sxs-lookup"><span data-stu-id="b4866-108">**Cause**</span></span>  
  
 <span data-ttu-id="b4866-109">Al ejecutar una aplicación clasificada para un nivel de privilegios específico, si el nivel requerido es mayor que el del usuario que ejecuta la aplicación, UAC mostrará un mensaje que permite elevar temporalmente el privilegio de la aplicación al nivel necesario.</span><span class="sxs-lookup"><span data-stu-id="b4866-109">When running an application that has been flagged for a specific privilege level, if the required level is higher than that of the user running the application, the UAC will display a prompt that allows you to temporarily elevate the application privilege to the required level.</span></span> <span data-ttu-id="b4866-110">Las herramientas suministradas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no tienen las clasificaciones correctas habilitadas para solicitar automáticamente la elevación de privilegios, por lo que la herramienta intentará ejecutarse en el nivel de privilegios actual del usuario que ejecuta la aplicación y se producirá un error si se requiere un nivel de privilegios mayor.</span><span class="sxs-lookup"><span data-stu-id="b4866-110">The tools shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have the correct flags enabled to automatically request privilege elevation, so the tool will attempt to run at the current privilege level of the user running the application and will fail if a higher privilege level is required.</span></span>  
  
 <span data-ttu-id="b4866-111">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="b4866-111">**Resolution**</span></span>  
  
 <span data-ttu-id="b4866-112">Para resolver este problema, ejecute todas las herramientas de BizTalk Server con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="b4866-112">To resolve this problem, run all BizTalk Server tools with Administrative privileges.</span></span> <span data-ttu-id="b4866-113">Para ejecutar una herramienta con privilegios de administrador, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="b4866-113">To run a tool with Administrative privileges, right-click the application and then select **Run as administrator**.</span></span>  
  
 <span data-ttu-id="b4866-114">Para obtener más información sobre el Control de cuentas de usuario, consulte [http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167).</span><span class="sxs-lookup"><span data-stu-id="b4866-114">For more information about the User Account Control, see [http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167).</span></span>  
  
### <a name="sometimes-biztalk-mapper-toolbox-may-appear-empty"></a><span data-ttu-id="b4866-115">A veces, el cuadro de herramientas del Asignador de BizTalk puede aparecer vacío</span><span class="sxs-lookup"><span data-stu-id="b4866-115">Sometimes BizTalk Mapper Toolbox May Appear Empty</span></span>  
 <span data-ttu-id="b4866-116">**Problema**</span><span class="sxs-lookup"><span data-stu-id="b4866-116">**Problem**</span></span>  
  
 <span data-ttu-id="b4866-117">A veces, al abrir el cuadro de herramientas del Asignador en Visual Studio, no aparece ningún functoid en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="b4866-117">Sometimes, when you open the Mapper toolbox in Visual Studio, you do not see any functoids in the toolbox.</span></span>  
  
 <span data-ttu-id="b4866-118">**Causa**</span><span class="sxs-lookup"><span data-stu-id="b4866-118">**Cause**</span></span>  
  
 <span data-ttu-id="b4866-119">Es posible que se deba a un error en la instalación o desinstalación de los complementos y parches de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4866-119">Might be a probable corruption by install/uninstall of Visual Studio add-ins and/or patch(es).</span></span>  
  
 <span data-ttu-id="b4866-120">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="b4866-120">**Resolution**</span></span>  
  
 <span data-ttu-id="b4866-121">Para resolver este problema:</span><span class="sxs-lookup"><span data-stu-id="b4866-121">To resolve this problem:</span></span>  
  
1.  <span data-ttu-id="b4866-122">Cierre todas las instancias de ejecución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4866-122">Close all running instances of Visual Studio.</span></span>  
  
2.  <span data-ttu-id="b4866-123">Iniciar **Visual Studio Command Prompt** como administrador.</span><span class="sxs-lookup"><span data-stu-id="b4866-123">Start **Visual Studio Command Prompt** as an administrator.</span></span>  
  
3.  <span data-ttu-id="b4866-124">En el símbolo del sistema, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4866-124">At the command prompt, type the following command:</span></span>  
  
    ```  
    devenv.exe /setup  
    ```