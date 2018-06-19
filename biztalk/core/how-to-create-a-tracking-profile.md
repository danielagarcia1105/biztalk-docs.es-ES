---
title: Cómo crear un perfil de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, creating
- creating, tracking profiles
ms.assetid: 676ae7e8-f3eb-45f1-ad2e-807b434c0bf9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f5d6cbb210cb292cd8ae7d0e2f4ff811984377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248940"
---
# <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="92375-102">Cómo crear un perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="92375-102">How to Create a Tracking Profile</span></span>
<span data-ttu-id="92375-103">Se crean perfiles de seguimiento para vincular definiciones de actividad de BAM a ensamblados implementados y propiedades de mensajería de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="92375-103">You create tracking profiles to link BAM activity definitions to deployed assemblies and BizTalk Server messaging properties.</span></span> <span data-ttu-id="92375-104">Al abrir el Editor de perfiles de seguimiento, puede crear un perfil de seguimiento nuevo al hacer clic en el vínculo de actividad de importación o en el elemento de menú de importación.</span><span class="sxs-lookup"><span data-stu-id="92375-104">When you open the Tracking Profile Editor, you can create a new tracking profile by either clicking the import activity link or the import menu item.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="92375-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="92375-105">Prerequisites</span></span>  
 <span data-ttu-id="92375-106">A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:</span><span class="sxs-lookup"><span data-stu-id="92375-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="92375-107">Una base de datos existente de administración de BizTalk de la que tiene permisos.</span><span class="sxs-lookup"><span data-stu-id="92375-107">An existing BizTalk Management database to which you have permissions.</span></span>  
  
-   <span data-ttu-id="92375-108">El TPE configurado para utilizar la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="92375-108">The TPE configured to use the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="92375-109">Una definición de actividad de BAM existente en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="92375-109">An existing BAM activity definition in the BAM Primary Import database.</span></span>  
  
### <a name="to-create-a-tracking-profile"></a><span data-ttu-id="92375-110">Para crear un perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="92375-110">To create a tracking profile</span></span>  
  
1.  <span data-ttu-id="92375-111">En el equipo o equipos que se han identificado como el sistema de origen, abra la **Editor de perfiles de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="92375-111">On the computer or computers that you have identified as the source system, open the **Tracking Profile Editor**.</span></span> <span data-ttu-id="92375-112">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **BTSTrkEditor.exe**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="92375-112">To do this, click **Start**, click **Run**, type **BTSTrkEditor.exe**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92375-113">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="92375-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="92375-114">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="92375-114">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="92375-115">En medio del panel izquierdo del TPE, haga clic en **haga clic aquí para seleccionar una definición de actividad de BAM** vínculo.</span><span class="sxs-lookup"><span data-stu-id="92375-115">In the middle of the left pane of the TPE, click **Click here to import a BAM Activity Definition** link.</span></span> <span data-ttu-id="92375-116">Se abrirá la **Importar definición de actividad de BAM** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="92375-116">This opens the **Import BAM Activity Definition** dialog box.</span></span>  
  
3.  <span data-ttu-id="92375-117">Desde el **nombre de definición de actividad de BAM** cuadro de lista Seleccione la actividad en el que se va a basar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="92375-117">From the **BAM Activity Definition Name** list box select the activity on which to base the tracking.</span></span> <span data-ttu-id="92375-118">Si la lista contiene muchas actividades implementadas, puede escribir parte del nombre de la actividad en el **en cadena** cuadro de texto y haga clic en el **búsqueda** botón.</span><span class="sxs-lookup"><span data-stu-id="92375-118">If your list contains many deployed activities, you can type part of the activity name in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="92375-119">Esto limita la lista de actividades que se muestra para los nombres que contienen el nombre parcial que ha escrito.</span><span class="sxs-lookup"><span data-stu-id="92375-119">This limits the list of activities displayed to those whose names contain the partial name entered.</span></span>  
  
4.  <span data-ttu-id="92375-120">Una vez que haya seleccionado la actividad, haga clic en el **Aceptar** botón.</span><span class="sxs-lookup"><span data-stu-id="92375-120">Once you have selected the activity, click the **OK** button.</span></span> <span data-ttu-id="92375-121">Se abrirá un perfil de seguimiento nuevo basado en la actividad seleccionada y muestra el perfil en el panel izquierdo del TPE.</span><span class="sxs-lookup"><span data-stu-id="92375-121">This opens a new tracking profile based on the activity selected and displays the profile in the left pane of the TPE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92375-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="92375-122">See Also</span></span>  
 [<span data-ttu-id="92375-123">Creación de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="92375-123">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)