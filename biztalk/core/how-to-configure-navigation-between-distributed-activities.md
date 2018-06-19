---
title: Cómo configurar la exploración entre distribuidas actividades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f8faf0a-eb06-4383-932d-4106306d6cf3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ab210f5ab728134b406b5c4bdaf25a1ec6db1c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968874"
---
# <a name="how-to-configure-navigation-between-distributed-activities"></a><span data-ttu-id="5aa2c-102">Cómo configurar la exploración entre actividades distribuidas</span><span class="sxs-lookup"><span data-stu-id="5aa2c-102">How to Configure Navigation Between Distributed Activities</span></span>
<span data-ttu-id="5aa2c-103">La exploración distribuida permite a los usuarios ver actividades existentes en implementaciones de BAM remotas.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-103">Distributed navigation allows users to view activities that exist in remote BAM deployments.</span></span> <span data-ttu-id="5aa2c-104">Al habilitar la exploración distribuida, los usuarios del portal de BAM de un equipo serán capaces de ver actividades en el portal de BAM de otra implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aa2c-104">When you enable distributed navigation, users of the BAM portal on one computer will be able to view activities in the BAM portal on another deployment of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5aa2c-105">El procedimiento de este tema describe cómo habilitar la exploración distribuida en el siguiente escenario:</span><span class="sxs-lookup"><span data-stu-id="5aa2c-105">The procedure in this topic describes how to enable distributed navigation in the following scenario:</span></span>  
  
-   <span data-ttu-id="5aa2c-106">Un departamento de ventas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementado en el equipo 1.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-106">A sales department with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployed on computer 1.</span></span>  
  
-   <span data-ttu-id="5aa2c-107">Un departamento de envíos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementado en el equipo 2.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-107">A shipping department with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployed on computer 2.</span></span>  
  
-   <span data-ttu-id="5aa2c-108">Una vista denominada myBusinessView con una actividad denominada Datos de ventas implementada en el equipo 1.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-108">A view called myBusinessView with an activity called Sales Data deployed on computer 1.</span></span>  
  
-   <span data-ttu-id="5aa2c-109">Una vista denominada myBusinessView con una actividad denominada Datos de envíos instalada en el equipo 2.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-109">A view called myBusinessView with an activity called Shipping Data installed on computer 2.</span></span>  
  
-   <span data-ttu-id="5aa2c-110">Un usuario empresarial del departamento de ventas con una empresa necesita ver las actividades en ambos equipos.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-110">A business user in the sales department with a business need to see the activities on both computers.</span></span>  
  
### <a name="how-to-set-up-distributed-navigation-for-remote-activities"></a><span data-ttu-id="5aa2c-111">Cómo configurar la exploración distribuida para actividades remotas</span><span class="sxs-lookup"><span data-stu-id="5aa2c-111">How to set up distributed navigation for remote activities</span></span>  
  
1.  <span data-ttu-id="5aa2c-112">El administrador del equipo 1 concede al usuario empresarial acceso a la vista myBusinessView en el equipo 1.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-112">The administrator of computer 1 grants the business user access to the myBusinessView view on computer 1.</span></span> <span data-ttu-id="5aa2c-113">Use el comando bm.exe, como se indica a continuación: **agregar-account - AccountName:\<nombre de la cuenta\> -View:** myBusinessView</span><span class="sxs-lookup"><span data-stu-id="5aa2c-113">You use the bm.exe command, as follows: **add-account -AccountName:\<account name\> -View:** myBusinessView</span></span>  
  
2.  <span data-ttu-id="5aa2c-114">El administrador del equipo 1 habilita la exploración distribuida ejecutando el comando enable-reference, como se indica a continuación: **bm.exe enable-reference - TargetServer:** Equipo2 **- TargetDatabase:\<destino base de datos\>**</span><span class="sxs-lookup"><span data-stu-id="5aa2c-114">The administrator on computer 1 enables distributed navigation by running the enable reference command, as follows: **bm.exe enable-reference -TargetServer:** computer2 **-TargetDatabase:\<target database\>**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5aa2c-115">Por lo general, la cuenta utilizada entre departamentos para el acceso a los servicios Web de BAM variará de un equipo a otro.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-115">Typically the account used between departments for BAM Web services access will be different on different computers.</span></span> <span data-ttu-id="5aa2c-116">Por lo tanto, en este escenario el administrador del equipo 1 debe agregar la cuenta de suplantación de servicios Web del equipo 1 a la función BAM_ManagementWS de la base de datos de importación principal de BAM para el equipo 2.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-116">Therefore, in this scenario the administrator of computer 1 must add the Web services Impersonation account of computer 1 to the BAM_ManagementWS role of the BAM Primary Import database for computer 2.</span></span> <span data-ttu-id="5aa2c-117">Para obtener más información, vea "Ver y modificar las pertenencias a roles" en [http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990).</span><span class="sxs-lookup"><span data-stu-id="5aa2c-117">For more information, see "Viewing and Modifying Role Memberships" at [http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5aa2c-118">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
3.  <span data-ttu-id="5aa2c-119">El administrador del equipo 2 concede al usuario empresarial acceso a la vista myBusinessView en el equipo 2 utilizando el comando BM.exe como se indicó en el paso 1:</span><span class="sxs-lookup"><span data-stu-id="5aa2c-119">The administrator of computer 2 grants the business user access to the myBusinessView view on computer 2 using the BM.exe command as noted in step 1.</span></span>  
  
## <a name="results-of-setting-up-distributed-navigation"></a><span data-ttu-id="5aa2c-120">Resultados de la configuración de la exploración distribuida</span><span class="sxs-lookup"><span data-stu-id="5aa2c-120">Results of Setting Up Distributed Navigation</span></span>  
 <span data-ttu-id="5aa2c-121">Cuando se habilita la exploración distribuida, los usuarios agregados a las vistas de los dos equipos verán, en el panel Mis vistas del portal de inicio correspondiente, las actividades de las vistas implementadas en ellos.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-121">When distributed navigation is enabled the users added to the views on both computers will see the activities for the views deployed on both computers in the My Views pane of their home portal.</span></span> <span data-ttu-id="5aa2c-122">Cuando estos usuarios hacen clic en una actividad hospedada en una implementación remota, se les conduce directamente al portal en el que se hospeda esa actividad y se les permite verla como si estuviera en el portal predeterminado que les corresponde.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-122">When these users click an activity that is hosted on a remote deployment, they are seamlessly directed to the portal on which that activity is hosted and they are able to view the activity as if it were on their default portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5aa2c-123">La exploración distribuida se puede habilitar en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-123">Distributed navigation can be enabled in both directions.</span></span> <span data-ttu-id="5aa2c-124">Si se sigue el procedimiento anterior en los dos equipos que comparten actividades remotas, se permite a los usuarios empresariales de cualquiera de los equipos utilizar la exploración distribuida.</span><span class="sxs-lookup"><span data-stu-id="5aa2c-124">Following the procedure above on both computers that are sharing remote activities enables business users of the portals on either computer to use distributed navigation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa2c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5aa2c-125">See Also</span></span>  
 <span data-ttu-id="5aa2c-126">[Administrar la exploración distribuida de actividades remotas](../core/managing-distributed-navigation-of-remote-activities.md) </span><span class="sxs-lookup"><span data-stu-id="5aa2c-126">[Managing Distributed Navigation of Remote Activities](../core/managing-distributed-navigation-of-remote-activities.md) </span></span>  
 [<span data-ttu-id="5aa2c-127">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="5aa2c-127">BAM Portal</span></span>](../core/bam-portal.md)