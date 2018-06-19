---
title: Supervisión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7effa38f-f9f2-40b7-8d8b-fa13cf94aa4f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9c45bb70e3f92f4c85def07add4390a0451cb87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298908"
---
# <a name="monitoring"></a><span data-ttu-id="5254a-102">Supervisión</span><span class="sxs-lookup"><span data-stu-id="5254a-102">Monitoring</span></span>
<span data-ttu-id="5254a-103">De forma predeterminada, todos los de supervisión de BizTalk Server y tareas utilizan la cuenta de acción predeterminada cuando no hay que ninguna cuenta de ejecución específica definida para el destino en el perfil de ejecución de la cuenta de supervisión de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5254a-103">By default, all BizTalk Server monitoring and tasks use the default action account when there is no specific Run As Account defined for the target in the Run As Profile of the BizTalk Server Monitoring Account.</span></span> <span data-ttu-id="5254a-104">Para configurar una cuenta de ejecución con el conjunto mínimo de permisos necesarios para que BizTalk Server con fines de supervisión, se requieren los permisos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5254a-104">To configure a Run As Account with the minimum set of permissions that are required for BizTalk Server monitoring purposes, the following permissions are required:</span></span>  
  
-   <span data-ttu-id="5254a-105">La cuenta debe ser miembro del grupo de administradores integrado y el grupo de usuarios de monitores de rendimiento del equipo supervisado.</span><span class="sxs-lookup"><span data-stu-id="5254a-105">The account must be a member of the monitored computer’s built-in Administrators group and Performance Monitors Users group.</span></span>  
  
-   <span data-ttu-id="5254a-106">La cuenta debe ser miembro del rol SysAdmin en la instancia SQL o instancias que hospeda las bases de datos y los trabajos para el grupo de BizTalk que se está supervisando.</span><span class="sxs-lookup"><span data-stu-id="5254a-106">The account must be a member of the SysAdmin role within the SQL instance or instances hosting the databases and jobs for the BizTalk group that is being monitored.</span></span>  
  
-   <span data-ttu-id="5254a-107">Para fines de supervisión de BizTalk Server, la cuenta debe ser una parte del grupo de operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5254a-107">For BizTalk Server monitoring purposes, the account must be a part of BizTalk Operators group.</span></span>  
  
-   <span data-ttu-id="5254a-108">Para ejecutar tareas a través de la consola de SCOM, la cuenta debe ser una parte del grupo de usuarios de la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5254a-108">For running tasks through SCOM console, the account must be a part of BizTalk Application Users group.</span></span>  
  
-   <span data-ttu-id="5254a-109">Para realizar tareas administrativas, la cuenta debe ser una parte del grupo de administradores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5254a-109">For performing administrative tasks, the account must be a part of BizTalk Administrator group.</span></span>