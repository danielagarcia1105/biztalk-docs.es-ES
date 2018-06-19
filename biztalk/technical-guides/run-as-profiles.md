---
title: Perfiles de ejecución | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98ac0a0c-91d8-4d12-aa40-2ad2e29ec784
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69fa6c9401f606619b2fb8d22d95ded48c18a092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301980"
---
# <a name="run-as-profiles"></a><span data-ttu-id="cbfa0-102">Perfiles de ejecución</span><span class="sxs-lookup"><span data-stu-id="cbfa0-102">Run As Profiles</span></span>
<span data-ttu-id="cbfa0-103">Cuando el módulo de administración de BizTalk Server Core Library se importa por primera vez, se crean dos nuevos perfiles de ejecución:</span><span class="sxs-lookup"><span data-stu-id="cbfa0-103">When the BizTalk Server Core Library Management Pack is first imported, it creates two new Run As Profiles:</span></span>  
  
-   <span data-ttu-id="cbfa0-104">**Cuenta de detección de servidor BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-104">**BizTalk Server Discovery Account**.</span></span> <span data-ttu-id="cbfa0-105">Este perfil está asociado con todas las detecciones de componentes de la función de servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-105">This profile is associated with all discoveries of BizTalk Server role components.</span></span>  
  
-   <span data-ttu-id="cbfa0-106">**Cuenta de supervisión de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-106">**BizTalk Server Monitoring Account**.</span></span> <span data-ttu-id="cbfa0-107">Este perfil está asociado con todos los monitores y tareas.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-107">This profile is associated with all monitors and tasks.</span></span>  
  
 <span data-ttu-id="cbfa0-108">Forma predeterminada, todas las detecciones, monitores y tareas definidas en el valor predeterminado de módulos de administración de BizTalk Server para usar las cuentas definidas en la "Cuenta de acción predeterminada" perfil de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-108">By default, all discoveries, monitors, and tasks defined in the BizTalk Server Management Packs default to using the accounts defined in the “Default Action Account” Run As Profile.</span></span>  <span data-ttu-id="cbfa0-109">Si la cuenta de acción predeterminada de un sistema concreto no tiene los permisos necesarios para detectar o supervisar BizTalk, esos sistemas pueden estar limitados por credenciales más específicas en el BizTalk Server como perfiles de ejecución, que sí tienen acceso a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-109">If the default action account for a given system does not have the necessary permissions to discover or monitor BizTalk, then those systems can be bound to more specific credentials in the BizTalk Server Run As Profiles, which do have access to BizTalk Server.</span></span>  
  
 <span data-ttu-id="cbfa0-110">Éstos son los pasos genéricos necesarios para configurar perfiles de ejecución de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="cbfa0-110">The following are the generic steps to configure Run As Profiles for BizTalk Server:</span></span>  
  
### <a name="to-configure-run-as-profiles"></a><span data-ttu-id="cbfa0-111">Para configurar perfiles de ejecución</span><span class="sxs-lookup"><span data-stu-id="cbfa0-111">To configure Run As profiles</span></span>  
  
1.  <span data-ttu-id="cbfa0-112">Identifique los nombres de los equipos de destino que la cuenta de acción predeterminada no tiene derechos suficientes para supervisar BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-112">Identify the name(s) of the target computer(s) where the default action account has insufficient rights to monitor BizTalk Server.</span></span>  
  
2.  <span data-ttu-id="cbfa0-113">Para cada sistema crear o usar un conjunto existente de credenciales que tienen al menos los privilegios de BizTalk Server tratados en la [entornos con pocos privilegios](../technical-guides/low-privilege-environments.md) sección de esta guía del módulo de administración.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-113">For each system create or use an existing set of credentials that have at least the BizTalk Server privileges discussed in the [Low-Privilege Environments](../technical-guides/low-privilege-environments.md) section of this management pack guide.</span></span>  
  
3.  <span data-ttu-id="cbfa0-114">Para cada conjunto de credenciales identificado en el paso 2, asegúrese de que existe una correspondiente cuenta de ejecución del grupo de administración.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-114">For each set of credentials identified in step 2, make sure that a corresponding Run As Account exists in the management group.</span></span> <span data-ttu-id="cbfa0-115">Si es necesario, cree la cuenta de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-115">Create the Run As Account if it is necessary.</span></span>  
  
4.  <span data-ttu-id="cbfa0-116">Configurar las asignaciones entre los destinos y las cuentas Ejecutar como en el **cuentas de ejecución** ficha de cada uno de los perfiles de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cbfa0-116">Set up the mappings between the targets and the Run As Account(s) on the **Run As Accounts** tab of each of the Run As Profiles.</span></span>