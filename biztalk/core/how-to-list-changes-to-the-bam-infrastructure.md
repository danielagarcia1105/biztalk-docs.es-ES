---
title: Cómo enumerar los cambios en la infraestructura de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], listing infrastructure changes
- managing [BAM definitions], listing infrastructure changes
- Get-Changes command [BAM]
- infrastructure, listing changes [BAM]
ms.assetid: 3feacd7d-6f42-4626-835b-0dc3befc9fd6
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4c0d2efc67e4329502b0eac7a11ddbd72f8bcee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998085"
---
# <a name="how-to-list-changes-to-the-bam-infrastructure"></a><span data-ttu-id="c6d0a-102">Cómo enumerar cambios en la estructura de BAM</span><span class="sxs-lookup"><span data-stu-id="c6d0a-102">How to List Changes to the BAM Infrastructure</span></span>
<span data-ttu-id="c6d0a-103">Los administradores utilizan el **get-changes** comando de la utilidad de administración de BAM para enumerar información actual sobre una definición de BAM implementada.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-103">Administrators use the **get-changes** command of the BAM Management utility to list current information about a deployed BAM definition.</span></span> <span data-ttu-id="c6d0a-104">También puede utilizar el comando get-changes para enumerar los artefactos de implementación en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-104">You can also use the get-changes command to list current deployment artifacts in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="c6d0a-105">La información incluye implementaciones y anulaciones de implementaciones que se han llevado a cabo correctamente, el nombre del archivo de definición de BAM, el nombre del archivo de configuración de BAM, los nombres de todas las actividades y vistas asociadas al archivo de definición y la cuenta de usuario que aplicó el cambio.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-105">The information includes successful deployments and undeployments, the name of the BAM definition file, the name of the BAM configuration file, the names of all activities and views associated with the definition file, and the user account that applied the change.</span></span> <span data-ttu-id="c6d0a-106">La lista get-changes muestra las implementaciones y las supresiones de definiciones con sus números de identificación asociados.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-106">The get-changes list shows deployments and definition removals with their associated identification numbers.</span></span>  
  
### <a name="to-list-changes-to-the-bam-definition"></a><span data-ttu-id="c6d0a-107">Para enumerar cambios en la definición de BAM</span><span class="sxs-lookup"><span data-stu-id="c6d0a-107">To list changes to the BAM definition</span></span>  
  
1. <span data-ttu-id="c6d0a-108">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-108">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="c6d0a-109">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-109">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="c6d0a-110">Tipo **bm get-changes.**</span><span class="sxs-lookup"><span data-stu-id="c6d0a-110">Type **bm get-changes.**</span></span>  
  
4. <span data-ttu-id="c6d0a-111">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d0a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6d0a-112">See Also</span></span>  
 <span data-ttu-id="c6d0a-113">[Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="c6d0a-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="c6d0a-114">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="c6d0a-114">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="c6d0a-115">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="c6d0a-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)